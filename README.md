# **安道**--为视障群体提供快速及切实可行的目的地定位及路线规划导航
| 说明 | 安道APP需求文档状态 |
|:------:|:------|
| 产品名称 | 安道 |
| 产品描述 | 一款让有视力障碍人群更有安全感，更加可依赖的导航APP |
| 产品状态 | 进行中 |
| 产品作者 | 罗佳莼 |
| 迭代版本 | 1.0 |
| 现行版本 | 2.0 |
| [迭代增量内容](https://gitee.com/luojiachun/API_Final/compare/8e8328cf4f7487170c4266744796e060725e7b8e...96b857fccdd09e302844950d237cda20b4570653) | 见文档结尾 |
### 价值主张宣言
针对有视力障碍人群出行困难的问题，我认为市场上现有的地图导航软件对于这个群体而言还不够人性化，「安道」app就是对现有的地图导航软件的整合提升，是一款让有视力障碍人群更有安全感，更加可依赖的导航app。该App使用到的人工智能技术来源于高德开放平台的**POI搜索**技术，以及**路线规划及道路导航**等技术的辅助，这些技术帮助可以让该app结合实时路线中的场景，快速定位用户所在点，并更便捷地得到用户的目的地，帮助用户绕避开存在危险的地区，提供更安全、更人性化的出行导航。

### API价值宣言
- 高德开放平台POI搜索：搜索服务API是一类简单的HTTP接口，提供多种查询POI信息的能力，其中包括关键字搜索、周边搜索、多边形搜索、ID查询四种筛选机制。
- 百度AI开放平台语音识别API加值：将语音信息转化为文字方便记录，节省文字输入时间
- 高德开放平台路线规划API加值：为不同的视障用户提供最安全最贴心的路线规划
- 高德开放平台道路导航API加值：为不同的视障用户提供最精确的目的地导向

---

## 一、问题表述
### 1.1 使用情境
- 先天性失明用户，对于独自生活与出行较有经验，黑暗不会给生活带来太大影响的群体，在外出出行时需要一款操作简单的导航软件进行使用
- 后天性失明用户，不熟悉失明后的黑暗生活，对于出行有较大的困难，但需要逐步适应新生活的群体，在慢慢适应的生活中需要勇敢地独自外出体验，即可使用本导航软件为其提供更贴心更适合的导航

### 1.2 用户画像
- 核心用户：先天性失明用户，对于独自生活与出行较有经验，黑暗不会给生活带来太大影响的群体
- 重要用户：后天性失明用户，不熟悉失明后的黑暗生活，对于出行有较大的困难，但需要逐步适应新生活的群体

| 信息 | 画像1 |
| :----: | :---- |
| 姓名 | 宋敏 |
| 年龄 | 20岁 |
| 职业 | 学生 |
| 人物简介 | 在一次意外的交通事故中彻底失去光明，对于黑暗的生活很不适应，想要独立完成生活中的小事但对陌生的感觉需要慢慢熟悉 |
| 用户痛点 | 想进行简单的独自外出但无法在黑暗中使用普通导航软件 |

| 信息 | 画像2 |
| :----: | :---- |
| 姓名 | 白龙 |
| 年龄 | 35岁 |
| 职业 | 按摩师 |
| 人物简介 | 因为特殊原因从小失去光明，成长以来熟悉了黑暗中的生活，也喜欢挑战新鲜事物 |
| 用户痛点 | 对于地点位置详细信息无法记录，以至于选择一个陌生的目的地很困难 |

### 1.3 核心价值与用户痛点
企图解决的用户痛点：
1. 用户由于视力障碍的原因无法手动打字输入目的地
2. 用户对于地理信息较不敏感，得到详尽确切的目的地较为不便
3. 目的地不准确：导航提示已到达目的地但实际存在小距离差异
4. 普通地图导航往往提供**最近**路线，对于特殊群体而言需要的是**最安全**的路线
5. 语音播报不及时，没有实时路线返回
6. 用户在行进过程中遇到突发事件停止后，无法确定当前所处位置

| 核心价值 | 用户痛点 | API加值 |
|:------:|:------:|:------:|
| 精确的目的地导向 | 目的地不准确 | [高德开放平台POI搜索](https://lbs.amap.com/api/webservice/guide/api/search) |
| 目的地关键词地点推荐 | 对于地理信息较不敏感 | [高德开放平台POI搜索](https://lbs.amap.com/api/webservice/guide/api/search) |
| 语音输入目的地 | 无法手动打字输入目的地 | [百度AI开放平台语音识别API](https://ai.baidu.com/tech/speech/asr) |
| 提供最安全的路线规划 | 得不到最安全的路线 | [高德开放平台路径规划api](https://lbs.amap.com/api/webservice/guide/api/direction) |
| 实时返回语音提醒 | 语音播报不及时 | [百度AI开放平台语音识别API](https://ai.baidu.com/tech/speech/asr) |
| 准确的定位 | 无法确定当前所处位置 | [百度AI开放平台地标识别api](https://ai.baidu.com/tech/imagerecognition/landmark) |

### 1.4 人工智能概率性 
据实践研究表明，高德开放平台提供的导航较其他同类型产品而言精确度更高。实际情况下，大部分群体都会发现一个普遍导航软件都存在的通病：到达目的地附近后找不到精确的目的地地点，因此人工智能的精确性并没有高到我们可以完全信任他的地步。

| 技术优势 | 用户痛点 |
|:------:|:------:|
| 精确的目的地导向 | 目的地不准确 |
| 目的地关键词地点推荐 | 对于地理信息较不敏感 |
| 语音输入目的地 | 无法手动打字输入目的地 |
| 提供最安全的路线规划 | 得不到最安全的路线 |

*人工智能出错时解决方法*：
- 当目的地出现偏差时，提供准确的目的地具体位置语音播报
- 自动记录用户经常使用的出发地及目的地，在下一次导航时自动提取数据
- 用户在结束导航后主动输入详尽地地址供人工智能分析学习

*相关资料阅读*：[公交导航准确度大PK:高德地图百度地图谁更精确 ](https://www.sohu.com/a/69051624_119779)

---

## 二、需求列表
### 2.1 需求列表
| 优先级 | 用户痛点 | 用户需求 | API智能加值 |
|:------:|:------:|:------:|:------:|
| 核心 | 目的地不准确 | 精确的目的地导向 | [高德开放平台POI搜索](https://lbs.amap.com/api/webservice/guide/api/search) |
| 重要 | 无法手动打字输入目的地 | 语音输入目的地 |[百度AI开放平台语音识别API](https://ai.baidu.com/tech/speech/asr) |
| 次重要 | 得不到最安全的路线 | 提供最安全的路线规划 | [高德开放平台路径规划api](https://lbs.amap.com/api/webservice/guide/api/direction) |
| 不重要 | 无法确定当前所处位置 | 准确的定位 | [百度AI开放平台地标识别api](https://ai.baidu.com/tech/imagerecognition/landmark) |

### 2.2 利害相关者分析
- 系统性偏差
据科学的实践研究表明，高德开放平台提供的导航较其他同类型产品而言精确度更高，但即使这样，导航软件的系统性偏差依然存在，位置确定需要一个点的坐标，这也关系到GPS相关问题，例如信号强度，用户经常面对的情况是信号不佳以至于导航存在偏差，这一点需要更多地思考。
- ESG考量
    - Environment：有关视力障碍人群的生活环境最重要的设施建设就是导盲带,用带有凸出小条形方砖形成的通道,以便视力有障碍的群体更方便地出行，但如今部分导盲带上停满了车辆与障碍，以至于盲人用户群的出行更为困难
    - Social：社会对于视力障碍这类弱势群体应给予更多地关注，为这类群体提供更高更有价值的福利；在社区管理中为视力障碍群体提供更安心更有助于轻松生活的保障
    - Governance：公开透明的产品管理制度，严格遵守法律法规，谨遵商业道德
- [利害相关者图示](https://www.processon.com/view/link/5f1aacef637689168e32af57)
![利害相关者](https://images.gitee.com/uploads/images/2020/0724/183837_83f53d44_4866566.png "liyi.png")

### 2.3 市场分析
- 产品市场
> 据iiMedia Research(艾媒咨询)数据显示，2018年的PC网页导航用户规模为5.62亿人，中国PC网页导航用户规模呈缓慢增长态势，预计2019年的PC用户规模将达5.73亿人。
人们日常出行离不开导航软件，并且作为一款专为视力障碍人群打造的导航地图软件，市场上现有的产品对于这个群体而言可用性不强，而「安道」app在使用中可以让有视力障碍人群更有安全感，更加可依赖。市场相对而言受限，但据统计,全球视力损伤或失明人数高达22亿人,所以市场前景依然广阔。

- 产品优势：
    - 竞争产品较少，同类型产品的面向对象不同
    - 市场前景广阔，用户群固定
    - 开发技术难度较小，后期运营维护较不复杂
    - 有智能价值及开放平台提供智能服务

- 参考阅读资料：
    - [2020-2025年中国汽车导航行业市场深度研究及发展前景投资可行性分析报告](http://www.chinabgao.com/report/7049732.html)
    - [世界视力报告显示：全球视力损伤或失明人数高达22亿人](http://www.zgjkwm.com/a/shichangkuaibao/117661.html)

---

## 三、界面流程及关键智能交互
### 3.1 用户体验/旅程分析
对于视力有障碍的特殊用户群而言，出行较为不便且没有一款合适的导航软件为其提供更安全可靠的服务，在日常出行中，无法方便快捷地输入目的地，在行进过程中也会存在困难，道路路况信息了解不便。
- 3.1.1 交互及界面设计 
    - [产品功能结构图processon文档](https://www.processon.com/view/link/5f119a28f346fb2bfb2c8091)
![产品功能结构图](https://images.gitee.com/uploads/images/2020/0723/213631_69b01be1_4866566.png)

| 交互及界面设计 | 人工智能加值 |
|:------:|:------ |
| 新用户注册 | 用户首次进入产品后需要对自己的信息进行输入与选择，为此我们提供语音识别的人工智能价值方便用户语音输入基本信息 |
| 登录/进入 | 若开启每次都需登录的选项，只需进行简单的人脸识别即可确认使用者信息 |
| 输入目的地 | 考虑到视力障碍人群，特别是全盲用户的使用，安道app提供语音输入识别功能，只需一个简单的单击交互即可唤醒输入框 |
| 选择目的地 | 考虑用户疏于特殊群体，对于地理信息困难较不敏感，此app提供poi搜索，用户只需语音输入简单的关键词，即可根据用户信息及历史记录推荐出可能会前往的目的地供用户选择 |
| 导航过程 | 全场实时的语音导航 |
| 到达目的地 | 地标识别服务方便用户只需进行简单的交互即可知道当前所在位置 |

- 3.1.2 信息设计

| 核心信息/设计 | 人工智能加值 |
|:------:|:------|
| 启动页信息 | 提供简单的语音提示，给用户已进入app并开始使用的信息 |
| 登录页信息 | 用人脸识别的方式记录登录使用者的信息，在后续的使用中返回用户曾经的使用信息 |
| 输入目的地信息 | 语音识别到用户输入的目的地信息 |
| 选择目的地信息 | 根据poi搜索推荐用户可能到底的目的地信息 |
| 到达信息 | 实时语音返回用户所在位置及导航信息 |

- 3.1.3 口头操作说明 
不同于市场中普通的导航软件，安道app与使用者的交互更为便捷简单，使用户可以以更轻松可靠的操作进入与使用此款导航app，对于首次使用的用户只需语音输入简单的基本信息即可进入使用（此步骤可跳过），在后续使用中可选择是否需要每次进入前登录，登录时使用人脸识别功能进入主页面，只需进行简单的单击任意位置的操作即可唤醒目的地的输入框，根据每一步的语音提醒进行语音输入目的地，用户无需给出完整清晰的目的地地址，只需输入简单的关键词，本app会根据poi搜索自动为您推荐可能的目的地，根据语音提示进行选择即可。导航过程中有实时的语音提示，为您提供更安全可靠的路线规划。

### 3.2 DVF模型
- 用户可欲性 

针对有视力障碍人群出行困难的问题，我认为市场上现有的地图导航软件对于这个群体而言还不够人性化，「安道」app是一款让有视力障碍人群更有安全感，更加可依赖的导航app。视障用户有独立生活，正常出行的需求，渴望想普通人一样轻松便捷地出行，但市面上的导航软件的使用方式对他们而言不够友好，安道app就可以为用户提供适合他们使用的出行导航与规划。
- 技术可行性 
    - 有一定地技术难度的开发
    - 界面设计尽量简单清晰，方便用户有更好地操作体验，减少不必要的按钮以防误触
    - api的调用与整合需要有一定的技术能力，但依旧可行，api开放平台大多有调用使用的文档说明
    - 作为一款适用于视力障碍用户的app，需要设身处地地为用户着想，体验他们的生活，站在他们的角度去设计交互，这一点需要思考
-  商业可行性 

通过完善app的内容交互，形成初期的完整的软件，借助周边力量达到宣传推广的效果，吸引部分视障用户使用本产品并提出意见，对用户提出的痛点进行修改反馈，后期得到数量庞大的用户群后与相关行业进行推广合作，为vip用户提供家人关联功能，从中获取商业价值。

### 3.3 加值输入出细节
- [产品原型](https://modao.cc/app/e9ec371bcafd7b93e54074b7a25e8eb090af33d1?simulator_type=device&sticky)
- app使用时全程语音提示并伴有操作的语音翻译，登录单击即可进入，通过人脸识别技术登入导航页
![登录](https://images.gitee.com/uploads/images/2020/0724/184424_a14361fd_4866566.png "denglu.png")
- 单击进入目的地输入页面，语音输入目的地关键词即可，运用语音识别技术为用户提供更简便的输入方式，用户无需给出完整清晰的目的地地址，只需输入简单的关键词，本app会根据poi搜索自动为您推荐可能的目的地
![目的地](https://images.gitee.com/uploads/images/2020/0724/184444_4ca8a48e_4866566.png "mudidi.png")
- 根据语音提示进行目的地的选择后，进入导航，导航过程中有实时的语音提示，为您提供更安全可靠的路线规划
![导航](https://images.gitee.com/uploads/images/2020/0724/184457_0b95f73e_4866566.png "daohang.png")
- 个人也输入个人基本信息，其中包含常用地址输入，用户在使用前可以便捷地输入常用的目的地，方便使用时选择
![个人](https://images.gitee.com/uploads/images/2020/0724/184509_458bc3aa_4866566.png "geren.png")

### 3.4 界面流程图
- [界面流程图processon文档](https://www.processon.com/view/link/5f11969b07912906d9aa9e9b)
![界面流程图](https://images.gitee.com/uploads/images/2020/0723/213630_43264597_4866566.jpeg)
- [安道原型](https://modao.cc/app/e9ec371bcafd7b93e54074b7a25e8eb090af33d1?simulator_type=device&sticky)
---

## 四、数据流程及关键智能API使用
### 4.1 数据流程分析和界面流程的匹配
- 数据流程分析&界面流程图&原型&智能加值
![界面流程图](https://images.gitee.com/uploads/images/2020/0724/185055_08e1520b_4866566.png "liucheng.png")

### 4.2 DVF模型
-  用户可欲性 

针对有视力障碍人群出行困难的问题，我认为市场上现有的地图导航软件对于这个群体而言还不够人性化，「安道」app是一款让有视力障碍人群更有安全感，更加可依赖的导航app。视障用户有独立生活，正常出行的需求，渴望想普通人一样轻松便捷地出行，但市面上的导航软件的使用方式对他们而言不够友好，安道app就可以为用户提供适合他们使用的出行导航与规划。
-  技术可行性 
    - 有一定地技术难度的开发
    - 界面设计尽量简单清晰，方便用户有更好地操作体验，减少不必要的按钮以防误触
    - api的调用与整合需要有一定的技术能力，但依旧可行，api开放平台大多有调用使用的文档说明
    - 作为一款适用于视力障碍用户的app，需要设身处地地为用户着想，体验他们的生活，站在他们的角度去设计交互，这一点需要思考
-  商业可行性 

通过完善app的内容交互，形成初期的完整的软件，借助周边力量达到宣传推广的效果，吸引部分视障用户使用本产品并提出意见，对用户提出的痛点进行修改反馈，后期得到数量庞大的用户群后与相关行业进行推广合作，为vip用户提供家人关联功能，从中获取商业价值。

### 4.3 API使用
1. 高德开放平台**POI搜索**：[API测试代码](https://github.com/Luojiachunaaa/API_Final/blob/master/code/POI%E6%90%9C%E7%B4%A2(%E9%AB%98%E5%BE%B7%E5%BC%80%E6%94%BE%E5%B9%B3%E5%8F%B0).ipynb)
- 搜索服务API是一类简单的HTTP接口，提供多种查询POI信息的能力，其中包括关键字搜索、周边搜索、多边形搜索、ID查询四种筛选机制。
- 输入
![POI搜索](https://images.gitee.com/uploads/images/2020/0724/185647_28ef5029_4866566.png "poi01.png")
- 输出
![POI搜索](https://images.gitee.com/uploads/images/2020/0724/185655_1ffdbd55_4866566.png "poi02.png")
2. 百度AI开放平台**语音识别**：[API测试代码](https://github.com/Luojiachunaaa/API_Final/blob/master/code/SpeechRecognition.md)
- 百度AI开放平台语音识别API加值：将语音信息转化为文字方便记录，节省文字输入时间
- 输入
![语音识别](https://images.gitee.com/uploads/images/2020/0724/185706_84e59991_4866566.png "yuyin01.png")
- 输出
![语音识别](https://images.gitee.com/uploads/images/2020/0724/185714_8d30007f_4866566.png "yuyin02.png")
3. 高德开放平台**路径规划api**：[API测试代码](https://github.com/Luojiachunaaa/API_Final/blob/master/code/%E8%B7%AF%E5%BE%84%E8%A7%84%E5%88%92(%E9%AB%98%E5%BE%B7%E5%BC%80%E6%94%BE%E5%B9%B3%E5%8F%B0).ipynb)
- 高德开放平台路线规划API加值：为不同的视障用户提供最安全最贴心的路线规划
- 输入
![路径规划](https://images.gitee.com/uploads/images/2020/0724/185725_bc72b17d_4866566.png "lujing01.png")
- 输出
![路径规划](https://images.gitee.com/uploads/images/2020/0724/185734_8e617b5e_4866566.png "lujing02.png")

### 4.4 智能API使用成果展示加值
#### 各个平台的对比优势分析
- 地图导航

| 公司简称 | 关注度 | 支持平台 | 用户评论分析 |
|:------:|:------:|:------:|:------:|
| 高德地图API | 873 | Android/iOS/WP/Web | 文档全面；支持平台全面；调用复杂；覆盖率高 |
| 百度地图API | 1164 | Android/iOS/Web | 集成简单好用、全面；兼容问题；文档全面 |

- 语音识别

| 公司简称 | 相关产品 | 核心技术 | 准确性 |
|:------:|:------:|:------:|:------:|
| 科大讯飞 | 1.语音引擎、教育产品、手机应用、互动音乐等 | 语音识别、语音合成、语音唤醒、自然语言处理 | 国内四六级英语口语评测技术和录音质检软件提供商，识别准确率超过95%。支持中英粤藏维等5个语种、川豫和东北等方言。语音输入速度达180字/分，识别结果响应时间低于500ms支持在线/离线命令词识别，准确率99% |
| 百度语音 | 百度开放平台 | 语音识别，语音合成，语音唤醒 | 离线在线融合，识别技术很强，识别准确率90%以上 |
| 腾讯 | 智能语音SDK | 语音识别，语音合成，声纹识别 | 通用领域的语音识别率最高可以达到95%，声纹识别准确率99% |
| 阿里云 | 智能语音交互 | 语音识别、语音合成、自然语言理 | 识别准确率97%|

- 参考文献：
    - [百度地图API VS 高德地图API——地图开放平台竞品分析](https://coffee.pmcaff.com/article/250851494241408/pmcaff?utm_source=forum&from=related&pmc_param%5Bentry_id%5D=1000000000131376)
    - [语音识别行业技术和市场横向对比](https://blog.csdn.net/king_audio_video/article/details/88826059)

#### 使用可行性
- 技术
    - 调用api技术有专业的文档说明知道，技术难度较小
    - 产品设计尽量简单，极简的页面让用户的操作更有安全感
    - 交互步骤减少，避免用户在功能的使用中出现误触与走失
- 市场
    - 用户群稳定，用户市场前景然广阔
    - 市场上现有的产品对于我们产品面向的群体而言可用性不强，市场竞争压力较小

### 4.5 数据流程图文
- 首次使用的用户语音输入基本信息进入使用，在后续使用中即可使用注册时输入的数据
- 登录时使用人脸识别功能进入主页面，使用人脸信息数据库
- 语音输入目的地，导航过程中有实时的语音提示，为您提供更安全可靠的路线规划，语音库数据提供帮助
- 用户无需给出完整清晰的目的地地址，只需输入简单的关键词，poi搜索的地理信息数据库自动推荐可能的目的地

- [数据流程图processon文档](https://www.processon.com/view/link/5f1197e85653bb7fd23e9ddc)
![数据流程图](https://images.gitee.com/uploads/images/2020/0723/213629_1270390c_4866566.jpeg)


#### 4.6 数据简介
- 地图的数据来源于高德开放平台，为导航路线规划提供帮助
- 地理信息的数据来源于高德开放平台，帮助准确定位用户位置及目的地位置信息
- 语音识别的数据来源于百度AI开放平台，大量的语音文字库帮助识别用户输入的语音

#### 4.7 人工智能概率性考量
据实践研究表明，高德开放平台提供的导航较其他同类型产品而言精确度更高。实际情况下，大部分群体都会发现一个普遍导航软件都存在的通病：到达目的地附近后找不到精确的目的地地点，因此人工智能的精确性并没有高到我们可以完全信任他的地步。

*人工智能出错时解决方法*：
- 当目的地出现偏差时，提供准确的目的地具体位置语音播报
- 自动记录用户经常使用的出发地及目的地，在下一次导航时自动提取数据
- 用户在结束导航后主动输入详尽地地址供人工智能分析学习

*相关资料阅读*：[公交导航准确度大PK:高德地图百度地图谁更精确 ](https://www.sohu.com/a/69051624_119779)

---

## 五、学习/实践心得总结及感谢
### 心得
我想对在同行/同侪说：本项目具体实践中，我确实有很多的心得与体会，作为一个项目的“创造者”，要时时刻刻站在用户的角度思考，只有从**人**的角度出发，才能称得上可以使用人工智能，设计的产品要有切实可靠，对用户痛点一针见血的价值主张，才能是一个合格可行的产品。

最后，根据市场上用户对于更贴近需求的导航app的所需，我们主张更安全更放心的理念，得到普遍用户群拥有的痛点，根据重要级筛选出最核心的价值，结合视障人群的特殊性，设计出方便用户操作的页面，根据高德开放平台和百度AI开放平台提供的数据对产品的内核进行搭建，最终产生了符合视力障碍人群需求的导航产品。

### 感谢
- [我的代码](https://github.com/Luojiachunaaa/API_Final/tree/master/code)可供同行/同侪们参考
- 感谢[高德开放平台](https://lbs.amap.com/)提供的很好用的api，感谢提供清晰易懂的文档说明，感谢提供丰富的数据
- 感谢[百度AI开放平台](https://ai.baidu.com/)提供的很好用的api，感谢提供清晰易懂的文档说明，感谢提供丰富的数据
- 感谢辛苦的廖老师和许老师和王老师和其他老师们，感谢帅哥美女们的耐心教导
- 感谢同学们对我的项目的指导与建议，一起加油⛽️

---

## 六、互评指引
- 有效外连URL
1. [高德开放平台POI搜索](https://lbs.amap.com/api/webservice/guide/api/search)
2. [百度AI开放平台语音识别API](https://ai.baidu.com/tech/speech/asr)
3. [高德开放平台路径规划api](https://lbs.amap.com/api/webservice/guide/api/direction)
4. [安道原型](https://modao.cc/app/e9ec371bcafd7b93e54074b7a25e8eb090af33d1?simulator_type=device&sticky)
5. [百度AI开放平台地标识别api](https://ai.baidu.com/tech/imagerecognition/landmark)
6. [公交导航准确度大PK:高德地图百度地图谁更精确](https://www.sohu.com/a/69051624_119779)
7. [利害相关者图示processon文档](https://www.processon.com/view/link/5f1aacef637689168e32af57)
8. [2020-2025年中国汽车导航行业市场深度研究及发展前景投资可行性分析报告](http://www.chinabgao.com/report/7049732.html)
9. [世界视力报告显示：全球视力损伤或失明人数高达22亿人](http://www.zgjkwm.com/a/shichangkuaibao/117661.html)
10. [产品功能结构图processon文档](https://www.processon.com/view/link/5f119a28f346fb2bfb2c8091)
11. [API测试代码](https://gitee.com/luojiachun/API_Final/tree/master/code)
12. [数据流程图processon文档](https://www.processon.com/view/link/5f1197e85653bb7fd23e9ddc)
13. [百度地图API VS 高德地图API——地图开放平台竞品分析](https://coffee.pmcaff.com/article/250851494241408/pmcaff?utm_source=forum&from=related&pmc_param%5Bentry_id%5D=1000000000131376)
14. [语音识别行业技术和市场横向对比](https://blog.csdn.net/king_audio_video/article/details/88826059) 
 
- 原创图表
    - 用户画像2张
    - 核心价值与用户痛点表格1个
    - 需求列表表格1个
    - 各个平台的对比优势分析表格2个
    - 利害相关者图示1张
    - 产品功能结构图1张
    - 原型交互图3张
    - 界面流程图1张
    - API输入/出代码展示图6张
    - 数据流程与界面流程分析图1张
    - 数据流程图1张
---

## 七、增量改进内容
- [增量改进链接](https://gitee.com/luojiachun/API_Final/compare/8e8328cf4f7487170c4266744796e060725e7b8e...96b857fccdd09e302844950d237cda20b4570653)
- 文档版本更新至2.0
- 文档格式修改
- 问题表述部分：
    - 添加了使用情境部分内容
- 需求列表部分：
    - 用图表和文字的方式对利害相关者进行分析
    - 补充了对市场的分析
- 界面流程及关键智能交互部分：
    - 加入了加值输入出细节的描述
    - 完善了用户流程图与原型
- 数据流程及关键智能API使用部分：
    - 补充了智能API使用成果展示加值部分内容
    - 添加数据流程图文的展示
