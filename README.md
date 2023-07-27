## 一. 项目简介
      开发者的个人情感会影响工作效率，以及整个团队的生产力，创造力，和谐程度和工作满意度。通过对开源评论的情感分析可以得到开发者对项目的看法和评价，有利于项目健康的发展，达到提高开发人员工作效率的目的。开源项目情感演化大屏通过获取开发者对开源项目的issue/PR评论对其进行情感分析，从时空的维度呈现出该项目的讨论热度和情感演化趋势。该大屏包含项目搜索模块、可视化情感指标筛选模块、时间轴模块、地图可视化模块以及情感分析可视化模块，其主要页面布局如下图所示（设计图仅供参考，以最终项目研发结果为准）：
![image](https://raw.githubusercontent.com/OS-HUBU/DeveloperEmotions/main/img/image.png)
图1 主要页面布局参考图

## 二. 主要功能
### 1. 项目搜索模块
    本模块通过输入项目关键字（如paddle、tensorflow），获取项目的分析结果并在地图上进行展示（如图2所示）。
  a. 关键词匹配项目列表。根据用户输入的内容加载出关键词匹配的项目列表。
  b. 项目列表。列表具体展示关键词相关的项目名称、时间范围和空间范围。
  c. 选择项目。选择列表中的某个项目后，地图部分、时间轴和热力图加载对应的数据。
![image1](https://raw.githubusercontent.com/OS-HUBU/DeveloperEmotions/main/img/image1.png)
图2 搜索模块

### 2. 可视化情感指标筛选模块
    用户可以选择自己感兴趣的情感指标，地图部分可以加载该指标对应的数据。
  a. 情感指标包含正面情感、负面情感、讨论热度，默认加载全时空范围内的所有数据
  b. 情感指标每次只能选中一个
  c. 选定不同的情感指标触发地图控件联动。点击不同标签，地图根据指标数据加载相应的热力图。
![image2](https://raw.githubusercontent.com/OS-HUBU/DeveloperEmotions/main/img/image2.png)
图3 情感指标选择

### 3. 时间轴模块
    通过操作时间轴与情感热力图进行联动，如图4，用户可以点击播放按钮，地图部分可以自动呈现出某项目在一段时间内热力图的变化趋势，同时可以根据自身的喜好选择不同的时间标签和播放速度。
  a. 时间轴由时间刻度、周/月累计、周/月新增、播放/暂停按钮、播放速度组成。
  b. 周/月切换。若选择周，则时间轴的节点表示某周，若选择月，则节点表示某月
  c. 播放按钮选中时，地图控件动态展示当前时间范围内的情感变化；暂停时，滑块停留位置展现年月日；再次播放时，从当前滑块停留位置开始播放；如未暂停，自动播放到时间末尾。播放状态下不能对地图进行点击操作
  d. 模块1无搜索内容时，时间轴范围起始时间为2022-01-01，终止时间为2020-12-31，时间轴固定为12个月。
![image3](https://raw.githubusercontent.com/OS-HUBU/DeveloperEmotions/main/img/image3.png)
图4 时间轴

### 4. 地图可视化模块
    用户可以自由的放大缩小拖动地图，点击某个地区可以展示详细信息。
  a. 鼠标移到某一国家，弹出浮动小气泡，展示该地区总体评论数量，正面评论数量和负面评论数量。
  b. 热力程度图例设计。不同的情感指标具有不同的热力程度图例。
  c. 点击某地区时，情感分析可视化模块从右边弹出
![image4](https://raw.githubusercontent.com/OS-HUBU/DeveloperEmotions/main/img/image4.png)
图5 地图可视化模块

### 5. 情感分析可视化模块
     在当前项目数据加载情况下，根据选定的时间点，地理位置，加载相应的情感分析数据，该模块主要显示以下内容。
  a. 基本信息：地区名称，该地区经纬度，时间。
  b. 走势图：为折线图，分别为热度趋势图，正面情感趋势图，负面情感趋势图。
  c. 情感分析图：展示该地区在某个时间范围内的正面、负面情感比例。
![image.png](https://raw.githubusercontent.com/OS-HUBU/DeveloperEmotions/main/img/1683011640264-f0d16328-4f10-43d2-9915-acb84942f055.png)
图6 情感分析可视化模块

## 三. 核心数据

- 2022年Github的issue和PR评论数据（已获取)
- 开发者个人的地理位置信息，主要通过个人profile填写的位置反解析出所在的国家。（进行中）
## 四. 参考资料
[1] Rishi D. Affective sentiment and emotional analysis of pull request comments on github[D]. University of Waterloo, 2017.
[2] Kaur R, Chahal K K, Saini M. Analysis of Factors Influencing Developers' Sentiments in Commit Logs: Insights from Applying Sentiment Analysis[J]. e-Informatica Software Engineering Journal, 2022, 16(1): 220102.

- [ ] [3] Yang Z, Du X, Rush A M, et al. Improving Event Duration Prediction via Time-aware Pre-training[C]//Findings of the Association for Computational Linguistics: EMNLP 2020. 2020: 3370-3378.

[4] Huq S F, Sadiq A Z, Sakib K. Is developer sentiment related to software bugs: An exploratory study on github commits[C]//2020 IEEE 27th International Conference on Software Analysis, Evolution and Reengineering (SANER). IEEE, 2020: 527-531.
