# 多任务学习
1. Asymmetric Multi-task Learning Based on Task Relatedness and Loss

动机：*当一个任务简单，一个任务比较难时，如果把知识从难的任务向简单的任务迁移就会造成负迁移的现象。*

存在问题：*一个任务的实现效果好（文章提到的损失小、更简单）并不一定会在迁移学习中使目标任务取得更好的学习效果*

2. Federated Multi-Task Learning

方法：*把每个节点作为一个任务，在每个节点上单独训练出一个模型，在云端对这些模型进行模型融合，得到一个单独的全局的模型*

3. Federated Learning with Non-IID Data

方法：*提出了一种数据共享策略，通过分发少量包含每个类实例的全局共享数据来改进非IID数据*

# 域自适应
1. Domain Adaptation via Transfer Component Analysis

方法：*本文的策略是假设边缘分布不同，即P!=Q，学习一个映射函数φ，使得边缘分布P(φ(Xs))≈P(φ(Xt))和条件分布P(Ys |φ(Xs))≈P(Yt|φ(Xt))；然后，利用标准监督学习方法应用标签Ys和映射源域数据φ(Xs)训练源域模型，并将其用于目标域映射后的数据φ(Xt)建立目标域模型。*

2. Boosting for transfer learning

方法：*这种算法通过量化源域和目标域之间数据分布的差异计算得到权重。对源域样本加权，减少源域中与目标域分布相差较大部分数据对学习过程的影响*

3. Subspace Alignment for Domain Adaptation

方法:*通过PCA方法提取出源域和目标域数据的主要特征，构造映射矩阵，将源域和目标域的数据映射到低维子空间中，减小源域和目标域数据分布的距离*

4. Sampling Methods for Random Subspace Domain Adaptation

方法：*通过贪婪算法选择源域数据，使得源域数据分布与目标域数据分布之间的距离最小。（每进行一次选择计算一次距离，如果距离增加则放弃本次选择的数据，如果距离减小则保留本次选择的数据）*

# 强化迁移
1. Importance Weighted Transfer of Samples in Reinforcement Learning

方法：*在这个方法中，所有选择出的源域样本都被一个批处理的强化学习算法（FQI）使用，以解决目标任务，但它们对学习过程的贡献与其重要性权重成正比。*

# 加入差分隐私
1. Model-Protected Multi-Task Learning

方法：*每个任务分别用自己的数据和标签训练出一个模型，我们假设有一个可信的共享信息收集者收集这些模型的信息。在这个总的模型参数矩阵上加入噪声，用低秩法和组稀疏法就可以从加噪后的总参数矩阵上提取出共享信息用于各个模型参数的更新。*

2. Differential-Private Data Publishing Through Component Analysis

方法：*本文提出一种方法，通过PCA提取出数据的主要特征，在主要特征中加入噪声。基于加入噪声的的主要特征生成数据并发布，从而增加数据的效用并保护数据隐私*

3. Wishart Mechanism for Differentially Private Principal Components Analysis

方法：*本文提出一种基于差分隐私的主成分分析方法（Wishart mechanism）:通过在原始数据的协方差矩阵中加入满足wishart分布的噪声提高数据的效用*

4. A Near-Optimal Algorithm for Differentially-Private Principal Components

方法：*这篇文章跟上篇的区别是上一个是在PCA的过程中加噪，这篇文章是在PCA后对提取出的主要特征加噪，相比之下上一篇的效用好一些*
