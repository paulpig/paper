#知识图谱
- 实体链接（将文档中的实体名字链接到知识库中），涉及到实体识别和实体消除
- 关系抽取：词性标注、语法分析、依存关系树等


#问答系统主流方法
- 将问题解析成一个特征树，并且根据关系提出相应的特征 （实际上就是信息抽取）
- 根据topic node从知识图谱中提取只有一跳或者两跳的子图（如何确定这个topic node(如何将justin Bieber这个此获取出来？？**命名实体识别**)），qverb可以通过词性标注来获取
- 如何将freebase中的映射到答案中，有些答案就直接是重叠的，有些答案在图谱中不能直接找到的哈
- 如何将图谱中的关系和自然语言关联起来，通过贝叶斯概率来关联


#问题和解决方式
- 当查询的语法是不符合知识库中的语法的时候，如果没有调整，那么在知识库的一两个节点中是不能寻找到的。
	- 解决方法：通过从大规模的训练样本中，学习到问题对应的最佳的relation，之后通过选择max P(R|Q)中的R，就能解决上次由于语法错误而找不到对应的关系的。



#实验流程：
1. 从问句中提取关键词（实体识别和抽取）
2. 用关键词在freebase中寻找到对应的节点，提取node feature
3. 判断当前节点是否是对应的主题，是设置为1，不是设置为0，训练样本是二分类
4. 用relation Map添加多余的特征（通过贝叶斯变换来确定和当前问题最相关的relation添加进去）
5. 用上述产生的训练样本来训练模型

#问题：
如何将多个词转化为向量的？