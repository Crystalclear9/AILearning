# 图机器学习

在关系结构上学习表示，理解消息传递、图任务和图数据特有的泄漏。

**先修知识：** 图结构、线性代数、神经网络。

## 学习顺序与覆盖范围

先补[图遍历](../../ComputerScience/DataStructuresAndAlgorithms/02-二分排序与图遍历.md)。第 1 章定义消息传递，第 2 章建立图可见性与评价边界，第 3 章手算并比较具体聚合器，第 4 章扩展任务。第 2 章先提醒风险，第 3 章再深入机制，属于概览到推演的递进。

基础正文解释概念与计算，各章的进阶小节讨论证明、方法联系、实现等价条件与失效反例。已有基础可直接使用章内目录进入进阶；本主题最后一章另有研究练习和解析。阅读策略见[进阶学习路线](../../学习路线.md#advanced)。

| 章节 | 主要内容 | 深入讲解入口 |
| --- | --- | --- |
| [图表示消息传递与GCN](01-图表示消息传递与GCN.md) | 图比普通表多了关系；消息传递的三个步骤；进阶：消息传递的置换等变性 | [进入讲解](01-图表示消息传递与GCN.md#deep-dive-2) |
| [过平滑采样与图评估](02-过平滑采样与图评估.md) | 图网络并非越深越好；Transductive 与 inductive；进阶：过平滑与过挤压是不同机制 | [进入讲解](02-过平滑采样与图评估.md#deep-dive-1) |
| [GCN手算GraphSAGE与图注意力](03-GCN手算GraphSAGE与图注意力.md) | 一个三节点例子；GraphSAGE；专题反例：均值聚合能否识别邻居集合 | [进入讲解](03-GCN手算GraphSAGE与图注意力.md#deep-dive-2) |
| [图级任务异质图与评估实践](04-图级任务异质图与评估实践.md) | 图级读出；异质图与边属性；进阶：图任务的独立单位与负采样 | [进入讲解](04-图级任务异质图与评估实践.md#deep-dive-1) |

## 如何完成本主题

完成各章后，先独立作答[综合练习：链接预测的候选边可见性](04-图级任务异质图与评估实践.md#sec-8-1)，再对照逐步解析与验收要求。

读完一章后，先不看答案复述定义、假设与计算过程，再完成正文实验和练习。代码章节要能解释每个轴、变量和关键步骤；理论章节要能手算一个例子，并指出结论在哪些条件下成立。遇到不熟悉的先修概念，返回相关主题补学。

## 与其他主题的联系

- [数据结构与算法](../../ComputerScience/DataStructuresAndAlgorithms/README.md)
- [模型评估](../../MachineLearning/ModelEvaluation/README.md)

## 参考资料

- [GCN 原始论文](https://arxiv.org/abs/1609.02907)
- [GraphSAGE 论文](https://arxiv.org/abs/1706.02216)
- [PyTorch Geometric 官方教程](https://pytorch-geometric.readthedocs.io/en/latest/get_started/introduction.html)

- [GIN与消息传递表达能力分析](https://arxiv.org/abs/1810.00826)

[分类目录](../README.md) · [总目录](../../README.md)
