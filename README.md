# Project_2-Distance-Metrics
- 处理数据集
- KNN 分类：Deep Learning Feature
- 尝试不同的距离的度量
  - 切比雪夫距离
  - 欧氏距离
  - 曼哈顿距离
  - 余弦距离
- 至少用一种metric learning的方法，来提高KNN的结果
- 写报告
  - 实验越多越充分
  - 注意参考文献和引用

# 参数说明：
- 需安装包metric_learn
- mltype：选择的metric learn
  - None: 不使用任何metric learn
  - MMC: Mahalanobis Metric for Clustering 
  - LMNN: Large Margin Nearest Neighbor
  - NCA: Neighborhood Components Analysis
  - LFDA: Local Fisher Discriminant Analysis
  - MLKR: Metric Learning for Kernel Regression
  - ITML: Information Theoretic Metric Learning
  - LSML: Least Squares Metric Learning
  - SDML: Sparse Determinant Metric Learning
  - RCA: Relative Components Analysis
- distance：KNN使用的距离的类型
  - euclidean
  - manhattan
  - chebyshev
  - cosine
- neighbors：KNN中的K

# 任务分配
|姓名|任务|
|-|-|
|李东岳| None, MMC, LMNN |
|李杰宇| NCA, LFDA, MLKR |
|王皓轩| ITML, report    |
|陈鸿滨| LSML, SDML, RCA |

- 代码可能会有问题，不过应该都只是API上调用的问题，大家看文档改一下就可以了，有的可能要用带_Supervised()的那个函数
- 有的算法会有爆栈的可能
- 对每个人负责的算法，那几个参数可以用gridsearch来调，结果尽量高过None
- 尽量在这周之内弄完

# 实验结果

|      | euclidean | manhattan | chebyshev | cosine |
|-|-|-|-|-|
| None |           |           |           |        |
| MMC  |           |           |           |        |
| LMNN |           |           |           |        |
| NCA  |           |           |           |        |
| LFDA |           |           |           |        |
| MLKR |           |           |           |        |
| ITML |           |           |           |        |
| LSML |           |           |           |        |
| SDML |           |           |           |        |
| RCA  |           |           |           |        |
