# 深度强化学习

理解函数近似带来的不稳定性，学习 DQN、连续控制和严谨的评估协议。

**先修知识：** DQN 分支需要价值方法与 PyTorch；连续控制分支还需要策略梯度与 Actor-Critic。

## 学习顺序与覆盖范围

价值方法与 PyTorch 就绪后可先读第 1、3 章的 DQN 原理与更新；第 2、4 章的连续控制和离线问题在[Actor-Critic](../PolicyBasedMethods/README.md)之后阅读。按章顺读也可以，但不能将 DQN 必须先学 PPO 当作算法依赖。

基础正文解释概念与计算，各章的进阶小节讨论证明、方法联系、实现等价条件与失效反例。已有基础可直接使用章内目录进入进阶；本主题最后一章另有研究练习和解析。阅读策略见[进阶学习路线](../../学习路线.md#advanced)。

| 章节 | 主要内容 | 深入讲解入口 |
| --- | --- | --- |
| [DQN经验回放与目标网络](01-DQN经验回放与目标网络.md) | 从表格到神经网络；DQN 的两个关键机制；进阶：最大值过估计与Double方法 | [进入讲解](01-DQN经验回放与目标网络.md#deep-dive-2) |
| [连续控制奖励设计与实验](02-连续控制奖励设计与实验.md) | 连续动作的方法选择；奖励设计会改变行为；进阶：连续Actor-Critic的分布外动作问题 | [进入讲解](02-连续控制奖励设计与实验.md#deep-dive-1) |
| [DQN最小训练更新与DoubleDQN](03-DQN最小训练更新与DoubleDQN.md) | 批量更新公式；区分扩展；进阶：一次更新的梯度边界与算法差异 | [进入讲解](03-DQN最小训练更新与DoubleDQN.md#deep-dive-1) |
| [连续控制离线学习与复现协议](04-连续控制离线学习与复现协议.md) | 连续控制；离线限制；进阶：复现层级与统计有效性 | [进入讲解](04-连续控制离线学习与复现协议.md#deep-dive-2) |

## 如何完成本主题

DQN 支线在第 3 章核对目标、动作索引与梯度边界；连续控制与离线支线再由第 4 章的[综合练习：离线策略收益的证据范围](04-连续控制离线学习与复现协议.md#sec-8-1)验收。两条支线按所需先修分别进入。

读完一章后，先不看答案复述定义、假设与计算过程，再完成正文实验和练习。代码章节要能解释每个轴、变量和关键步骤；理论章节要能手算一个例子，并指出结论在哪些条件下成立。遇到不熟悉的先修概念，返回相关主题补学。

## 与其他主题的联系

- [PyTorch 深度学习编程](../../Programming/PyTorch/README.md)
- [模型评估](../../MachineLearning/ModelEvaluation/README.md)

## 参考资料

- [Spinning Up：强化学习基本概念](https://spinningup.openai.com/en/latest/spinningup/rl_intro.html)
- [Gymnasium：时间限制处理](https://gymnasium.farama.org/tutorials/gymnasium_basics/handling_time_limits/)
- [Double DQN 论文](https://arxiv.org/abs/1509.06461)
- [Spinning Up：DDPG](https://spinningup.openai.com/en/latest/algorithms/ddpg.html)
- [SAC 原始论文](https://arxiv.org/abs/1801.01290)

[分类目录](../README.md) · [总目录](../../README.md)
