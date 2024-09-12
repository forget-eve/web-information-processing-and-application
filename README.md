# 课程相关

## 课程主页

- [点此链接](http://staff.ustc.edu.cn/~tongxu/webinfo/)

## 课程安排

- [x] 课程形式：讲课 + 实验
  - 理论学时 60 学时 + 实验学时 30 学时(无单独实验课安排)
- [x] 成绩组成： $\color{red}{50}$ % 考试成绩 + $\color{blue}{40}$ % 实验成绩 + 10% 作业成绩(上下半学期各一次，涉及部分章节)
- [x] 实验安排
  - 信息检索、知识图谱、大语言模型各一次实验
    > - 实验大约将第3周、第11周、第15周发布
    > - 2-3人一组，按组进行打分，可以单人进行(无优惠政策)
- [x] 考试形式：半开卷(一张A4纸)

# 第一节 绪论

## 课程主旨

- 问题输入：卷帙浩繁的信息海洋
- 问题输出：满足需求的特定信息
- 解决方案可以分为以下三步

```mermaid
graph LR
A[信息检索]-->B[信息提取]
B-->C[信息排序]
D(从海量数据中找到可能有用的文档)-->A
E(从目标文档中提取和关联价值信息)--> B
F(对目标信息进行排序并呈现给用户)-->C
```

## 课程背景

- [x] 案例1：文档搜索
  - 基于搜索关键词，寻找最相关的文档，是信息检索的基本任务
- [x] 案例2：多模态搜索
  - 从单一的文本信息到更为复杂的多模态搜索，任务与方法都在拓展
- [x] 案例3：面向知识的搜索
  - 人们已不再满足于单纯呈现原始的文档，而需要更加精炼的知识表达与更加直观的需求解决

## 课程框架

- [x] 本课程所要解决的问题
  - Web信息如何获取？【网络爬虫】
  - Web信息如何整理与存储？【文本处理、索引】
  - Web信息如何有效搜索？【查询/排序/评估】
  - 如何提炼价值信息与知识？【信息抽取】
  - 如何基于知识进行推理应用？【知识图谱应用】
  - 大语言模型技术将为信息检索带来什么？【LLM导论】

```mermaid
graph LR
A[Web信息] --> |信息抓取| B(文本处理)
B-->C[索引]
subgraph First
  D[查询]
  E[排序]
  F[评估]
end
C-->E
subgraph Second
  G[信息抽取]
  H[知识推理]
  I[大语言模型]
end
E-->H
```

## 课程内容

- [x] 围绕“ $\color{red}{信息检索}$ ”、“ $\color{blue}{知识图谱}$ ”两大模块

<p align="center">
  <img src="./img/课程内容1.png" alt="课程内容">
  <img src="./img/课程内容2.png" alt="课程内容">
  <img src="./img/课程内容3.png" alt="课程内容">
</p>

## Web 信息基础

### Web信息起源

- [x] Web信息起源：1965，超文本概念提出
  - Ted Nelson在1965年提出了超文本的概念。
    > - HyperText，源自于“非连续性著述”( `Non sequential writing` ，Web的第一个特性)的理念，即分叉的、允许读者作出选择的文本。
    > - 以海量数据为基础，使原先的线性文本变成无限延伸、扩展的非线性文本。
  - 超文本传输协议(HTTP ，HyperText Transfer Protocol)
  - 超文本标记语言(HTML，HyperText Markup Language)

- [x] Web信息起源：1969，因特网起源
  - 1969年，互联网的原型 `ARPANet` 由美国国防部研究计划署(DARPA)所制定的协定下诞生，首先用于军事连接。
    > - 起初只有4个结点，分布在UCLA等四所大学的4台大型计算机。
    > - ARPANet的试验较好地解决了异种机网络互联的一系列理论和技术问题，并推动了TCP/IP协议的诞生(1983)。
  - 1986年，美国国家科学基金会(NSF)建立NSFNet广域网，逐渐取代了ARPANet。

- [x] Web信息起源：1989，万维网诞生
  - 1989年，欧洲核子物理研究所(CERN)的Tim Berners Lee(万维网之父)等人首次提出了一个分类互联网信息的协议，即World Wide Web
    > - 在1990年，他写出了第一个网页：http://info.cern.ch
    > - 他定义了URLs、HTML、HTTP等的规范，使网络能够为大众所使用。
    > - 他创立了万维网联盟(World WideWeb Consortium，W3C)并担任主席

### Web特点

- Web的信息流视角：Web 1.0时代

```mermaid
graph LR
A[信息提供者]-->B[信息整合者]-->C[信息消费者]
```

- Web的信息流视角：Web 2.0时代
  - 我们每个人，既是信息的消费者，也是信息的生产者

- Web的信息流视角：Web 3.0时代
  - 两个不同方向但又相互耦合的猜想
    > - $\color{red}{更加个性化、更加智能化、跨越平台与站点的信息大一统}$
    > - $\color{blue}{更加去中心化，基于区块链支撑的用户确权，以用户为中心}$

### Web搜索发展史

#### 搜索起源

- [x] 搜索引擎发展史：1990年，Archie
  - Archie：一般公认最早的搜索引擎
    > - 由麦吉尔大学的Alan Emtage等几位学生发明，用于搜索互联网上的匿名FTP
    > - Archie依靠脚本文件搜索互联网上的匿名FTP(无需登录信息)，然后根据用户需求反馈相应的文件，它的实质是一个可搜索的FTP文件名列表。
  - 目前仍有少量提供Archie服务的网站

- [x] 搜索引擎发展史：1993年，Wanderer
  - Wanderer：最早的爬虫
    > - 由MIT的学生Matthew Gray设计
    > - 原意用于统计互联网上服务器的数量，而非为搜索引擎所设计
  - Wandex：最早的网页索引计划
    > - Wanderer后来发展为可以捕获网址，而为这些网址建立索引的计划就是Wandex
  - 其他诞生于1993年的Robots
    > - ALIWEB(Archie-like Index of WEB，发表于首届WWW会议)
    > - WWW Worm，收集了海量多媒体文件，并可通过关键词检索

- [x] 搜索引擎发展史：1994年，Yahoo！
  - 1994年，最老的“分类目录”搜索数据库之一Yahoo诞生
    > - 由美籍华人Jerry Yang(杨致远)与David Filo所共同创造
    > - 最早的Yahoo的数据是手工输入的，实际上只是一个可搜索的目录
    > - 1995年，Yahoo网站正式上线

- [x] 搜索引擎发展史：1994年，Lycos
  - 1994年诞生，搜索引擎中的元老，是最早提供信息搜索服务的网站之一
  - 通过前缀匹配与字符近似匹配，提供网页自动摘要和相关性排序，数据量较大，整合了搜索数据库、在线服务和其他互联网工具
  - 2000年被西班牙网络集团收购后，目前是全世界最大的西班牙语搜索引擎

- [x] 搜索引擎发展史：1994年，Infoseek
  - 1994年诞生，沿袭了Yahoo！与Lycos的概念。
  - 1995年，与网景公司(Netscape)的战略性协议实现强强联合
  - 2001年2月，Infoseek改用Overture的搜索结果
  - 李彦宏曾担任Infoseek核心工程师，主导了Infoseek的革新换代

- [x] 搜索引擎发展史：1995年，Metacrawler
  - 1995年，第一个元搜索引擎诞生，由华盛顿大学的两位硕士生共同开发
  - 元搜索引擎的概念(Meta SearchEngine Roundup)
    > - 用户提交搜索后，由元搜索引擎负责转换处理，然后提交给多个预先选定的独立搜索引擎
    > - 各独立搜索引擎返回查询结果后，再集中处理并返回给用户

- [x] 搜索引擎发展史：1995年，Altavista
  - 第一个支持自然语言搜索的引擎
  - 第一个实现高级搜索语法的引擎
    > - AND、OR、NOT等
  - 2003年，Altavista被Overture收购，后者是Yahoo的子公司

- [x] 搜索引擎发展史：1997年，Google
  - 1997年，全球最大的搜索引擎Google诞生。
  - 1995年，Larry Page(PageRank因此得名)来到斯坦福攻读博士，并开始研究网络链接项目
  - 他与Sergey Brin提出了PageRank技术，并用于搜索引擎，从而改写了搜索引擎的定义
  - 1997年，Google.com域名被注册，1998年，Google公司正式成立

- [x] 搜索引擎发展史：1997年，天网
  - 国内第一个基于网页索引搜索的搜索引擎，见证了中国互联网发展史
    > - 由北京大学网络实验室研究开发，是国家重点科技攻关项目"中文编码和分布式中英文信息发现"的研究成果。
    > - 于1997年10月29日正式在CERNET上向广大互联网用户提供Web信息搜索及导航服务
    > - 教育网优势，FTP搜索功能强大

- [x] 搜索引擎发展史：2000年，百度
  - 2000年，由前Infoseek资深工程师李彦宏创立
    > - 专注于中文搜索领域，目前是最大的中文搜索引擎
    > - 2003年，根据某在线调查，百度已超越Google成为中国网民首选的中文搜索引擎

- [x] 搜索引擎发展史：下一代搜索引擎？
  - 2009年，Wolfram Alpha上线
    - 搜索引擎？计算知识引擎！
    - 直接向用户返回答案，而不是返回网页链接
      > - 倘若输入“抛10次，4次正面向上”，它可以回答抛硬币的概率问题。甚至连某地下一次日食的时间，或者国际空间站现在的位置，它都能给你答案
  - 2016年，微软小冰读心术
    - 如何明确用户的检索需求？
    - 通过若干连续问题确认用户的真实意图，避免歧义干扰
      > - 本质是决策树的应用
      > - 背后有庞大的数据库支撑
      > - 如何设计提问策略是核心问题
  - 2023年，NewBing
    - 与大模型相结合，开启信息检索新时代
    - 从提供信息，抽取/归纳信息到“生成”信息，提供更灵活与更友好的服务
      > - 基于海量数据堆积而成的“涌现”能力
      > - 借助思维链“去伪存真”
      > - 用户反馈与互动帮助其成长
      > - `小心背后的“幻觉”现象`

### Web搜索的挑战

- [x] 来自三方面的挑战：数据、用户、利益

```mermaid
graph LR
A[飞速增长的海量数据]
B[复杂多变的用户需求]
C[技术让位于利益]
```

<!-- tabs:start -->

#### **来自数据的挑战**

<!-- tabs:start -->

##### **海量数据**

- 数据的积累，无论绝对增长还是相对增速都是惊人的数字

##### **异构数据**

- 无论是网页结构的不同，还是数据模态的不同，都对Web信息的有效处理带来了挑战

##### **数据质量**

- Web中包含大量未经编辑处理或权威确认的信息，可能导致错误、无效或误导

##### **数据不稳定性**

- 许多网站和文档快速的添加和消亡，导致大量死链的存在
- 甚至，已有网页内容也在不断地发生更新

<!-- tabs:end -->

#### **来自用户的挑战**

<!-- tabs:start -->

##### **查询需求的表达**

- 用户可能无法采用规范、清晰的方式表达其查询需求
- 用户表达的非规范性 × 语义演化的日新月异 → 玩梗

##### **知识需求与直观表达**

- 技术使人们缺乏耐心，希望直接从搜索引擎获得答案，而不是通过阅读文档自行得到答案

##### **个性化需求**

- 大众化的信息需求被个性化、差异化的信息需求所取代

<!-- tabs:end -->

#### **来自利益的挑战**

<!-- tabs:start -->

##### **SEO对于搜索的干扰**

- 搜索引擎优化( `Search Engine Optimization` )，可能提升网站效率，也可能因滥用搜索算法而影响正常使用

##### **竞价排名对于搜索的干扰**

- 基于广告改变排序，对使用者产生误导

##### **低质内容的滥觞——洗稿**

- 技术的滥用导致洗稿工具等手段盛行拉低内容质量，恶化用户体验

<!-- tabs:end -->

<!-- tabs:end -->

## 信息检索概述

### 基本概念

- [x] 信息检索(Information Retrieval)
  - 基本含义：给定用户需求，从数据库中寻找并反馈相关的文档
    - Query：用户的查询需求
    - Corpus：待检索的数据库
    - Relevance：文档满足查询需求的程度
  - <kbd>信息检索是关于信息的结构、分析、组织、存储、搜索(Search)和获取(Retrieval)的领域 <br>—— Gerard Salton，1968</kbd>

### 信息检索的发展历史

- 1950年，明尼苏达大学的Calvin Mooers提出了“信息检索”这一概念
- 1960年代，康奈尔大学的Gerard Salton研发了SMART系统，被视作信息检索的鼻祖
- 1970年代，SIGIR成立，信息检索领域的旗舰学术会议由此开始
- 1980年代，商用IR系统开始出现
- 1990年代，TREC会议于1992年起始，开始标准测评、Web搜索等研究

### 信息检索 vs. 数据库

- [x] 数据库属于标准的结构化数据，而信息检索往往面临文本、图像、视频等非结构化或半结构化数据。
- [x] 数据库依赖精确的查询条件，而信息检索的查询词更加自由，匹配也相对粗疏
- [x] 数据库对排序并不强调，而信息检索的效果关键在于相关性排序

### 信息检索的应用场景

- 通用搜索
  - 一般的Web搜索，IR最常见的应用

- 垂直搜索(Vertical Search)
  - 搜索被限定在特定的主题和领域上

- 内部搜索
  - 内部网络甚至个人电脑中的搜索引擎

- P2P搜索(Peer-to-peer Search)
  - 由节点构成的网络中寻找信息，但没有集中式的控制

### 信息检索的基础问题

<!-- tabs:start -->

#### **查询理解**

- [x] 信息需求是人们发送查询的背后动因
- [x] 准确理解查询需求是信息检索的前提
- [x] 用户是搜索质量的终极判定者，需要通过与用户的交互，帮助用户表达他们的信息需求
  - 通过上下文信息去除歧义影响
- [x] 查询建议、查询扩展等应用

#### **相关性计算**

- [x] 相关性是判断是否满足需求的基础，基于相关性的排序决定了文档呈现顺序
- [x] 单纯依赖查询和文档的简单匹配，未必能够得到所需的结果
- [x] 不同类型的检索模型(Retrieval Model)导致了不同假设的相关性计算

#### **效果评估**

- [x] 信息检索的质量取决于反馈文档与用户期望的匹配程度
- [x] 常见的评价指标：准确率(Precision)、召回率(Recall)、F值(F-measure)等
- [x] 活跃的基准测试项目：TREC
  - https://trec.nist.gov/
  - 围绕问答、特定领域检索、主体识别等项目展开测评

#### **检索性能**

- [x] 如何快速响应用户的检索需求？
- [x] 如何利用索引减少检索所需时间？
- [x] 如何对检索条件和规则进行模块化，以实现效果与效率的均衡？

<!-- tabs:end -->

# 第二章 爬虫基础

> - Python教程(第21节-第29节部分)
> - https://www.bilibili.com/video/BV1ws411i7Dr/
> - Python爬虫全套课程
> - https://www.bilibili.com/video/BV1Yh411o7Sz

- [x] 如果觉得听课太累，下面还有更简洁的实战教程
  - 零基础入门版
    - https://zhuanlan.zhihu.com/p/21479334
  - 常用工具
    - https://zhuanlan.zhihu.com/p/110448373
    - https://zhuanlan.zhihu.com/p/57678048
- [x] 实战教程
  - 卷王版
  - 一个收集各种爬虫(默认爬虫语言为 python)的集合(如Bilibili用户、京东商品等)，一应俱全。不过有的失效或者不更新了，大佬们自由发挥。
  - https://github.com/facert/awesome-spider
- [x] 进阶版：分布式爬虫
  - 含豆瓣热门、百度贴吧、百度翻译3个实例。建议循序渐进。
    - https://github.com/Kr1s77/Python-crawler-tutorial-starts-from-zero
- [x] 拓展(移动端数据如何获取？)
  - 微信小程序 Charles抓包
    - https://blog.csdn.net/HeyShHeyou/article/details/90452656
  - 手机APP fiddler抓包
    - https://zhuanlan.zhihu.com/p/34430703

## 网络爬虫的定义与需求

- [x] Web网络的图模型
  - 以网页为节点、超链接(Hyper-Link)为有向边

<p align="center">
  <img src="./img/Web网络的图模型.png" alt="Web网络的图模型">
</p>

- [x] 爬虫的任务定义
  - 从一个种子站点集合(Seed sites)开始，从Web中寻找并且下载网页，获取排序需要的相关信息，并且剔除低质量的网页。
  - 常见的爬虫类型
    - 通用网络爬虫：目标为全网Web信息，主要为门户站点搜索引擎和大型Web服务提供商采集数据。
    - 聚焦网络爬虫：选择性爬取与预定主题相关的内容。
    - 增量式网络爬虫：对已下载内容进行增量式更新并只爬取更新内容。
    - 深度网络爬虫：专门负责获取搜索引擎无法索引的、超链接不可达的或提交表单后才可见的网络内容。

- [x] 爬虫的基本用途
  - 数据展示、引擎优化、数据分析、特定应用

- [x] 爬虫的基本流程

<p align="center">
  <img src="./img/爬虫的基本流程.png" alt="爬虫的基本流程">
</p>

> - 从爬取网页中获取更多URL，充实URL库，进而获取新的网页

### 爬虫的数量覆盖率问题

<!-- tabs:start -->

#### **问题——“全”**

- [x] 遍历完备性无法保证
  - 孤立节点的存在(如下图右半部分)
  - 其他影响遍历的因素
  - 部分“偏远”节点难以遍历
  - 网络结构的动态演化
  - IP/Robots等条件的约束

<p align="center">
  <img src="./img/爬虫的数量覆盖率问题1.png" alt="爬虫的数量覆盖率问题">
</p>

#### **问题——“好”**

- [x] 如何度量网页的重要性？
  - 启发式方法：出入度…
  - 基于结构：PageRank/HITS…
  - 开放问题：信息密度衡量？
- [x] 不仅重要，还要保证时效
  - “时新性”的要求

<p align="center">
  <img src="./img/爬虫的数量覆盖率问题2.png" alt="爬虫的数量覆盖率问题">
</p>

<!-- tabs:end -->

### 爬虫的主要需求

- <span style="color:blue;">速度(Speed)</span>：突破网络瓶颈，最短时间内获取所需网页
- <span style="color:blue;">可扩展性(Scalability)</span>：基于多爬虫机制，有效打破单爬虫效率天花板
- <span style="color:blue;">健壮性(Robustness)</span>：有效应对服务器陷阱等潜在问题
- <span style="color:blue;">时新性(Freshness)</span>：保持内容的时效性，提升用户体验
- <span style="color:blue;">友好性(Politeness)</span>：遵循网络秩序，不影响网络服务正常运转
- <span style="color:blue;">合法性(Legitimacy)</span>：遵守相关法律，不侵犯用户隐私、商业机密等

<!-- tabs:start -->

#### **速度**

- [x] 2012年的统计数据：谷歌每天需要爬取200亿个页面
  - 以每周1400亿个页面计算，约为 $2^{37}$ 个页面
  - 平均每个页面64KB，约为 $2^{16}$ 个bit
    - 实际情况远远不止64KB，大量非文本内容
  - 可知每秒流量>100Gb/s
- [x] 网络瓶颈的存在对速度的限制
  - 以家用100Mbps网络为例，考虑以太网MTU为1500字节(<span style="color:green;">上限了！</span>)，即使达到100%利用率，每秒也仅传输约8333个网页

#### **可扩展性**

- [x] 单一爬虫工作效率低下，难以突破效率天花板。
- [x] 采用多爬虫机制已成为大型搜索引擎的工作常态。
- [x] 多个爬虫带来新的挑战
  - 如何管理多个并发的连接？
  - 不同爬虫负责不同URL，如何进行划分？
  - 过多的硬件并行好处并不大
    - 抓取的性能瓶颈出现在通讯和硬盘读写

#### **健壮性**

- [x] 如何有效应对爬取过程中所面临的各种风险？
  - 爬取网页时陷入回路怎么处理？
  - URL不规范如何解决？
  - 服务器陷阱如何应对？
  - 系统崩溃如何处理？

#### **时新性**

- [x] T时刻的时新性：所抓取的网页内容与T时刻该网页的最新内容一致
- [x] 网页年龄：距离网页最近一次更新的时间
  - 通过对网页更新行为的建模来预测年龄
- [x] 保持爬取内容的时新性能够提升搜索效果
  - 但同时，过度重视时新性将严重增加搜索引擎的负担。
  - 部分网页频繁更新，增加抓取难度

#### **友好性**

- [x] 不能显著影响被爬取的服务器性能
  - 大量DNS查询可能造成类似DDOS的效果
- [x] 有些服务器可能不希望被爬取
  - Robots exclusion
  - 反面教材：360搜索、头条搜索

#### **合法性**

- [x] 法律中的规定
- [x] 我国：《互联网搜索引擎服务自律公约》，无针对爬虫的特定规定，但爬取的数据可能侵犯用户隐私权、违反《反不正当竞争法》等
  - 欧盟：GDPR
  - 加州：CCPA
  - …… 

<!-- tabs:start -->

##### **Linkedin vs hiQ(2019)**

- [x] hiQ作为数据分析公司爬取Linkedin的数据，Linkedin发出要求终止的信函之后限制了hiQ访问数据。最终最高法院判决Linkedin 不得作出限制。

##### **杭州魔蝎科技侵犯公民个人信息案(2021)**

- [x] 魔蝎科技将开发的前端插件嵌入网贷平台App中，利用各类爬虫技术，爬取用户本人账户内的通话记录、社保、公积金等各类数据，并提供给网贷平台用于判断用户的资信情况

<!-- tabs:end -->

#### **友好 & 合法**

- [x] 一个合适的爬虫是怎样的
  - 只爬取需要的数据
  - 满足被爬站点的使用协议
    - 注意：Robots协议被认定为搜索引擎行业内公认的、应当被遵守的商业道德
  - 不对被爬网站造成不良影响(如造成DDoS)
  - 不收集可定位到个人的信息(数据脱敏/合并)
  - 保护好被爬取的数据

<!-- tabs:end -->

- [x] 友情提示：爬虫本中立，数据应保护
  - 遵守协议，不要爬取隐私、涉密数据
  - 爬取方式应友好且合法，不影响网站正常运行
  - 如果不幸吃上大碗牢饭，不把为师说出去就行了

## 爬虫的基本要素

### 爬虫所涉及的协议和要素

- [x] HTML / HTTP
- [x] DNS / URL
- [x] Sitemap
- [x] Robots Exclusion

<!-- tabs:start -->

#### **HTML / HTTP**

<!-- tabs:start -->

##### **HTML**

- [x] 如何表示与获取网页中的链接结构？

<p align="center">
  <img src="./img/如何表示与获取网页中的链接结构.png" alt="如何表示与获取网页中的链接结构">
</p>

- [x] HTML文件示例

<p align="center">
  <img src="./img/HTML文件示例.png" alt="HTML文件示例">
</p>

- [x] HTML的基本概念
  - HyperText Markup Language，书写网页的“框架语言”
  - 基本组成：“标记”(Tags)+“文本内容”(Text)
    - 例如： `<a href="http://www.ustc.edu.cn/2062/list.htm">学校概况</a>`
  - 标记的作用：
    - 说明网页元数据(如“标题”等)
    - 说明文本内容的布局和字体、字号等信息
    - 嵌入图片、视频、创建超链接等

- [x] HTML的示例框架

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<html>
<head>
  <title> This is the title but often omitted </title>
</head>
<body>
  <img src = “url1” alt=“text”>
  other text
  <a href = “url2” title=“anchor text”> this is link text </a>
</body>
</html>
```

- [x] HTML中具有特别意义的文字

```html
<head><title> text </text></head>
```
> 是搜索服务显示的内容之一（URL，标题，摘要等）

```html
<img src=“url” alt=“text”>
```

> 图片描述，可以帮助我们做“从文字到图片”的查询

```html
<a href=“url” title=“text”>link text</a>
```

> 有助于理解目标网页内容及网页之间在内容上的关系

##### **HTTP**

- [x] HTTP的基本概念
  - 超文本传输协议(HyperText Transport Protocol)
    - 工作在TCP 之上(请求/应答方式)
    - 容许在一个TCP 连接上发多个HTTP请求
  - 工作步骤(从客户端看)
    - 通过域名服务器(DNS)得到服务器主机的IP地址
    - 用TCP和服务器建立联系
      - 发送HTTP请求(例如，GET或POST)
      - 接收HTTP应答头
      - 接收HTML网页内容

- [x] HTTP的应用实例

<p align="center">
  <img src="./img/HTTP的应用实例.png" alt="HTTP的应用实例">
</p>

- [x] HTTP的状态代码分类

<p align="center">
  <img src="./img/HTTP的状态代码分类.png" alt="HTTP的状态代码分类">
</p>

> - 重点记住一些特殊的状态码，如：200(OK)，403(Forbidden)，404(Not Found)……

<!-- tabs:end -->

#### **DNS / URL**

<!-- tabs:start -->

##### **DNS**

- [x] DNS的基本概念和作用
  - 域名系统(Domain Name System)
    - 将域名和IP地址相互映射的一个分布式数据库。
    - DNS地址解析可能成为重要瓶颈，甚至造成类似DOS的攻击效果

<p align="center">
  <img src="./img/DNS.png" alt="DNS">
</p>

- [x] 如何提高DNS解析模块的性能？
  - `并行DNS Client`
  - `缓存cache DNS results`
  - `预取prefetch client`

<!-- tabs:start -->

###### **并行 DNS Client**

- [x] 并行的地址解析Client
  - 专门对付多个请求的并行处理
  - 容许一次发出多个解析请求
  - 协助在多个DNS server之间做负载分配
    > - 例如，根据掌握的URL进行适当调度

###### **缓存 cache DNS results**

- [x] 增加DNS缓存的重要性
  - 面向海量URL和主机的搜索任务，如果没有DNS缓存，会造成频繁查询DNS服务器，从而造成类似于拒绝服务攻击(DOS)的副作用。
  - 针对小规模的网页搜索(如百万量级)，可利用建立在内存中的DNS映射，既能加快网页信息的获取，后能降低对于DNS服务器的压力。
- [x] DNS缓存的内容
  - Internet的DNS系统会定期刷新，交换更新的域名和IP信息
  - 缓存中有部分信息过期影响不大，但注意要适度刷新

###### **预取 prefetch client**

- [x] 为了减少等待查找涉及新主机的地址的时间，尽早将主机名投给DNS系统
- [x] 与缓存系统的区别：缓存 – 用了才缓存；预取 – 不用也暂时先缓存
- [x] DNS预取的基本步骤
  - 分析刚刚得到的网页
  - 从<href>属性中提取主机名
  - 向缓存服务器提交DNS解析请求
  - 结果存放在DNS缓存中(也可能用上，也可能用不上)

<!-- tabs:end -->

##### **URL**

- [x] URL的基本概念
  - 统一资源定位符(Universal Resource Locator)
    - 以某种统一的(标准化的)方式标识资源的简单字符串。
  - URL一般由四部分组成：
    - 访问资源的模式/协议。
    - 存放资源的主机名。
    - 资源自身的名称，由路径表示。
    - 被访问的文件名或主页名。

- [x] URL与IP地址的对应关系
  - 一般而言，域名与IP地址处于一一对应的关系
  - 实际情况下，域名与IP地址之间存在复杂的对应关系
    - 一对一：基本的对应关系
    - 一对多：可能由于虚拟主机导致，使得多个URL映射到同一IP
      - 例如，www.pku.edu.cn / www.gh.pku.edu.cn 等都映射到162.105.129.12上，但由于各个站点内容不同，所以被认为是不同的Web服务器
    - 多对一：可能由于DNS轮询导致，以应对商业站点的负载问题
      - 例如，多个182.61.200.x均与www.baidu.com 映射。
      - 奇怪的案例：输入www.玩原神玩的.com会跳转到我校主页(谁干的!?)

- [x] URL链接提取与规范化
  - 目标：得到网页中所含URL的标准型
    - URL的处理与过滤，避免多次获得不同URL指向的相同网页
    - 相对URL：基础URL被省略，需要进行补齐
  - URL的不规范现象
    - 不同URL可能指向同一个网页
    - URL的格式存在错误或无用内容
      - 多余的文件名(如index.html)，无用的查询变量或空的查询条件
    - 动态网页与动态参数
    - <span style="color:blue;">短链接</span>

- [x] 一些URL规范化的操作
  - URL的基本组成：协议:// 主机名[: 端口]/ 路径/[: 参数] [? 查询]#Fragment
    - protocol ://hostname[:port]/path/ [;parameters][?query]#fragment
  - 一些常见的URL规范化示例
    - URL协议名和主机名的小写化
      > - HTTP://WWW.BAIDU.COM -> http://www.baidu.com
    - 删除Fragment（#）或多余的查询串，如?，&
      > - http://www.example.com#seo -> http://www.example.com
    - 删除默认后缀或多余的www
      > - http://www.example.com/index.html -> http://example.com

<!-- tabs:end -->

#### **Sitemap，站点地图**

- [x] 放在服务器根目录中的sitemap.xml，为爬虫指明抓取的建议
  - 协助爬虫找到隐藏的网页(如需要查询或表单才能够访问的内容)
  - Changefreq属性还提供有关更新频率的说明，以协助保障时新性

<p align="center">
  <img src="./img/Sitemap.png" alt="Sitemap">
</p>

- [x]  案例：中央政府门户网站的站点地图-百度版本(http://www.gov.cn/baidu.xml)

<p align="center">
  <img src="./img/Sitemap1.png" alt="Sitemap">
</p>

#### **Robots Exclusion，排斥协议**

- [x] Sitemap是允许协议，而Robots是排斥协议
- [x] 在服务器文档根目录中的文件robots.txt，包含一个路径前缀表，描述了服务器给出的抓取限制
- [x] 例如，腾讯新闻的Robots.txt(news.qq.com/robots.txt)

<p align="center">
  <img src="./img/排斥协议.png" alt="排斥协议">
</p>

- [x] 案例：中央政府门户网站的Robots.txt(www.gov.cn/robots.txt)

<p align="center">
  <img src="./img/排斥协议1.png" alt="排斥协议">
</p>

- [x] 该限制只针对爬虫，一般浏览不受影响
- [x] 该限制属于“君子协定”，没有强制执行力
  - 但目前，绝大多数搜索引擎都遵守该限制

<p align="center">
  <img src="./img/排斥协议2.png" alt="排斥协议">
</p>

<!-- tabs:end -->

## 面向API的新爬虫任务

### API的基本概念

- [x] 应用程序接口(Application Programming Interface)
- [x] 2000年，Salesforce和eBay推出了自己的API，程序员可以访问并下载一些公开数据。从那时起，许多网站都提供API用于访问公共数据库。
- [x] 通过开放的API 来吸引更多的用户和更多的创意，与具备分享、标准、去中心化、开放、模块化的Web 2.0时代相得益彰，为创造者和平台都带来价值。
- [x] 同时，网页API也为开发人员提供了一种更友好的网络爬虫方式：
  - 直接获取资源列表，清晰、明确
  - 接收JSON或XML等格式化数据的反馈

### 基于API的数据爬取示例

- [x] 基于豆瓣提供的API，获得评分最高的20部电影信息

<p align="center">
  <img src="./img/基于API的数据爬取示例.png" alt="基于API的数据爬取示例">
</p>

### 基于API的数据爬取一般流程

<p align="center">
  <img src="./img/基于API的数据爬取一般流程.png" alt="基于API的数据爬取一般流程">
</p>

> 其中，第3-4步可能存在循环，即通过获得某个资源ID对应的详细信息，获得更多其他资源ID，并继续抓取更多信息。

### Token的概念、作用与取得方式

- [x] API的调用需要用户身份认证(用户授权)，而Token相当于授权后的通行证
- [x] 使用Token认证而非用户名/密码认证方式的优点
  - `Token` 的生成完全独立于帐号密码，往来通信不会影响账号安全
  - 即使 `Token` 丢失或泄露，只需登录后台删除该Token即可

<p align="center">
  <img src="./img/Token.png" alt="Token">
</p>

> 目前微博的API认证授权机制

### 结构化数据反馈

<!-- tabs:start -->

#### **XML**

- [x] 可扩展标记语言(Extensible Markup Language)
  - 是一种允许用户对自己的标记语言进行定义的源语言。
  - 提供统一的方法来描述和交换独立于应用程序的结构化数据。
- [x] XML相比于HTML的优势所在：
  - 可扩展性方面：HTML不允许用户自行定义标识或属性，而在XML中，用户能够根据需要自行定义新的标识及属性名。
  - 结构性方面：HTML不支持深层的结构描述，XML的文件结构嵌套可以复杂到任意程度，能表示面向对象的等级层次。
  - 可校验性方面：HTML没有提供规范文件以支持结构校验，而XML文件可以包括一个语法描述，使应用程序可以对此进行结构校验。

<p align="center">
  <img src="./img/XML.png" alt="XML">
</p>

- [x] 必须有XML声明语句作为文档开头
- [x] 良好的XML文档有且只有一个根节点
  - 例如，在本实例中为 `item`
- [x] 可根据需要嵌套文件结构
  - 例如， `<venue>` 中包含 `<city>` 信息
- [x] 所有的标记必须有相应的结束标记
  - 例如， `<zip>` 与 `</zip>` 的成对出现
  - 注意，所有的空标记也必须被关闭

#### **JSON**

- [x] JS 对象表示法(JavaScript Object Notation)
  - 轻量级的数据交换格式，采用完全独立于编程语言的文本格式。
  - 简洁和清晰的层次结构使得 JSON 成为理想的数据存储和交换语言。
  - 易于人阅读和编写，同时也易于机器解析，并有效地提升网络传输效率。

```json
"name":"Michael",
"address":
{
  "city": "Beijing",
  "street": "Chaoyang Road",
  "postcode": 100025
}
```

- [x] JSON中的六大构造字符
  - “[”“]”表示数组开始/结束
  - “{”“}”表示对象开始/结束
  - “:”表示名称的分隔符，“,”表示值的分隔符
  - 从内容表示上看，JSON更为轻量，但在无缩进情况下层次化解析相对困难

#### **JSON与XML的区别**

- [x] XML的优点：格式统一、标准，容易与其他系统进行远程交互，方便共享
- [x] XML的缺点：文件庞大，文件格式复杂，解析复杂且方式繁多，工作量大
- [x] JSON的优点
  - 数据格式比较简单，易于读写，格式经过压缩，占用带宽小；
  - 支持多种语言，易于解析，可以简单的进行数据的读取；
  - 能直接为服务器端代码使用，大大简化了开发和维护工作。

- [x] XML与JSON格式对比

```xml
<?xml version="1.0" encoding="utf-8"?>
<root>
  <resultcode>200</resultcode>
  <reason>Return Successed!</reason>
  <result>
    <area>江苏省苏州市</area>
    <location>电信</location>
  </result>
</root>
```

```json
{
  "resultcode": "200",
  "reason": "Return Successed!",
  "result":{
    "area": "江苏省苏州市",
    "location": "电信"
  }
}
```

<!-- tabs:end -->

## 常见的爬虫算法

### 最最基础的算法

<!-- tabs:start -->

### **最最基础的算法**

```algorithm
\begin{algorithm}
\caption{SPIDER}
\begin{algorithmic}
\PROCEDURE{SPIDER}{$G$}
  \STATE Let root $:=$ any URL from $G$
  \STATE Initialize Stack <stack data structure>
  \STATE Let Stack $:=$ Push(root, Stack)
  \STATE Initialize Collection <big file of URL-page pairs>
  \WHILE{Stack is not empty}
    \STATE current\_URL $:=$ Pop(Stack)
    \STATE page $:=$ look-up(current\_URL)
    \STATE Store(<current\_URL, page>, Collection)
    \FOR{every URL\_i in page}
      \STATE Push(URL\_i, Stack)
    \ENDFOR
  \ENDWHILE
  \STATE Return Collection
\ENDPROCEDURE
\end{algorithmic}
\end{algorithm}
```

- [x] 潜在风险：
  - 重复收集的问题？
  - 回路或不连通的解决方法？
  - 如何控制搜集特定的一部分？

### **最最基础的改进算法**

```algorithm
\begin{algorithm}
\caption{SPIDER}
\begin{algorithmic}
\PROCEDURE{SPIDER}{$G$, \{SEEDS\}}
  \STATE Initialize Collection <big file of URL-page pairs>
  \STATE Initialize Visited <big hash-table>
  \FOR{every root in \{SEEDS\}}
    \STATE Initialize Stack <stack data structure>
    \STATE Stack $:=$ Push(root, Stack)
    \WHILE{Stack is not empty}
      \REPEAT
        \STATE current\_URL := Pop(Stack)
      \UNTIL{current\_URL is not in Visited}
      \STATE Insert\_hash(current\_URL, Visited)
      \STATE page := look-up(current\_URL)
      \STATE Store(<current\_URL, page>, Collection)
      \FOR{every URL\_i in page}
        \STATE Push(URL\_i, Stack)
      \ENDFOR
    \ENDWHILE
  \ENDFOR
  \STATE Return Collection
\ENDPROCEDURE
\end{algorithmic}
\end{algorithm}
```

- [x] 解决方案：
  - 利用BigTable排除重复部分
  - 基于种子集合控制爬取内容
  - 通过更换种子重启动解决回路等

<!-- tabs:end -->

### 重复性的监测问题

- [x] 不仅URL本身可能重复，即使不同URL，也可能导致相似的文档内容
- [x] 完全重复文档的检测方法
  - 检验和(Checksumming)，所有字节进行加和，相同文档有相同检验和
  - 缺陷：相同检验和不代表相同(如打乱顺序)
- [x] 近似重复文档的检测方法：指纹表示法
  1. 对文档进行分词处理，并进行n-gram组合
  2. 挑选部分n-gram用于表示这一文档
  3. 对被选中的n-gram进行散列，以提升检索效率和减少指纹大小
  4. 存储散列值作为文档指纹，通常存储在倒排索引中

#### 遍历策略

<!-- tabs:start -->

##### **广度优先算法**

<p align="center">
  <img src="./img/广度优先算法.png" alt="广度优先算法">
</p>

> 本质是维持一个URL队列，先进先出

```algorithm
\begin{algorithm}
\caption{SPIDER}
\begin{algorithmic}
\PROCEDURE{SPIDER}{$G$, \{SEEDS\}}
  \STATE Initialize Collection <big file of URL-page pairs>/ // 存储URL-页面对的集合
  \STATE Initialize Visited <big hash-table> // 存储已访问的URL
  \FOR{every root in \{SEEDS\}}
    \STATE Initialize Queue <queue data structure>// 待爬取的URL队列
    \STATE Let Queue $:=$ EnQueue(root, Queue)
    \WHILE{Queue is not empty}
      \REPEAT
        \STATE current\_URL $:=$ DeQueue(Queue)
      \UNTIL{current\_URL is not in Visited}
      \STATE Insert\_hash(current\_URL, Visited)
      \STATE page $:=$ look-up(current\_URL)  // 爬取页面
      \STATE Store(<current\_URL, page>, Collection)
      \FOR{every URL\_i in page} 
        \STATE EnQueue(URL\_i, Queue) // 链接提取
      \ENDFOR
    \ENDWHILE
  \ENDFOR
  \STATE Return Collection
\ENDPROCEDURE
\end{algorithmic}
\end{algorithm}
```

##### **深度优先算法**

<p align="center">
  <img src="./img/深度优先算法.png" alt="深度优先算法">
</p>

> 本质是维持一个URL栈，先进后出

```algorithm
\begin{algorithm}
\caption{SPIDER}
\begin{algorithmic}
\PROCEDURE{SPIDER}{$G$, \{SEEDS\}}
  \STATE Initialize Collection <big file of URL-page pairs>// 结果存储
  \STATE Initialize Visited <big hash-table> // 已访问URL列表
  \FOR{every root in \{SEEDS\}}
    \STATE Initialize Stack <stack data structure> // 待爬取的URL栈
    \STATE Let STACK $:=$ Push(root, Stack)
    \WHILE{Stack is not empty}
      \REPEAT
        \STATE current\_URL $:=$ Pop(Stack)
      \UNTIL{current\_URL is not in Visited}
      \STATE Insert\_hash(current\_URL, Visited)
      \STATE page $:=$ look-up(current\_URL) // 爬取页面
      \STATE Store(<current\_URL, page>, Collection)
      \FOR{every URL\_i in page} 
        \STATE Push(URL\_i, Stack) // 链接提取
      \ENDFOR
    \ENDWHILE
  \ENDFOR
  \STATE Return Collection
\ENDPROCEDURE
\end{algorithmic}
\end{algorithm}
```

##### **广度 or 深度优先算法**

- [x] 对于一般的网页爬虫而言，在 <span style="color:blue;">时间无限</span> 的情况下，两种算法可以视作等价
- [x] 假如在<strong style="color:red;">有限步</strong> 条件下，两者的优劣如何？
  - 如果希望获得更为多样化的内容，应采用广度优先
  - 如果希望获得更为深层次的信息，应结合路径选择采用深度优先
    - 部分站点需要深层次浏览以判断站点信息质量
- [x] 此外，不同的<strong style="color:blue;">应用场景</strong>，对两种算法的适应度可能不尽相同
  - 以社交网络场景为例，广度优先有着以下特点：
    - 通常而言，选择度数较高的起点，可以快速到达大量节点
    - 但全局性不佳，难以反映网络全貌
    - 另外，此类采样所得节点的度数往往虚高
    - Facebook网络，随机抽样平均度94，广度优先抽样竟达324

##### **从遍历要求到网页本身重要性的要求**

- [x] 需要对网页的重要性进行评估，进而优先搜集重要的网页
- [x] 根据经验，体现网页重要度的常见特征类别：
  - 启发式特征(简单统计指标)
    - 如，入度、父网页入度、镜像度、较小的目录深度(易于浏览)
  - 结构性特征
    - 如，PageRank/HIT值，各类Betweeness值等
    - 主题类特征(反应网页与特定需求的契合程度)

<!-- tabs:end -->

## 常见反爬虫机制与应对策略

- [x] 有爬虫，就有反爬虫
- [x] 使用任何技术手段，阻止别人批量获取自己网站信息
  - 顺便，大家也一起来当一下免费的数据标注员

> - 常见反爬虫策略及其应对策略如下

<!-- tabs:start -->

### **User Agent**

- [x] 最常见的反爬虫策略，利用访问网站时浏览器发布的Request Headers信息中的User-Agent信息，判断用户使用何种方式浏览

<p align="center">
  <img src="./img/User-Agent.png" alt="User Agent">
</p>

- [x] 示例代码如下:

```python
# 命名为 UA.py
import requests
html = request.get("https://zhihu.com").content
print(html.decode())
```

> 运行结果如下

```term
$ python UA.py
{"error":{"message":"您当前请求存在异常，暂时限制本次访问","code":40362}}
```

>  - 爬虫往往U-A部分为空

- [x] 应对策略：利用Python的Request库允许用户自定义请求头信息的手段
  - 在请求头信息中将 <kbd style="color:blue;">User-Agent</kbd> 的值改为浏览器的请求头标识，从而绕开反爬虫机制

- [x] 示例如下

```python
# 命名为 UA_new.py
import requests
# 伪造请求头信息 欺骗服务器
headers = {"User-Agent":"Mozilla/5.0 (Macintosh; Inter Mac OS X 10.13; rv:9527.0) Gecko/20100101 Firefox/9527.0"}
resp = requests.get("https://zhihu.com", headers = headers)
print(resp.status_code) # 不打印内容是因为过长
```

> 运行结果如下

```term
$ python UA_new.py
200
// HTTP回应200说明抓取响应成功
```

### **IP/账号访问次数/频率**

- [x] 通过限制特定IP地址/账号访问频率和次数进行反爬
  - 其本质在于判断浏览行为是否是人类行为
- [x] 应对手段：
  - 构造 <strong style="color:blue;">IP代理池</strong> ，然后每次访问时随机选择代理
    - Github中有相关服务，通过各种提供免费IP的网站来提供代理池
  - 每次爬取行为后间隔一段时间
  - 注册多个账号以保障数据收集
    - 挑战：账号本身的成本问题、账号被查封的危险

### **验证码**

- [x] 通过各类验证码，判断浏览者属于人类还是机器
- [x] 应对手段：
  - 简单的字符识别：基于机器学习与模式识别相关技术
  - 复杂的逻辑推理：人工辅助破解

### **动态网页**

- [x] 从网页的url加载网页的源代码之后，会在浏览器里执行JavaScript程序
  - 网页内容由脚本加载，而直接抓取则只能得到空白页面
  - 此类情况在抓取在线播放的音视频文件时尤为常见
- [x] 应对手段：
  - 核心思路：模拟调用请求
  - 使用审查元素分析ajax请求，如此循环直到获得包含数据信息的json文件

### **加密-解密技术**

- [x] 对网页中的关键信息进行加密或混淆，来增加
- [x] 一类常见案例：页面上显示为正常文本，而源代码中为编号
  - 网页加载时需要借助字体库，将编码转为文字
    - 字体库/映射可以动态更新！
    - 解决方法：
      - 通过抓包获取字体库/映射
      - 基于映射进行解码

<p align="center">
  <img src="./img/加密-解密技术.png" alt="加密-解密技术">
</p>

### **蜜罐技术**

- [x] 网页上会故意留下一些人类看不到或者绝对不会点击的链接。由于爬虫会从源代码中获取内容，所以爬虫可能会访问这样的链接
- [x] 只要网站发现有IP访问这个链接，立刻永久封禁访问者，从而难以继续爬取
- [x] 应对手段：
  - 核心思路：干涉爬虫路径
  - 通过工具库判断页面上的隐含元素，使爬虫避开这些元素，可以部分回避蜜罐的诱导。

### **用户权限限制**

- [x] 不同类型/级别的用户给予不同的内容权限
  - VIP、SVIP、蓝钻、红钻、绿钻、各种钻……
- [x] 应对手段：
  - 氪金，就可以变强

### **其他的反爬虫策略**

- [x] 不同的网页结构：每个相同类型的页面的源代码格式均不相同
- [x] 同样也是双刃剑：增加爬取难度的同时降低用户浏览体验(逼死强迫症)
- [x] 多模态的呈现方式：文字转为图像或视频
- [x] 应对策略：OCR、语音识别、图像/视频标签技术

<!-- tabs:end -->










