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
- 需安装包metric_learn，API地址：http://metric-learn.github.io/metric-learn/metric_learn.rca.html
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

- None（distance=euclidean，neighbors=50）结果为86.45，neighbors可以考虑先用gridsearch，针对每种距离选取一个最好的neighbors的取值，然后所有的度量学习方法在过KNN的时候都使用这个值，如果有时间的话再做它对acc的影响的实验

###Results: Li Dongyue

####None

| Neighbors_Num |     euclidean      |     manhattan      |     chebyshev      |       cosine       |
| :-----------: | :----------------: | :----------------: | :----------------: | :----------------: |
|      10       | 0.8884875242491137 | 0.8763127968425982 | 0.7844671884406984 | 0.9024014984279884 |
|      20       | 0.8795906080674293 | 0.8642049635427119 | 0.7796508127633955 | 0.8977858050705733 |
|       5       | 0.8893571476352933 | 0.8807947019867549 | 0.785002341293732  | 0.8983878520302362 |
|       8       | 0.8884206301424844 | 0.8785203023613619 |                    |                    |
|      15       | 0.8852766071309117 |                    |                    |                    |
|       3       | 0.8836711485718108 |                    |                    |                    |
|       1       | 0.875911432202823  |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
|               |                    |                    |                    |                    |
