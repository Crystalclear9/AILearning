# AI 学习资料总目录

本资料按 **8 个分类、47 个主题、186 个章节**组织，覆盖数学、编程、计算机基础、机器学习、深度学习、应用方向、强化学习与独立进阶专题。章节包含概念、算例与实现、进阶分析、练习解析；当前同时保留已重写的长篇教材章与尚待重写的短讲义。

初学者按[基础学习路线](学习路线.md#basic)建立完整知识链；已有基础可按[进阶学习路线](学习路线.md#advanced)重点阅读证明条件、方法比较和研究练习。

## 开始学习

- [学习路线与阶段验收](学习路线.md)：按先修关系安排学习，选择视觉、语言、生成或强化学习方向。
- [内容范围与掌握标准](内容范围与掌握标准.md)：了解原有主题的学习边界、逐主题验收及进阶衔接。
- [运行环境](运行环境.md)：区分完整 Python 示例、SQL 与特定 shell 命令，配置可复现环境。
- [术语与符号](术语与符号.md)：查阅跨主题数学符号和容易混淆的概念。

## 分类目录

| 分类 | 主题数 | 章节数 |
| --- | ---: | ---: |
| [编程基础](Programming/README.md) | 5 | 22 |
| [数学基础](Mathematics/README.md) | 8 | 32 |
| [计算机基础](ComputerScience/README.md) | 5 | 21 |
| [机器学习](MachineLearning/README.md) | 6 | 26 |
| [深度学习](DeepLearning/README.md) | 6 | 25 |
| [应用与研究方向](AI-Domains/README.md) | 6 | 26 |
| [强化学习](ReinforcementLearning/README.md) | 4 | 16 |
| [进阶理论与研究专题](AdvancedStudies/README.md) | 7 | 18 |

## 进阶扩展

完成相关先修后，可进入[新增进阶篇](AdvancedStudies/README.md)：学习理论、因果推断、贝叶斯计算、自监督表示、连续生成与流匹配、高效模型系统、不确定性与分布鲁棒性。各主题用两到四章深入一个问题链，包含推导、比较、算例和研究练习；顺序见[进阶分支路线](学习路线.md#advanced-topics)。

<a id="textbook-status"></a>

## 长篇教材章节与当前覆盖

长篇标准为**每章纯正文约 12000–20000 汉字**，统计剔除标题、目录、导航、代码和参考链接。长度是最低展开要求，同时要求具体概念讲清、关键推导可重建、例题有全过程、方法比较交代条件、练习附详细解析。

**目前 88 章达到该篇幅，纯正文合计约 111.8 万汉字；其中 84 章重写、4 章新增。其余 98 章仍是原有短讲义，尚未达到这次要求，整套长篇重写未完成。** Python、NumPy、Pandas、Matplotlib、PyTorch、微积分、线性代数、概率论、统计学、优化方法、数值计算、矩阵微积分、信息论、数据结构与算法、计算机系统基础、Git、Linux、数据库、机器学习基础、监督学习、统计学习理论二十一个主题的现有章节均已达到长篇标准。编程分类现有 22 章、数学分类现有 32 章、计算机基础分类现有 21 章已全部达到长篇标准。文件数量与总目录不代表所有章节具有同等深度。

| 主题 | 已达到长篇标准的章节 | 重点展开 |
| --- | --- | --- |
| [Python 编程基础](Programming/Python/README.md) | [01 变量容器与控制流程](Programming/Python/01-变量容器与控制流程.md)、[02 函数、类与迭代器](Programming/Python/02-函数类与迭代器.md)、[03 文件、异常、环境与脚本组织](Programming/Python/03-文件异常环境与脚本组织.md)、[04 模块、包、数据类与配置管理](Programming/Python/04-模块包数据类与配置管理.md)、[05 调试、测试与可复现小项目](Programming/Python/05-调试测试与可复现小项目.md)、[06 对象协议、类型约束与执行模型](Programming/Python/06-对象协议类型约束与执行模型.md) | 对象与所有权、函数与流式统计、文件恢复、配置模式、调试与完整项目、协议和执行机制 |
| [NumPy 数值数组](Programming/NumPy/README.md) | [01 数组形状、索引与广播](Programming/NumPy/01-数组形状索引与广播.md)、[02 向量化、线性代数与可复现实验](Programming/NumPy/02-向量化线性代数与可复现实验.md)、[03 高级索引、批量运算与内存布局](Programming/NumPy/03-高级索引批量运算与内存布局.md)、[04 用 NumPy 实现线性回归训练](Programming/NumPy/04-用NumPy实现线性回归训练.md) | 轴与广播、索引映射、数值误差、向量化、批量运算、内存布局与复现实验 |
| [Pandas 表格处理](Programming/Pandas/README.md) | [01 数据表索引缺失与清洗](Programming/Pandas/01-数据表索引缺失与清洗.md)、[02 分组连接与防止数据泄漏](Programming/Pandas/02-分组连接与防止数据泄漏.md)、[03 时间序列窗口与数据质量检查](Programming/Pandas/03-时间序列窗口与数据质量检查.md)、[04 从原始表到训练样本的完整流程](Programming/Pandas/04-从原始表到训练样本的完整流程.md) | 表语义与清洗契约、分组和连接、双时间窗口与版本重放、成熟标签和训练服务一致性 |
| [Matplotlib 可视化](Programming/Matplotlib/README.md) | [01 图形对象坐标与常用图表](Programming/Matplotlib/01-图形对象坐标与常用图表.md)、[02 训练诊断分布比较与导出](Programming/Matplotlib/02-训练诊断分布比较与导出.md)、[03 多子图误差条与统计表达](Programming/Matplotlib/03-多子图误差条与统计表达.md)、[04 构建模型诊断图与图表交付](Programming/Matplotlib/04-构建模型诊断图与图表交付.md) | 图形对象和坐标、训练及分布比较、配对区间与层级单位、可追溯诊断和图表交付 |
| [PyTorch 深度学习编程](Programming/PyTorch/README.md) | [01 张量自动求导与模型接口](Programming/PyTorch/01-张量自动求导与模型接口.md)、[02 完整训练验证与保存](Programming/PyTorch/02-完整训练验证与保存.md)、[03 数据集设备与高效训练](Programming/PyTorch/03-数据集设备与高效训练.md)、[04 检查点恢复与训练代码组织](Programming/PyTorch/04-检查点恢复与训练代码组织.md) | 存储与求导、归约和训练协议、数据与设备性能、状态完整性及恢复对照 |
| [微积分](Mathematics/Calculus/README.md) | [01 导数、偏导数与链式法则](Mathematics/Calculus/01-导数偏导数与链式法则.md)、[02 积分、泰勒展开与曲率](Mathematics/Calculus/02-积分泰勒展开与曲率.md)、[03 多元微分、隐函数与解的敏感性](Mathematics/Calculus/03-多元微分与隐函数.md)、[04 从导数到训练目标的推导实践](Mathematics/Calculus/04-从导数到训练目标的推导实践.md) | 可微与计算图、积分和余项、曲率与步长、隐函数与伴随、目标归约和完整训练实验 |
| [线性代数](Mathematics/LinearAlgebra/README.md) | [01 向量矩阵与线性变换](Mathematics/LinearAlgebra/01-向量矩阵与线性变换.md)、[02 投影、最小二乘与矩阵分解](Mathematics/LinearAlgebra/02-投影最小二乘与矩阵分解.md)、[03 线性方程组与稳定求解](Mathematics/LinearAlgebra/03-线性方程组与稳定求解.md)、[04 从协方差到 PCA 的完整实践](Mathematics/LinearAlgebra/04-从协方差到PCA的完整实践.md) | 基与子空间、投影与 QR/SVD、稳定求解与误差证书、协方差与 PCA 完整实践 |
| [概率论](Mathematics/Probability/README.md) | [01 条件概率与贝叶斯推断](Mathematics/Probability/01-条件概率与贝叶斯推断.md)、[02 随机变量期望与常见分布](Mathematics/Probability/02-随机变量期望与常见分布.md)、[03 联合分布边缘化与条件期望](Mathematics/Probability/03-联合分布边缘化与条件期望.md)、[04 采样大数定律与蒙特卡洛推断](Mathematics/Probability/04-采样大数定律与蒙特卡洛推断.md) | 条件化与贝叶斯、分布与矩、联合和条件期望、采样极限定理与蒙特卡洛估计 |
| [统计学](Mathematics/Statistics/README.md) | [01 参数估计与置信区间](Mathematics/Statistics/01-参数估计与置信区间.md)、[02 假设检验相关性与实验](Mathematics/Statistics/02-假设检验相关性与实验.md)、[03 线性回归的统计解释](Mathematics/Statistics/03-线性回归的统计解释.md)、[04 重采样实验设计与报告实践](Mathematics/Statistics/04-重采样实验设计与报告实践.md) | 估计与覆盖、检验与实验设计、回归推断及稳健方差、重采样单位和完整报告 |
| [优化方法](Mathematics/Optimization/README.md) | [01 目标函数、梯度下降与约束](Mathematics/Optimization/01-目标函数梯度下降与约束.md)、[02 动量自适应方法与训练诊断](Mathematics/Optimization/02-动量自适应方法与训练诊断.md)、[03 凸性二阶方法与约束优化](Mathematics/Optimization/03-凸性二阶方法与约束优化.md)、[04 优化实验记录与故障定位](Mathematics/Optimization/04-优化实验记录与故障定位.md) | 下降与随机梯度、动量与自适应状态、二阶约束与对偶、实验诊断和公平成本 |
| [数值计算](Mathematics/NumericalMethods/README.md) | [01 浮点误差、条件数与稳定计算](Mathematics/NumericalMethods/01-浮点误差条件数与稳定计算.md)、[02 数值求导、积分与蒙特卡洛](Mathematics/NumericalMethods/02-数值求导积分与蒙特卡洛.md)、[03 线性系统条件数与病态问题](Mathematics/NumericalMethods/03-线性系统条件数与病态问题.md)、[04 根查找数值积分与停止准则](Mathematics/NumericalMethods/04-根查找数值积分与停止准则.md) | 浮点与误差模型、差分和积分、反问题谱滤波与参数选择、可靠求根与停止证据 |
| [矩阵微积分](Mathematics/MatrixCalculus/README.md) | [01 梯度雅可比与形状约定](Mathematics/MatrixCalculus/01-梯度雅可比与形状约定.md)、[02 批量损失与反向传播推导](Mathematics/MatrixCalculus/02-批量损失与反向传播推导.md)、[03 Softmax交叉熵与归一化求导](Mathematics/MatrixCalculus/03-Softmax交叉熵与归一化求导.md)、[04 从零实现两层网络的梯度检查](Mathematics/MatrixCalculus/04-从零实现两层网络的梯度检查.md) | 微分与伴随、批量归约及共享参数、稳定分类和归一化、全参数梯度与二阶检查 |
| [信息论](Mathematics/InformationTheory/README.md) | [01 信息量熵与编码直觉](Mathematics/InformationTheory/01-信息量熵与编码直觉.md)、[02 交叉熵KL散度与分类训练](Mathematics/InformationTheory/02-交叉熵KL散度与分类训练.md)、[03 最大似然交叉熵与困惑度](Mathematics/InformationTheory/03-最大似然交叉熵与困惑度.md)、[04 互信息特征选择与估计限制](Mathematics/InformationTheory/04-互信息特征选择与估计限制.md) | 熵与编码、KL与分类评分、序列似然和困惑度、互信息估计与无泄漏特征选择 |
| [数据结构与算法](ComputerScience/DataStructuresAndAlgorithms/README.md) | [01 复杂度与基础数据结构](ComputerScience/DataStructuresAndAlgorithms/01-复杂度与基础数据结构.md)、[02 二分排序与图遍历](ComputerScience/DataStructuresAndAlgorithms/02-二分排序与图遍历.md)、[03 递归动态规划与最优子结构](ComputerScience/DataStructuresAndAlgorithms/03-递归动态规划与最优子结构.md)、[04 堆近邻与大数据处理策略](ComputerScience/DataStructuresAndAlgorithms/04-堆近邻与大数据处理策略.md) | 计算模型与摊还、二分排序及图证明、状态充分性和近似动态规划、可合并Top-k与近邻外存策略 |
| [计算机系统基础](ComputerScience/ComputerSystems/README.md) | [01 程序执行内存与存储](ComputerScience/ComputerSystems/01-程序执行内存与存储.md)、[02 进程线程并发与性能分析](ComputerScience/ComputerSystems/02-进程线程并发与性能分析.md)、[03 I/O 缓存与数据加载流水线](ComputerScience/ComputerSystems/03-I_O缓存与数据加载流水线.md)、[04 GPU 并行、显存与分布式系统](ComputerScience/ComputerSystems/04-GPU并行显存与分布式入门.md)、[05 性能建模、基准实验与瓶颈推断](ComputerScience/ComputerSystems/05-性能建模基准实验与瓶颈推断.md) | 执行与虚拟内存、同步与并发、缓存背压和I/O流水线、GPU资源与归约、性能建模和受控实验 |
| [Git 版本管理](ComputerScience/Git/README.md) | [01 工作区暂存区与提交](ComputerScience/Git/01-工作区暂存区与提交.md)、[02 分支合并冲突与实验复现](ComputerScience/Git/02-分支合并冲突与实验复现.md)、[03 检查历史定位问题与安全撤销](ComputerScience/Git/03-检查历史定位问题与安全撤销.md)、[04 协作分支与实验版本规范](ComputerScience/Git/04-协作分支与实验版本规范.md) | 索引与对象图、合并语义、历史定位与撤销、引用同步及实验交付 |
| [Linux 与命令行](ComputerScience/Linux/README.md) | [01 路径文件管道与权限](ComputerScience/Linux/01-路径文件管道与权限.md)、[02 进程日志远程与环境管理](ComputerScience/Linux/02-进程日志远程与环境管理.md)、[03 Shell脚本参数与作业管理](ComputerScience/Linux/03-Shell脚本参数与作业管理.md)、[04 服务器实验的监控与故障排查](ComputerScience/Linux/04-服务器实验的监控与故障排查.md) | 路径与描述符、进程信号和日志、脚本状态机、资源监控与故障诊断 |
| [数据库与 SQL](ComputerScience/Databases/README.md) | [01 关系模型筛选与聚合](ComputerScience/Databases/01-关系模型筛选与聚合.md)、[02 连接索引事务与特征数据](ComputerScience/Databases/02-连接索引事务与特征数据.md)、[03 窗口函数与时间特征 SQL](ComputerScience/Databases/03-窗口函数与时间特征SQL.md)、[04 索引执行计划与可靠数据提取](ComputerScience/Databases/04-索引执行计划与可靠数据提取.md) | 多重集与缺失、连接和事务、双时间窗口、索引计划及可恢复提取 |
| [机器学习基础](MachineLearning/Foundations/README.md) | [01 学习任务、数据与模型：从问题定义到可检验的学习系统](MachineLearning/Foundations/01-学习任务数据与模型.md)、[02 泛化、偏差方差与完整学习流程](MachineLearning/Foundations/02-泛化偏差方差与学习流程.md)、[03 特征工程、正则化与数据偏差](MachineLearning/Foundations/03-特征工程正则化与数据偏差.md)、[04 从问题定义到上线监测的完整学习流程](MachineLearning/Foundations/04-从问题定义到上线监测的完整流程.md)、[05 决策论、代理损失与统计一致性](MachineLearning/Foundations/05-决策论代理损失与统计一致性.md) | 任务契约、风险分解、特征与偏差、评估部署、代理校准及决策 |
| [监督学习](MachineLearning/SupervisedLearning/README.md) | [01 线性回归与逻辑回归](MachineLearning/SupervisedLearning/01-线性回归与逻辑回归.md)、[02 决策树、随机森林与梯度提升](MachineLearning/SupervisedLearning/02-决策树集成与其他模型.md)、[03 支持向量机、核方法与近邻](MachineLearning/SupervisedLearning/03-支持向量机核方法与近邻.md)、[04 集成学习、调参与可解释性](MachineLearning/SupervisedLearning/04-集成学习调参与可解释性.md) | 回归与逻辑模型、树与集成、SVM 对偶与核、近邻、调参与解释的适用条件 |
| [统计学习理论](AdvancedStudies/LearningTheory/README.md) | [01 总体风险、一致收敛与模型选择](AdvancedStudies/LearningTheory/01-总体风险一致收敛与模型选择.md)、[02 算法稳定性、插值与隐式偏置](AdvancedStudies/LearningTheory/02-算法稳定性插值与隐式偏置.md)、[03 PAC-Bayes、变分界与随机预测器](AdvancedStudies/LearningTheory/03-PACBayes变分界与随机预测器.md)、[04 局部复杂度、快速率与数据依赖泛化](AdvancedStudies/LearningTheory/04-局部复杂度快速率与数据依赖泛化.md) | 一致收敛、算法稳定性、隐式偏置、PAC-Bayes、有限类快速率与局部化 |

新章接在对应主题后续位置。学习理论先掌握第 01 章集中与风险，再学习稳定性、PAC-Bayes和快速率；Python对象协议放在函数、类与异常基础之后；监督学习的回归与分类章可与评估主题交叉阅读。以先修关系安排阅读，不按篇幅挑选互不连贯的章节。

## 如何阅读

章节表中的“深入讲解入口”可以直接进入对应机制或推导。长篇章会连续展开概念、证明、完整例题、方法比较与分层题解；短讲义仍只提供较紧凑的知识链，篇幅状态见上方[长篇教材覆盖表](#textbook-status)。建议先独立复算，再对照解析，不把看过公式当成已经掌握。

每个主题先看 README 中的先修知识与阅读路径，再进入章节。分类按知识归属组织，文件夹排列不代表必须逐类学完；PyTorch 与神经网络基础可并行，视觉、语言、生成、图、多模态和强化学习按目标选择。

| 阅读层次 | 需要解决的问题 | 建议做法 |
| --- | --- | --- |
| 概念与原理 | 对象是什么，输入输出和符号表示什么 | 先读定义，确认先修知识、轴含义与问题目标 |
| 对应算例与机制 | 结论如何落实为计算，步骤为何这样安排 | 在相关概念之后复算例子，追踪状态、形状与归约 |
| 进阶推导 | 结论在什么条件下成立，方法有何取舍 | 补中间步骤，区分数学性质、实现行为与实验结果 |
| 基础练习与边界追问 | 能否独立应用，改变条件后是否仍成立 | 先作答，再用推导或反例核对解析 |
| 研究与综合练习 | 能否连接多章并设计有效验证 | 按主题或支线验收，固定数据、预算和选择规则 |

初学者先走[基础学习路线](学习路线.md#basic)，进阶推导可以在基础闭环完成后返回；已有基础可从[进阶路线](学习路线.md#advanced)和章内目录进入。基础算例随对应知识安排，练习由应用走向条件判断，再进入研究与综合任务。

代码帮助验证机制，不能替代原理。运行前先说明期望性质，运行后解释输入、输出和关键中间量；前向一致、梯度一致、训练稳定和独立效果改善是不同层次的证据。

## 排版与示例约定

文件统一使用 UTF-8；公式使用 `$...$`、`$$...$$` 数学标记，建议用支持 LaTeX 的 Markdown 阅读器。章节内目录采用显式锚点，文件之间采用相对路径，移动资料时请整体保留目录结构。

Python 完整示例带必要导入与人工或内置数据；SQL、Git、Linux 命令有环境前提，不能在任意终端直接混用。涉及梯度、划分、归约与概率时，按所在章节定义理解符号与系数；环境要求见[运行环境](运行环境.md)。

每个主题保留作者教材、原始论文或官方文档入口。讲义覆盖各主题的核心学习链条；继续深入特定研究问题时，可据参考资料查阅完整理论、实现细节与版本说明。
