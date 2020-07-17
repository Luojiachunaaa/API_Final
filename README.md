# **安道**APP产品
| 说明 | 安道APP需求文档状态 |
|:------:|:------|
| 产品名称 | 安道 |
| 产品描述 | 一款让有视力障碍人群更有安全感，更加可依赖的导航APP |
| 产品状态 | 进行中 |
| 产品作者 | 罗佳莼 |
| 迭代版本 | 1.0 |
MVP加/价值主张宣言 (6%)
# 一、PRD 价值主张设计
### 1.加值宣言 
针对有视力障碍人群出行困难的问题，我认为市场上现有的地图导航软件对于这个群体而言还不够人性化，「安道」app就是对现有的地图导航软件的整合提升，是一款让有视力障碍人群更有安全感，更加可依赖的导航app。该App使用到的人工智能技术来源于高德开放平台的**POI搜索**技术，以及**路线规划及道路导航**等技术的辅助，这些技术帮助可以让该app结合实时路线中的场景，快速定位用户所在点，并更便捷地得到用户的目的地，帮助用户绕避开存在危险的地区，提供更安全、更人性化的出行导航。
- 高德开放平台POI搜索：搜索服务API是一类简单的HTTP接口，提供多种查询POI信息的能力，其中包括关键字搜索、周边搜索、多边形搜索、ID查询四种筛选机制。
- 百度AI开放平台语音识别API加值：将语音信息转化为文字方便记录，节省文字输入时间
- 高德开放平台路线规划API加值：为不同的视障用户提供最安全最贴心的路线规划
- 高德开放平台道路导航API加值：为不同的视障用户提供最精确的目的地导向
### 2.核心价值 
- 产品核心价值（最小可行性产品）：对于视力障碍的特殊用户群，「安道」app为其提供精确定位、快速查找以及切实可行的、更贴合用户实际需求的目的地地位及路线规划导航。
MVP 1.  项目标题融合了问题情境并提出解决方案，点出加/价值主张宣言。(3: 0,1,2)
MVP 2.  项目简介说明简要说明了问题及解决方案，问题是以人为中心的，且解决方案所使用的人工智能的API融合了人工智能概率性考量。(5:0,1,2,4)
---
## 问题表述与需求列表
问题情境：问题表述与需求列表 (10%)
### 问题表述
### 1. 用户画像
- 先天性失明用户，对于独自生活与出行较有经验，黑暗不会给生活带来太大影响的群体
- 后天性失明用户，不熟悉失明后的黑暗生活，对于出行有较大的困难，但需要逐步适应新生活的群体
- 存在色盲或者色弱问题的群体
 

### 3.核心价值与用户痛点
企图解决的用户痛点：
1. 用户由于视力障碍的原因无法手动打字输入目的地
2. 用户对于地理信息较不敏感，得到详尽确切的目的地较为不便
3. 目的地不准确：导航提示已到达目的地但实际存在小距离差异
4. 普通地图导航往往提供**最近**路线，对于特殊群体而言需要的是**最安全**的路线
5. 语音播报不及时，没有实时路线返回
6. 用户在行进过程中遇到突发事件停止后，无法确定当前所处位置

| 核心价值 | 用户痛点 | API加值 |
|:------:|:------:|:------:|
| 精确的目的地导向 | 目的地不准确 | 高德开放平台POI搜索 |
| 目的地关键词地点推荐 | 对于地理信息较不敏感 | 高德开放平台POI搜索 |
| 语音输入目的地 | 无法手动打字输入目的地 | 百度AI开放平台语音识别API |
| 提供最安全的路线规划 | 得不到最安全的路线 | 高德开放平台路径规划api |
| 实时返回语音提醒 | 语音播报不及时 | 百度AI开放平台语音识别API |
| 准确的定位 | 无法确定当前所处位置 | 百度AI开放平台地标识别api |

### 4.人工智能概率性与用户痛点 
据实践研究表明，高德开放平台提供的导航较其他同类型产品而言精确度更高。

人工智能出错时解决方法：
- 当目的地出现偏差时，提供准确的目的地具体位置语音播报

相关资料阅读：
- [公交导航准确度大PK:高德地图百度地图谁更精确 ](https://www.sohu.com/a/69051624_119779)



问题表述 1.  API驱动之智能产品App的问题情境说明清楚合理，展示了为啥要做 （为什么做？） (3:0,1,2)
问题表述 2.  API驱动之智能产品App的需求说明清楚合理，展示了是谁有需要解决的问题，用户画象明晰 （用户任务）(3: 0,1,2)
问题表述 3.  API驱动之智能产品App的需求列表分项内容清楚合理，展示了关键智能API的智能加值 （需求项有哪些？）(3: 0,1,2)
问题表述 4.  API驱动之智能产品App的需求列表优先级清楚合理，展示了关键智能API对问题情境的相关性(API<—>用户情景)(3: 0,1,2)
问题表述 5.  API驱动之智能产品App的问题情境说明清楚合理，展示了关键智能API类型对解决方案的可能影响论证（解决方案的影响（例如API的种族、可持续、ESG等）） (3: 0,1,2) 
### 需求列表
| 优先级 | 用户痛点 | 用户需求 | 功能实现 | API加值 |
|:------:|:------:|:------:|:------:|:------:|
| 核心 | 目的地不准确 | 精确的目的地导向 | 高德开放平台POI搜索 |
| 重要 | 无法手动打字输入目的地 | 语音输入目的地 |
| 重要 | 得不到最安全的路线 | 提供最安全的路线规划 | 高德开放平台路径规划api |
| 次重要 | 无法确定当前所处位置 | 准确的定位 | 百度AI开放平台地标识别api |
---
## 解决方案原型表述
解决方案：界面流程及关键智能交互 (26%)
# 二、产品原型 
[安道app产品原型 ](https://modao.cc/app/e9ec371bcafd7b93e54074b7a25e8eb090af33d1?simulator_type=device&sticky)
### 1.交互及界面设计 
| 交互及界面设计 | 人工智能加值 |
|:------:|:------|
| 新用户注册 | 用户首次进入产品后需要对自己的信息进行输入与选择，为此我们提供语音识别的人工智能价值方便用户语音输入基本信息 |
| 登录/进入 | 若开启每次都需登录的选项，只需进行简单的人脸识别即可确认使用者信息 |
| 输入目的地 | 考虑到视力障碍人群，特别是全盲用户的使用，安道app提供语音输入识别功能，只需一个简单的单击交互即可唤醒输入框 |
| 选择目的地 | 考虑用户疏于特殊群体，对于地理信息困难较不敏感，此app提供poi搜索，用户只需语音输入简单的关键词，即可根据用户信息及历史记录推荐出可能会前往的目的地供用户选择 |
| 导航过程 | 全场实时的语音导航 |
| 到达目的地 | 地标识别服务方便用户只需进行简单的交互即可知道当前所在位置 |

（交互及界面设计：在PRD文件中是否有说明且原型是否有做到：交互及界面设计的某个核心交互环节使用了人工智能的加值

### 2.信息设计
| 核心信息/设计 | 人工智能加值 |
|:------:|:------|
| 启动页信息 | 提供简单的语音提示，给用户已进入app并开始使用的信息 |
| 登录页信息 | 用人脸识别的方式记录登录使用者的信息，在后续的使用中返回用户曾经的使用信息 |
| 输入目的地信息 | 语音识别到用户输入的目的地信息 |
| 选择目的地信息 | 根据poi搜索推荐用户可能到底的目的地信息 |
| 到达信息 | 实时语音返回用户所在位置及导航信息 |
（信息设计：在PRD文件中是否有说明且原型是否有做到：信息设计的某个核心信息或设计使用了人工智能的加值

### 3.原型文档 
[原型文档](https://modao.cc/app/e9ec371bcafd7b93e54074b7a25e8eb090af33d1?simulator_type=outside_artboard&sticky)
原型文档：多少程度上有提供MVP可交互的原型文档，供它人在Github上下载使用

### 4.口头操作说明 
不同于市场中普通的导航软件，安道app与使用者的交互更为便捷简单，使用户可以以更轻松可靠的操作进入与使用此款导航app，对于首次使用的用户只需语音输入简单的基本信息即可进入使用（此步骤可跳过），在后续使用中可选择是否需要每次进入前登录，登录时使用人脸识别功能进入主页面，只需进行简单的单击任意位置的操作即可唤醒目的地的输入框，根据每一步的语音提醒进行语音输入目的地，用户无需给出完整清晰的目的地地址，只需输入简单的关键词，本app会根据poi搜索自动为您推荐可能的目的地，根据语音提示进行选择即可。导航过程中有实时的语音提示，为您提供更安全可靠的路线规划。
（口头操作说明：在2-3分钟时间限制内，对听众留下了「的确这是个可行丶可用的人工智能加值产品」的印象
### 界面流程及关键智能交互
### 1.使用水平
- 语音输入
- 人脸识别
- poi搜索
- 地标识别
使用水平：在PRD文件中是否有说明且展示，核心功能所应用的API之输入及输出

### 2.使用比较分析 
[公交导航准确度大PK:高德地图百度地图谁更精确 ](https://www.sohu.com/a/69051624_119779)这篇文章可以看出确实高德开发平台提供的导航api更为精准，当然百度的也不差，但既然是为视力障碍群体开发的导航app，自然要选择使用更为精准的地图导航。
使用比较分析：在PRD文件中是否有说明且提供连结证据，所使用的API是查找过最适用的（主要竞争者无或比较次），如考量其成熟度丶性价比丶等等

### 3.使用后风险报告
使用后风险报告：在PRD文件中是否有说明且提供连结证据，所使用的API类别的现在及未来发展性，如API市场竞争程度丶输入输出限制丶定价丶及可替代的程序库（改用自己开发的代码及数据库而不用API）等等
1. 产品功能结构图
![产品功能结构图](https://github.com/Luojiachunaaa/API_Final/blob/master/images/structure.png)
### 数据流程及关键智能API使用
解决方案总1.  关键智能API的思路及方法总体描述清晰，同行可以清楚评判这关键智能API的分析思路及分析技术(3: 0,1,2)
解决方案总2.  App产品的总体成果展示有效，同行可以清楚评判这关键智能API思路方法的用户可欲性 (用户有多大程度想用)(5: 0,1,2,3,4)
解决方案总3.  App产品的总体成果展示有效，同行可以清楚评判这关键智能API思路方法的技术可行性 (5: 0,1,2,3,4)
解决方案总4.  App产品的总体成果展示有效，同行可以清楚评判这智能API思路方法的商业可行性 (5: 0,1,2,3,4)
解决方案细1.  App产品的界面流程智能加值输入细节描述清晰，同行可以从界面流程图及文清楚评估这关键智能交互的专业水准(5: 0,1,2,3,4)
解决方案细2.  App产品的界面流程智能加值输出细节描述清晰，同行可以从界面流程图及文清楚评估这关键智能交互的专业水准(5: 0,1,2,3,4)
解决方案细3.  App产品的界面流程技术细节描述清晰，同行可以从界面流程图及文清楚评估这关键智能交互的专业水准(5: 0,1,2,3,4)
解决方案：数据流程及关键智能API使用 (26%)
分析成果总1.  智能API使用的流程及成果总体描述清晰，同行可以清楚评判这产品设计的关键流程及成果(3: 0,1,2)
分析成果总2.  App产品的数据流程总体展示有效，同行可以清楚评判这产品设计成果的用户可欲性  (用户有多大程度想用) (5: 0,1,2,3,4)
分析成果总3.  App产品的数据流程总体展示有效，同行可以清楚评判这产品设计成果的技术可行性 (5: 0,1,2,3,4)
分析成果总4.  App产品的数据流程总体展示有效，同行可以清楚评判这产品设计成果的商业可行性 (5: 0,1,2,3,4)
分析成果细1.  App产品设计的智能API使用及代码细节透过成果展示分析加值，同行可以从代码清楚评估这产品设计关键智能API使用的专业水准（各个平台的对比优势分析、可取代性）(5: 0,1,2,3,4)
分析成果细2.  App产品设计的数据流程图细节成果优秀，同行可以从图及文清楚评估这数据流程的智能API加值专业水准(5: 0,1,2,3,4)
分析成果细3.  App产品设计的”人工智能概率性考量”细节成果优秀，同行可以从图及文清楚评估智能API加值专业水准（各个平台的对比优势分析、可取代性）(5: 0,1,2,3,4)
---
## 学习/实践心得总结及感谢
心得总结及感谢(8%)
心得总结 1.  API驱动之智能产品App的心得提练，展示同行/同侪参考价值 (5: 0,1,2,3,4)
心得总结 2.  API驱动之智能产品App使用他人资源说明清楚合理，感谢语展示了对同行/同侪成果的尊重 (5: 0,1,2,3,4)
文档形式专业程度(24%)
文档形式 1.  App产品设计文档及原型制作优良，以代码注释及markdown图文展示了专业沟通能力 (3: 0,1,2)
文档形式 2.  App产品设计文档及原型制作优良，有充份的独特有效外连URL多个以上(2个得1分，最高20个10分) (10: 0,1,2,…10)
文档形式 3.  App产品设计文档及原型制作优良，以高清点阵图或高清矢量交互图展示了专业排版及沟通能力 (3: 0,1,2)
文档形式 4.  App产品设计文档及原型制作优良，有充份的原创高水平图表 （界面流程图&数据流程图/重复不算）(1得1分，最高10个10分) (10: 0,1,2,…10)



