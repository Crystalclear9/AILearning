# 第 2 章 LSTM门控GRU与应用边界

[主题目录](README.md) · [分类目录](../README.md) · [总目录](../../README.md) · [上一章](01-序列状态与时间反向传播.md) · [下一章](03-序列到序列与注意力桥接.md)

## 本章目录

- [1. LSTM 如何管理记忆](#sec-1)
  - [基础算例：遗忘门的持续作用可以手算](#sec-1-1)
  - [深入讲解：门控状态怎样在保留遗忘和读出之间分工](#deep-dive-1)
- [2. GRU 的简化思路](#sec-2)
  - [机制展开：GRU 插值与重置门的计算位置](#sec-2-1)
  - [实现核对：与 GRUCell 比较前向及全部一阶梯度](#sec-2-2)
- [3. 一个前向示例](#sec-3)
- [4. 门控不是永久记忆保证](#sec-4)
- [5. 多层与双向的维度](#sec-5)
- [6. 进阶：LSTM加法路径的有限保证](#sec-6)
  - [门控把记忆通路与新增内容分开](#sec-6-1)
- [7. 练习与参考答案](#sec-7)
  - [边界追问：相同 hidden size 是否代表同参数量](#sec-7-1)

<a id="sec-1"></a>

## 1. LSTM 如何管理记忆

LSTM 除隐藏状态 $h_t$ 外还有细胞状态 $c_t$。遗忘门 $f_t$ 决定保留旧记忆的比例，输入门 $i_t$ 决定写入新候选的比例，输出门 $o_t$ 控制暴露多少记忆：

$$c_t=f_t\odot c_{t-1}+i_t\odot\tilde c_t,\qquad
h_t=o_t\odot\tanh(c_t).$$

门通常由当前输入与旧隐藏状态经过 sigmoid 得到，取值在 0 到 1。加法路径有助于保留信息与梯度，但不保证能无损记住所有长序列。

<a id="sec-1-1"></a>

### 基础算例：遗忘门的持续作用可以手算

暂不加入新内容，记忆每步乘遗忘门 f。若 f=0.5，十步后保留比例为 1/1024；若 f=0.99，十步后约为 0.904。门控提供调节记忆时间尺度的通道，但不保证网络一定学会合适门值。还存在门饱和、输入质量和优化问题。用这种受控例子能理解直接记忆路径，再讨论真实网络中门值依赖状态与其他梯度路径的情况。

<a id="deep-dive-1"></a>

### 深入讲解：门控状态怎样在保留遗忘和读出之间分工

LSTM常写遗忘门f、输入门i、候选g，细胞状态 $c_t=f_t\odot c_{t-1}+i_t\odot g_t$，输出 $h_t=o_t\odot\tanh(c_t)$。门在(0,1)调节通过量，状态加法提供较直接的记忆路径，但门本身依输入和旧状态，完整梯度仍需计入这些依赖。

若某维f≈1、i≈0，该维近似保留旧记忆；f≈0、i≈1则主要写入候选。门不是人为规则，而是训练学习的连续函数。仅观察一个门值不能确定该维长期语义。

GRU常以更新门组合旧状态与候选，重置门影响候选如何读取历史。不同实现对更新门方向、重置位置和偏置拆分有约定，移植参数需核对，不能只因公式名称相同就期待输出一致。

多层、双向最终状态轴包含层与方向，不是时间。LSTM还区分h与c；使用最后时间位置输出也未必等于双向最终状态拼接。以短序列手算和与参考模块对照，可发现门顺序及轴错误。

门控改善某些长期依赖的可学性，却不自动解决缺失信息、长时域噪声或训练分布变化。应与简单序列基线、真实长度和可见范围共同评价。

<a id="sec-2"></a>

## 2. GRU 的简化思路

GRU 通常合并状态，通过更新门在旧状态与新候选之间插值，通过重置门控制计算候选时使用多少历史。不同实现的门顺序和公式约定可能略有差别。与 LSTM 相比，它通常参数更少，但不能据此断言总是更快或更准确。

<a id="sec-2-1"></a>

### 机制展开：GRU 插值与重置门的计算位置

按 [PyTorch 的公式约定](https://docs.pytorch.org/docs/2.14/generated/torch.nn.GRU.html)，$n_t=\tanh(W_{in}x_t+b_{in}+r_t\odot(W_{hn}h_{t-1}+b_{hn}))$，$h_t=(1-z_t)\odot n_t+z_t\odot h_{t-1}$。z 趋近 1 时更保留旧状态。部分教材把重置门放在隐藏矩阵乘法之前，通常不是同一函数；跨实现复制参数时必须核对门序、偏置和乘法位置，而不只看张量尺寸。

<a id="sec-2-2"></a>

### 实现核对：与 GRUCell 比较前向及全部一阶梯度

下面按同一参数布局拆出重置门、更新门和候选项，使用双精度并固定输入。手写与参考函数先比较输出，再对同一个平方和目标比较输入、旧隐藏状态和所有参数梯度。代码特意保留两组偏置，并将重置门放在隐藏仿射变换之后，与本节引用的 PyTorch 约定一致。

```python
import torch
from torch import nn
from torch.nn import functional as F

torch.manual_seed(7)
cell = nn.GRUCell(input_size=2, hidden_size=2).double()
x = torch.randn(3, 2, dtype=torch.float64, requires_grad=True)
h = torch.randn(3, 2, dtype=torch.float64, requires_grad=True)
reference = cell(x, h)

input_parts = F.linear(x, cell.weight_ih, cell.bias_ih).chunk(3, dim=-1)
hidden_parts = F.linear(h, cell.weight_hh, cell.bias_hh).chunk(3, dim=-1)
i_r, i_z, i_n = input_parts
h_r, h_z, h_n = hidden_parts
reset = torch.sigmoid(i_r + h_r)
update = torch.sigmoid(i_z + h_z)
candidate = torch.tanh(i_n + reset * h_n)
manual = (1 - update) * candidate + update * h
assert torch.allclose(manual, reference, atol=1e-12, rtol=1e-12)

variables = (x, h, *tuple(cell.parameters()))
reference_grad = torch.autograd.grad(reference.square().sum(), variables)
manual_grad = torch.autograd.grad(manual.square().sum(), variables)
assert all(torch.allclose(a, b, atol=1e-10, rtol=1e-10)
           for a, b in zip(reference_grad, manual_grad))
print("maximum output difference:", (manual - reference).abs().max().item())
print("input, hidden state, and parameter gradients agree")
```

**进一步比较：** 将候选项改为先对 h 乘 reset、再做隐藏矩阵变换，一般不能继续通过相等断言。原因是逐坐标门控对应对角矩阵，通常不与任意隐藏权重矩阵交换；偏置位置也改变函数。这个反例说明跨框架复现不仅要匹配参数个数，还要匹配运算顺序。

<a id="sec-3"></a>

## 3. 一个前向示例

```python
import torch
from torch import nn
sequence = torch.randn(4, 6, 8)
rnn = nn.GRU(input_size=8, hidden_size=16, batch_first=True)
outputs, last = rnn(sequence)
print(outputs.shape)  # [4, 6, 16]：各时间步状态
print(last.shape)     # [1, 4, 16]：层数×方向数、批量、隐藏维
```

双向 RNN 同时使用左右上下文，适合已知完整序列的任务；实时预测未来时，不能偷用尚未到达的数据。时间序列的标准化与划分也必须符合时间边界。

<a id="sec-4"></a>

## 4. 门控不是永久记忆保证

若遗忘门长期接近 1 且输入门接近 0，细胞状态能较好保留旧信息；但门是学习得到的，受数据、优化和状态范围影响。长距离任务仍可能失败，也可能用与预期不同的短期线索完成训练。

比较 RNN、LSTM、GRU 与注意力模型时，应明确序列长度、实时性和资源。RNN 可以逐步处理流式数据，保持有限状态；全注意力可以直接关联远处位置，但长序列成本不同。不存在仅凭架构名称就适用于所有序列任务的统一胜者。

<a id="sec-5"></a>

## 5. 多层与双向的维度

多层 RNN 让一层输出序列作为下一层输入，双向则组合正向与反向状态。最终隐藏状态的第一维常包含层数乘方向数，不是时间长度。读取时应明确要哪层、哪个方向。

双向网络适用于完整上下文已知任务；实时流不能读取未来观察。模型选择必须先定义信息可见范围。

以批量 B、隐藏维 H、层数 L、双向数 D=2 为例，常见最终隐藏张量形状为 (L×D,B,H)，输出序列则在特征轴含两个方向的信息。取最后一层应先拆清层与方向，不能把第一个轴直接当作时间。

双向的“最后一个时间位置输出”通常不等于前后两方向最终状态的拼接：反向最终状态对应另一端。分类时按模型接口选择状态或掩码池化，并用长度不同样本核对。LSTM 还分别有 hidden 和 cell，维度相似但语义不同，传递时不可互换。

<a id="sec-6"></a>

## 6. 进阶：LSTM加法路径的有限保证

在固定门值的局部直觉下，细胞状态路径导数含遗忘门连乘，门接近一时可减少衰减；完整导数还包含门依赖旧状态的其他项。因此门控改善可学习长期依赖，但不保证无损无限记忆。

比较实验应把模型表达差异与执行实现分开：统一输入和训练预算，报告每步耗时、参数量及不同依赖跨度的表现。双向模型还改变可见信息，因此在线任务不能与读取未来的离线模型直接比成绩。

<a id="sec-6-1"></a>

### 门控把记忆通路与新增内容分开

LSTM 的核心更新 $c_t=f_t\odot c_{t-1}+i_t\odot\tilde c_t$ 包含一条加法记忆通路。暂忽略门对旧状态的间接依赖时，直接路径导数为 f；若 f 接近 1，直接衰减较小。这解释其设计动机，却不是所有长程梯度永远稳定的完整证明。

设旧记忆为 2、遗忘门为 0.9、输入门为 0.2、候选为 -1，则新记忆为 1.6。门值改变“保留多少”和“加入多少”，不等于为某个语义概念提供可直接解释的开关。隐藏输出还经过其他非线性与输出门。

GRU 以更少状态和门组织更新，参数与接口不同。公平比较应控制隐藏容量或参数预算，固定序列长度、训练轮次与评价协议；不能只用默认相同 hidden size 就宣布两者成本相同。短序列任务中简单基线也可能足够。

<a id="sec-7"></a>

## 7. 练习与参考答案

**练习：** 对实时传感器预测，直接用双向 LSTM 读取当前窗口之后的数据为什么不合法？

**答案：** 部署时未来观测不可获得，离线成绩会包含未来信息。可以在完整历史窗口内部双向编码，但预测时点后的数据必须排除。

<a id="sec-7-1"></a>

### 边界追问：相同 hidden size 是否代表同参数量

**问题：** 比较普通 RNN、GRU、LSTM 时都设 hidden size 为十六，能否称容量成本完全一致？

**推理解析：** 不能，门数量、状态结构和偏置不同，参数数及计算不同；双向与层数也改变可见信息。可分别做相同隐藏维和参数预算的比较，说明各自目的。结构名不提供统一优劣，需固定序列、实时性与训练评价协议。

---

[主题目录](README.md) · [分类目录](../README.md) · [总目录](../../README.md) · [上一章](01-序列状态与时间反向传播.md) · [下一章](03-序列到序列与注意力桥接.md)
