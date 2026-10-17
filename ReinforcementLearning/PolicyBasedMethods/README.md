# 策略梯度与Actor-Critic

直接优化动作分布，理解回报、优势、基线与 PPO 的关系。

**先修知识：** MDP、TD 与状态/动作价值、概率求导；神经网络实现需相应训练基础。

## 学习顺序与覆盖范围

进入 Actor-Critic 前，先掌握[价值方法中的 TD 与动作价值](../ValueBasedMethods/01-蒙特卡洛TD与动作价值.md)。本主题第 2 章先介绍优势与 PPO，第 3 章展开 GAE 和轨迹边界，第 4 章再组合训练循环；首次阅读第 2 章时可把 GAE 视为待展开的优势估计方法。

基础正文解释概念与计算，各章的进阶小节讨论证明、方法联系、实现等价条件与失效反例。已有基础可直接使用章内目录进入进阶；本主题最后一章另有研究练习和解析。阅读策略见[进阶学习路线](../../学习路线.md#advanced)。

| 章节 | 主要内容 | 深入讲解入口 |
| --- | --- | --- |
| [策略梯度与方差控制](01-策略梯度与方差控制.md) | 为什么直接学习策略；REINFORCE 的估计；进阶：策略梯度的对数导数推导 | [进入讲解](01-策略梯度与方差控制.md#deep-dive-2) |
| [Actor-Critic优势与PPO](02-Actor-Critic优势与PPO.md) | 两个角色分别学习什么；PPO 的概率比率；专题推导：PPO裁剪究竟截断哪一边 | [进入讲解](02-Actor-Critic优势与PPO.md#deep-dive-2) |
| [从REINFORCE到GAE的实现细节](03-从REINFORCE到GAE的实现细节.md) | 轨迹需要保存什么；一个策略梯度方向实验；进阶：GAE与bootstrap误差传播 | [进入讲解](03-从REINFORCE到GAE的实现细节.md#deep-dive-3) |
| [PPO训练循环与稳定性检查](04-PPO训练循环与稳定性检查.md) | 采样与更新分阶段；完整目标的组成；进阶：重要性比率与旧数据重用边界 | [进入讲解](04-PPO训练循环与稳定性检查.md#deep-dive-2) |

## 如何完成本主题

完成各章后，先独立作答[综合练习：PPO 的旧量与梯度边界](04-PPO训练循环与稳定性检查.md#sec-8-1)，再对照逐步解析与验收要求。

读完一章后，先不看答案复述定义、假设与计算过程，再完成正文实验和练习。代码章节要能解释每个轴、变量和关键步骤；理论章节要能手算一个例子，并指出结论在哪些条件下成立。遇到不熟悉的先修概念，返回相关主题补学。

## 与其他主题的联系

- [优化方法](../../Mathematics/Optimization/README.md)
- [深度强化学习](../../ReinforcementLearning/DeepRL/README.md)

## 参考资料

- [Spinning Up：强化学习基本概念](https://spinningup.openai.com/en/latest/spinningup/rl_intro.html)
- [Gymnasium：时间限制处理](https://gymnasium.farama.org/tutorials/gymnasium_basics/handling_time_limits/)
- [PPO 原始论文](https://arxiv.org/abs/1707.06347)
- [GAE 论文](https://arxiv.org/abs/1506.02438)

[分类目录](../README.md) · [总目录](../../README.md)
