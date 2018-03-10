##目的
将图片中选择出proposal region 用于之后的训练

##selective search步骤
1. 使用的是Hierarchical Group（分层思想）
2. 不同的策略：
	- color空间选择的策略(GRB、HSV)
	- 不同的合并策略：颜色、纹理、大小、共有部分
	- 变化合并开始区域
3. 合并位置

##using selective search to recognize object

SVM作为分类器来训练，为了检测到带有正样本的图片
- 正样本是overlap with positive 20%-50%的region(离positive最近的negative sample归纳到positive中，使得decision boundary更好的确定)
- 负样本是严格negative region
