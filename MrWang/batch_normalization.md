# covarite shift
- $P_s(Y|X=x)=p_t(Y|X=x) \quad P_s(X)!=P_t(X)$
- 当存在训练样本没法找到X和Y之间正确关系的$\theta$，$P_s(Y|X=x)$完全取决于$P_s(X)$,因此当训练样本和测试样本的X的分布不同的时候，就会出现covarite shift问题，也就是在训练样本中的最优，并不是测试样本中的最优的
- BN能够跳过sigmod中饱和区，并在非饱和区(容易理解)
- 能够起到dropout的功能，归一化有些节点为0，从而就实现了dropout的效果
