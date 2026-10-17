# 贝叶斯计算与近似推断

连接后验积分、变分优化与 MCMC，明确近似偏差及采样诊断的证据边界。

**先修知识：** 贝叶斯参数估计、KL、梯度与线性代数；第二章需马尔可夫链基本概念。

## 章节与学习目标

| 章节 | 核心内容 | 深入讲解入口 |
| --- | --- | --- |
| [第 1 章 变分推断、ELBO 与近似后验](01-变分推断ELBO与近似后验.md) | 后验与计算目标；ELBO 分解逐步推导；均值场更新与梯度估计 | [进入讲解](01-变分推断ELBO与近似后验.md#deep-dive-2) |
| [第 2 章 MCMC 不变分布、HMC 与收敛诊断](02-MCMC不变分布HMC与收敛诊断.md) | 样本相关与不变分布；Metropolis–Hastings 的接受机制；HMC 如何利用几何 | [进入讲解](02-MCMC不变分布HMC与收敛诊断.md#deep-dive-2) |

## 阅读顺序与验收

先完成第 1 章的定义与基本推导，再读第 2 章的方法扩展。遇到公式先复算低维例子，再进入实验设计；不要把局部数值检查当成算法整体效果证明。

**完成要求：** 独立推导 ELBO；解释均值场相关方向的误差；证明 MH 不变性并区分 ESS、混合与模型检验。

作答后再阅读各章解析。能够独立说明一个失效条件，并设计一个可区分竞争解释的对照实验，才算完成本主题的进阶学习。

## 回看先修知识

- [概率模型](../../MachineLearning/ProbabilisticModels/README.md)
- [信息论](../../Mathematics/InformationTheory/README.md)
- [数值计算](../../Mathematics/NumericalMethods/README.md)

## 参考资料

- [Variational Inference Review](https://arxiv.org/abs/1601.00670)
- [Stan Posterior Analysis](https://mc-stan.org/docs/reference-manual/analysis.html)

[进阶目录](../README.md) · [学习路线](../../学习路线.md#advanced-topics) · [总目录](../../README.md)
