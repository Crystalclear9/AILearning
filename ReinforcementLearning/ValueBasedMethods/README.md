# 价值方法

理解从采样回报到 TD、SARSA 和 Q-learning，并动手训练一个小型表格智能体。

**先修知识：** MDP、Bellman 方程；Python 与 NumPy。

## 学习顺序与覆盖范围

基础正文解释概念与计算，各章的进阶小节讨论证明、方法联系、实现等价条件与失效反例。已有基础可直接使用章内目录进入进阶；本主题最后一章另有研究练习和解析。阅读策略见[进阶学习路线](../../学习路线.md#advanced)。

| 章节 | 主要内容 | 深入讲解入口 |
| --- | --- | --- |
| [蒙特卡洛TD与动作价值](01-蒙特卡洛TD与动作价值.md) | 两类估计目标；SARSA 与 Q-learning；进阶：TD的bootstrap与半梯度 | [进入讲解](01-蒙特卡洛TD与动作价值.md#deep-dive-1) |
| [一维导航的表格Q学习](02-一维导航的表格Q学习.md) | 明确环境和终止；训练与评估分开；进阶：行为覆盖与贪心目标的分离 | [进入讲解](02-一维导航的表格Q学习.md#deep-dive-1) |
| [探索策略多步学习与资格迹](03-探索策略多步学习与资格迹.md) | 探索的目标；n步更新；进阶：n步与lambda回报的联系 | [进入讲解](03-探索策略多步学习与资格迹.md#deep-dive-2) |
| [价值学习的评估与失败诊断](04-价值学习的评估与失败诊断.md) | 训练回报与评估回报；常见实现问题；进阶：回报曲线的选择偏差与行为审计 | [进入讲解](04-价值学习的评估与失败诊断.md#deep-dive-2) |

## 如何完成本主题

完成各章后，先独立作答[综合练习：Q 值增大与策略改善分开判断](04-价值学习的评估与失败诊断.md#sec-9-1)，再对照逐步解析与验收要求。

读完一章后，先不看答案复述定义、假设与计算过程，再完成正文实验和练习。代码章节要能解释每个轴、变量和关键步骤；理论章节要能手算一个例子，并指出结论在哪些条件下成立。遇到不熟悉的先修概念，返回相关主题补学。

## 与其他主题的联系

- [策略梯度与Actor-Critic](../../ReinforcementLearning/PolicyBasedMethods/README.md)
- [深度强化学习](../../ReinforcementLearning/DeepRL/README.md)

## 参考资料

- [Spinning Up：强化学习基本概念](https://spinningup.openai.com/en/latest/spinningup/rl_intro.html)
- [Gymnasium：时间限制处理](https://gymnasium.farama.org/tutorials/gymnasium_basics/handling_time_limits/)

[分类目录](../README.md) · [总目录](../../README.md)
