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
| None |   88.94   |   88.08   |   78.50   |  89.84 |
| MMC  |    -      |    -      |    -      |   -    |
| LMNN |   90.48   |   89.49   |   76.22   |  90.59 |
| NCA  |    -      |    -      |    -      |   -    |
| LFDA |   84.60   |   64.49   |   89.99   |  89.74 |
| MLKR |    -      |    -      |    -      |   -    |
| ITML |    -      |    -      |    -      |   -    |
| LSML |    79.87  |     9.02  |   19.98   |  85.87 |
| SDML |     -     |    -      |    -      |   -    |
| RCA  |           |           |           |        |

- None（distance=euclidean，neighbors=50）结果为86.45，neighbors可以考虑先用gridsearch，针对每种距离选取一个最好的neighbors的取值，然后所有的度量学习方法在过KNN的时候都使用这个值，如果有时间的话再做它对acc的影响的实验

### Results: Li Dongyue

#### None

| Neighbors_Num |     euclidean      |     manhattan      |     chebyshev      |       cosine       |
| :-----------: | :----------------: | :----------------: | :----------------: | :----------------: |
|       1       | 87.59              | 87.44              | 75.97              | 88.31              |
|       3       | 88.37              | 87.87              | 77.02              | 89.17              |
|       5       | 88.94              | 88.08              | 78.50              | 89.84              |
|       8       | 88.84              | 87.85              | 78.56              | 90.19              |
|      10       | 88.85              | 87.63              | 78.45              | 90.24              |
|      15       | 88.53              | 86.97              | 78.36              | 90.07              |
|      20       | 87.96              | 86.42              | 77.97              | 89.78              |
|      30       | 87.36              | 85.76              | 77.01              | 89.54              |
|      40       | 86.90              | 84.91              | 76.10              | 89.16              |
|      50       | 86.45              | 84.30              | 75.08              | 89.00              |
|      100      | 84.47              | 81.84              | 72.29              | 87.62              |

#### PCA+KNN
| Neighbors_Num |     euclidean      |     manhattan      |     chebyshev      |       cosine       |
| :-----------: | :----------------: | :----------------: | :----------------: | :----------------: |
|       1       |                    |                    | 84.53              |                    |
|       3       |                    |                    | 85.92              |                    |
|       5       |                    |                    | 86.99              |                    |
|       8       |                    |                    | 87.40              |                    |
|      10       |                    |                    | 87.34              |                    |
|      15       |                    |                    | 87.19              |                    |
|      20       |                    |                    | 87.05              |                    |
|      30       |                    |                    | 86.60              |                    |
|      40       |                    |                    | 86.04              |                    |
|      50       |                    |                    | 85.62              |                    |
|      100      |                    |                    | 83.91              |                    |

#### LMNN试验结果

| Neighbors_Num |     euclidean      |     manhattan      |     chebyshev      |       cosine       |
| :-----------: | :----------------: | :----------------: | :----------------: | :----------------: |
|       1       | 88.76              | 87.78              | 74.19              | 88.61              |
|       3       | 89.52              | 88.74              | 74.81              | 89.95              |
|       5       | 90.48              | 89.49              | 76.22              | 90.59              |
|       8       | 90.60              | 89.36              | 76.83              | 90.91              |
|      10       | 90.52              | 89.60              | 76.79              | 91.00              |
|      15       | 90.66              | 89.38              | 76.61              | 91.06              |
|      20       | 90.37              | 88.98              | 76.10              | 90.96              |
|      30       | 89.91              | 88.54              | 75.42              | 90.71              |
|      40       | 89.57              | 87.93              | 74.55              | 90.61              |
|      50       | 89.20              | 87.47              | 73.95              | 90.27              |
|      100      | 87.71              | 85.87              | 71.40              | 89.61              |

#### LDFA

| Neighbors_Num | euclidean | manhattan | chebyshev | cosine |
| :-----------: | :-------: | :-------: | :-------: | :----: |
|       1       |   84.95   |   67.64   |   87.74   | 88.92  |
|       3       |   84.94   |   65.61   |   89.22   | 89.33  |
|       5       |   85.16   |   63.87   |   89.87   | 89.71  |
|       8       |   85.18   |   62.24   |   90.22   | 89.20  |
|      10       |   84.99   |   61.40   |   90.15   | 89.08  |
|      15       |   84.52   |   59.98   |   90.29   | 88.86  |
|      20       |   84.34   |   58.59   |   90.24   | 88.64  |
|      30       |   83.88   |   56.32   |   90.12   | 88.25  |
|      40       |   83.52   |   54.97   |   90.07   | 87.72  |
|      50       |   83.29   |   53.78   |   89.83   | 87.32  |
|      100      |   81.70   |   50.03   |   89.58   | 85.88  |
