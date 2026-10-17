# 强化学习

本分类共 4 个主题。MDP → 价值方法建立表格决策基础，再进入策略梯度与 Actor-Critic，最后整合深度强化学习。表格方法只需 Python、NumPy 和相关数学；神经网络实现再补 PyTorch。DQN 分支可在价值方法与 PyTorch 后先读，连续控制再衔接策略方法。具体安排见[学习路线](../学习路线.md)。

## 主题与章节

### [马尔可夫决策过程](MDP/README.md)

- [第 1 章 状态动作奖励与回报](MDP/01-状态动作奖励与回报.md)
- [第 2 章 价值函数Bellman方程与规划](MDP/02-价值函数Bellman方程与规划.md)
- [第 3 章 有限状态动态规划完整算例](MDP/03-有限状态动态规划完整算例.md)
- [第 4 章 部分可观测与奖励建模边界](MDP/04-部分可观测与奖励建模边界.md)

### [价值方法](ValueBasedMethods/README.md)

- [第 1 章 蒙特卡洛TD与动作价值](ValueBasedMethods/01-蒙特卡洛TD与动作价值.md)
- [第 2 章 一维导航的表格Q学习](ValueBasedMethods/02-一维导航的表格Q学习.md)
- [第 3 章 探索策略多步学习与资格迹](ValueBasedMethods/03-探索策略多步学习与资格迹.md)
- [第 4 章 价值学习的评估与失败诊断](ValueBasedMethods/04-价值学习的评估与失败诊断.md)

### [策略梯度与Actor-Critic](PolicyBasedMethods/README.md)

- [第 1 章 策略梯度与方差控制](PolicyBasedMethods/01-策略梯度与方差控制.md)
- [第 2 章 Actor-Critic优势与PPO](PolicyBasedMethods/02-Actor-Critic优势与PPO.md)
- [第 3 章 从REINFORCE到GAE的实现细节](PolicyBasedMethods/03-从REINFORCE到GAE的实现细节.md)
- [第 4 章 PPO训练循环与稳定性检查](PolicyBasedMethods/04-PPO训练循环与稳定性检查.md)

### [深度强化学习](DeepRL/README.md)

- [第 1 章 DQN经验回放与目标网络](DeepRL/01-DQN经验回放与目标网络.md)
- [第 2 章 连续控制奖励设计与实验](DeepRL/02-连续控制奖励设计与实验.md)
- [第 3 章 DQN最小训练更新与DoubleDQN](DeepRL/03-DQN最小训练更新与DoubleDQN.md)
- [第 4 章 连续控制离线学习与复现协议](DeepRL/04-连续控制离线学习与复现协议.md)

[返回总目录](../README.md)
