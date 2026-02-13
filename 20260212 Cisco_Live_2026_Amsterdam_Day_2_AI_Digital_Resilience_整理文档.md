# Cisco Live 2026 Amsterdam：Day 2 | AI & Digital Resilience

## 视频基本信息

| 项目 | 内容 |
|------|------|
| **视频标题** | Cisco Live 2026 Amsterdam: Day 2 \| AI & Digital Resilience |
| **视频链接** | https://www.youtube.com/watch?v=cBAoWoFYJ7w |
| **发布时间** | 2026年2月12日 |
| **视频时长** | 8小时29分56秒 |
| **频道** | Cisco（42万订阅者） |
| **活动名称** | Cisco Live EMEA 2026（2026年2月9日-13日，荷兰阿姆斯特丹） |
| **直播日期** | 2026年2月11日（星期三，大会第二天） |
| **主持人** | Steve Multer（主持）、Robb Boyd（展厅记者）、Amy Vertannes（演播室主持）、Cedric De Vylder（展厅记者） |
| **内容形式** | 全天直播，包含Center Stage演讲、演播室访谈、展厅深度报道、客户案例、产品演示 |

---

## 目录

1. [核心观点与主题](#核心观点与主题)
2. [Splunk与数字韧性](#splunk与数字韧性)
3. [能源网络系统：Fault Managed Power与液冷技术](#能源网络系统fault-managed-power与液冷技术)
4. [Cisco Spaces：智能空间导航](#cisco-spaces智能空间导航)
5. [AI自动化之旅：MCP、Circuit与AgenticOps](#ai自动化之旅mcpcircuit与agenticops)
6. [DevNet Zone深度报道](#devnet-zone深度报道)
7. [工业现代化加速：IoT安全与Cyber Vision](#工业现代化加速iot安全与cyber-vision)
8. [客户案例：Schiphol机场与Carl Zeiss](#客户案例schiphol机场与carl-zeiss)
9. [工业IoT制造演示](#工业iot制造演示)
10. [客户体验：TUI Cruises邮轮网络](#客户体验tui-cruises邮轮网络)
11. [协作设备：Room Kit Pro G2与Distance Zero](#协作设备room-kit-pro-g2与distance-zero)
12. [未来办公空间：Wi-Fi 7与智能建筑](#未来办公空间wi-fi-7与智能建筑)
13. [Connected Intelligence：Webex翻译代理与联络中心](#connected-intelligencewebex翻译代理与联络中心)
14. [安全深度专题：Agents on the Wire](#安全深度专题agents-on-the-wire)
15. [安全运营中心（SOC）实战](#安全运营中心soc实战)
16. [合作伙伴专题：Orange Business与后量子密码学](#合作伙伴专题orange-business与后量子密码学)
17. [合作伙伴专题：NetApp与FlexPod](#合作伙伴专题netapp与flexpod)
18. [ThousandEyes与DHL网络保障](#thousandeyes与dhl网络保障)
19. [AI网络：Nexus AI Fabric Intelligence与Silicon One](#ai网络nexus-ai-fabric-intelligence与silicon-one)
20. [合作伙伴专题：AMD与UEC标准](#合作伙伴专题amd与uec标准)
21. [Cisco IQ：AI驱动的服务平台](#cisco-iqai驱动的服务平台)
22. [Day 2总结：AI的三大挑战](#day-2总结ai的三大挑战)
23. [关键语录](#关键语录)
24. [术语表](#术语表)

---

## 核心观点与主题

Cisco Live EMEA 2026第二天围绕"AI时代的关键基础设施"展开，涵盖数据中心、协作、安全、工业网络等全栈技术。CEO Jeetu Patel在前一天主题演讲中提出的三大AI挑战——**基础设施约束、信任赤字、数据鸿沟**——贯穿全天讨论。

| 主题领域 | 核心观点 | 关键发布/公告 |
|---------|---------|-------------|
| **能源与可持续性** | AI对电力的需求正在重塑数据中心和建筑设计，需要革命性的供电技术 | Fault Managed Power（FMP）试点套件发布，直接液冷交换机，Unified Edge浸没式冷却原型 |
| **AI自动化与代理** | Model Context Protocol（MCP）正在革命性地改变AI与现有系统的集成方式 | Circuit（Cisco内部GenAI工具）、Agent as a Service、MCP服务器生态 |
| **工业IoT安全** | 75%的数据产生于工业环境，OT/IT融合是AI时代的关键挑战 | Cyber Vision集群分析、19款新工业交换机、Wi-Fi 7工业网络 |
| **协作与Connected Intelligence** | 协作已成为关键基础设施，需要人与AI、AI与AI的多层智能 | Room Kit Pro G2（含NVIDIA计算模块）、Webex Translator Agent（实时语音翻译）、ServiceNow集成 |
| **安全** | AI时代需要全新的安全基础，代理需要身份、行为监控和护栏 | Hybrid Mesh Firewall AI就绪化、Live Protect（eBPF防护）、Splunk Enterprise Security、AI Defense扩展至代理保护 |
| **AI网络** | AI应用对网络有根本不同的需求——海量数据、高功耗、对延迟敏感 | Cisco Silicon One G300（64×1.6T）、液冷系统、Nexus One/HyperFabric、AgenticOps with AI Canvas |
| **服务与平台** | 服务正从被动响应转向个性化、预测性和主动性 | Cisco IQ平台、Support Signature GA、Services as Code、后量子密码学评估、AI驱动故障排除 |

---

## Splunk与数字韧性

### 演播室访谈：James Hodge（Splunk）

**主持人**：Amy Vertannes
**嘉宾**：James Hodge（Splunk）

James Hodge介绍了Splunk在Cisco生态中的定位，强调"One Cisco"战略下的创新：

- **Cisco Data Fabric**：整合Cisco基础设施数据，提供端到端可观测性
- **MCP服务器集成**：在可观测性堆栈上部署MCP服务器，实现与AI代理的集成
- **行为分析与自动化**：将分析器、自动化、行为分析等产品捆绑在一起

### 数字韧性的定义

> **James Hodge**："数字韧性让我们能够在功能层面、服务层面和业务层面审视一切，从检测和响应转向预测和预防，让你不会经历糟糕的数字体验日。"

### 展厅演示：Splunk数据可视化

**嘉宾**：Bruce（Splunk技术营销总监）

在展厅Splunk展位上，Bruce展示了Splunk作为数据摄取和可视化平台的能力：

- **AI/LLM运营仪表板**：追踪成本、请求量、模型利用率
- **基础设施监控**：监控运行AI系统的服务器的HVAC系统，识别过热服务器
- **统一视图**：将应用数据、数据中心基础设施和网络数据关联在一起

---

## 能源网络系统：Fault Managed Power与液冷技术

### Center Stage演讲

**演讲者**：Denise Lee（VP of Engineering & Sustainability Office，Cisco）

Denise Lee以全球七周四大洲的行业调研为背景，阐述了AI时代面临的能源挑战，并介绍了Cisco的能源网络系统战略。

### 核心技术：Fault Managed Power（FMP）

> **Denise Lee**："你即将听到的是一项革命性技术。自从Edison和Tesla辩论交流电与直流电以来，45年来首次出现的全新电力等级——Class Four Fault Managed Power。"

FMP的三个核心组件：

- **发射器**（Transmitter）
- **电缆**（Cable）
- **接收器**（Receiver）

**技术特性**：
- 脉冲电力（Pulse Power），触摸安全
- 高压直流，最高450V DC
- 与PoE相同的布线方式
- UL认证已获得

### 数据中心液冷技术

| 冷却方式 | 特点 | 适用场景 |
|---------|------|---------|
| **传统风冷** | 约10kW/机架，40-50%能源用于冷却 | 传统数据中心 |
| **直接液冷（Direct to Chip）** | 可达150kW+，需要大量软管和泵 | 改造型数据中心 |
| **浸没式冷却（Immersion）** | 无运动部件，静音，无需热/冷通道 | 新建AI数据中心 |
| **后门热交换器** | 与直接液冷结合使用 | 改造型项目 |

### 关键数据

- 5MW风冷数据中心应用直接液冷+FMP：**节省76%能源成本**
- 等效于**2.3倍的计算能力**
- FMP在园区部署中的实际案例：**20%资本支出节省、22%劳动力成本节省、78%年度维护成本节省**
- 阿姆斯特丹电网连接时间：**10-13年**
- 40%计划中的数据中心将因电力限制而延迟

### 新产品发布

- **直接液冷交换机**：基于Nexus系列的液冷版本
- **Cisco Unified Edge浸没式冷却原型**：在展厅展示，适用于粗糙环境、制造环境和边缘推理
- **FMP试点套件项目**：未来九个月内向战略客户提供概念验证套件

### Denise Lee的建议

> "我给IT专业人士的建议是：找到你们公司的设施、房地产和运营人员，请他们喝杯咖啡，讨论一下未来的规划。如果IT和设施团队不协作，我们就会错失让事情更高效、更可持续的机会。"

---

## Cisco Spaces：智能空间导航

### 演播室讨论与视频展示

**主持人**：Steve Multer、Amy Vertannes
**展示者**：Katrina（Cisco展厅Storyteller）

Cisco Spaces将基础设施转化为传感器，实现室内空间的映射、分析和管理：

- **展厅导航**：基于Spaces的3D地图，帮助参会者搜索和定位展示、演示和会议
- **会议室管理**：实时查看房间占用状态、人数、温度等信息
- **智能建筑应用**：传感器数据驱动更智能、更高效的空间运营
- **Storyteller计划**：6名引导员配合3块交互式展板，帮助参会者连接正确的信息和人员

---

## AI自动化之旅：MCP、Circuit与AgenticOps

### Center Stage演讲

**演讲者**：
- Shannon McFarland（VP DevNet & OSPO，Cisco）
- Sujith Joseph（Principal Engineer，Cisco AI and Automation Center）

### Model Context Protocol（MCP）——AI集成的"入门药物"

Shannon McFarland阐述了如何在现有的棕地环境中逐步引入AI：

> "Model Context Protocol允许你充当AI世界与现有环境之间的代理或网关——你的API、文件系统、数据库。我们可以利用MCP而无需重构或升级已有的原生系统。"

**MCP部署模式**：
1. 为每个流水线资产部署MCP服务器（GitHub、CircleCI、Kubernetes等）
2. 添加可观测性以追踪AI操作的有效性
3. 在IDE中实施规则（Rules）以确保代理行为受控
4. 逐步引入自主/半自主代理

### Circuit——Cisco内部GenAI应用

Sujith Joseph演示了Circuit，Cisco的内部AI工具：

- **定位**：类似ChatGPT/Gemini，但专为Cisco员工定制
- **规模**：
  - 超过**100,000名用户**
  - 日均**125,000条用户提示**
  - 处理**3.25亿次LLM请求**
  - 累计处理**1.45万亿token**（含提示和补全）
  - **6,200个团队**使用该服务
- **功能**：
  - 支持多种领先LLM模型选择
  - 默认编排模式（自动路由至正确代理）
  - 访问Web数据和内部数据
  - Agent Hub（代理注册中心）
  - Agent Studio（无代码AI代理创建工具）
  - RAG as a Service（基于OneDrive内容索引）
  - Prompt库（个人/团队/组织级别共享）
  - 内置Prompt Optimizer
  - 与Cisco AI Defense集成的安全层

### Agent as a Service

- 无代码工具，指定需求即可自动生成代理
- 自动化代码审查和修复
- 集成调试模式和全程追踪
- 支持所有注册的MCP服务器和工具

### 关键架构洞察

> **Sujith Joseph**："如果你想在企业内实现真正的自动化，需要三件事：一是确保企业内有AI就绪的数据；二是确保企业使用的工具或API有MCP接口；三是将这些服务器汇聚到一个超级代理上，让它们相互对话、相互构建。这将带来企业内的指数级创新。"

---

## DevNet Zone深度报道

### 展厅采访

**记者**：Robb Boyd
**嘉宾**：Matt（Head of Strategy for DevNet Program）

DevNet Zone本周的重点：

- **AI辅助编程入门**：利用AI工具帮助不会编程的人克服入门障碍
- **热门主题**：自动化和可编程性在网络运维、计算运维中的实际应用
- **新增AI层**：将AI与传统自动化结合，提供实践赋能
- **Lab Studio**：新增引导式实验室，涵盖NSO、Meraki、Security Cloud Control、AI自动化等

> **Matt**："AI的信息是：这些工具可以帮助你克服入门障碍。学习编程对不会编程的人来说不容易，但我们可以用这些工具开始构建应用程序、构建集成、扩展和使用Cisco平台的API。"

---

## 工业现代化加速：IoT安全与Cyber Vision

### Center Stage演讲

**演讲者**：Samuel Pasquier（VP Industrial IoT Product Management，Cisco）
**客户嘉宾**：
- Patrick Koks（Schiphol Airport，架构师）
- Akis Mystiroudis（Carl Zeiss，网络与连接团队负责人）

### 物理AI与工业网络

Samuel Pasquier阐述了从聊天机器人时代→代理式AI→物理AI的演进路径：

- **物理AI**：机器人和物理设备在工业环境中运行，需要本地数据中心作为"大脑"，网络作为连接物理"手臂"和"大脑"的神经系统
- **75%的数据产生于工业环境**——机器、变电站等场所
- 过去一年推出**19款新工业交换机**

### OT安全三步策略

| 步骤 | 目标 | 工具/方法 |
|------|------|---------|
| **可见性**（See） | 发现所有连接设备和通信模式 | Cisco Cyber Vision |
| **保护**（Protect） | 实施分段，隔离威胁横向移动 | 网络分段策略 |
| **远程访问**（Secure Access） | 安全的供应商远程访问 | 零信任远程访问 |

### Cyber Vision集群分析

Cyber Vision通过AI驱动的聚类技术，将复杂的网络发现结果转化为可操作的视图：

- 原始发现：齿轮箱工厂中的所有通信模式（过于复杂，不可操作）
- AI聚类后：清晰展示谁在与谁通信，可视化表示整个环境
- 基于此可以开始实施分段策略

---

## 客户案例：Schiphol机场与Carl Zeiss

### Schiphol Airport

**嘉宾**：Patrick Koks（架构师）

- 欧洲最繁忙的机场之一，年客流量超过**6,800万**
- 日处理旅客量高达**25万人**
- 24/7运营，行李分拣、飞机处理、安检等OT域中的任何问题都会影响整个机场运营
- 面临的挑战：多个OT域和供应商带来的"网络中的网络"可见性问题

### Carl Zeiss

**嘉宾**：Akis Mystiroudis（Head of Network & Connectivity，Corporate IT）

- 全球领先的光学和光电子公司，**46,000+员工**，覆盖**50+国家**
- 业务涵盖消费类产品（眼镜、相机镜头）、医疗技术、工业测量、半导体制造
- 挑战：OT环境曾经隔离，现在需要IT/OT融合以访问数据
- 使用Cyber Vision获得OT环境可见性，了解机器间通信模式

---

## 工业IoT制造演示

### 展厅演示

**记者**：Cedric De Vylder
**嘉宾**：Ruben Lobo（Director of IoT，Cisco）

展厅展示了一个完整的工业制造场景演示：

- **AI视觉系统**：使用摄像头和AI检测制造过程中的质量问题（如冰球制造）
- **Splunk仪表板**：实时可视化制造数据
- **Cisco工业交换机**：连接所有传感器和设备
- **端到端集成**：从传感器到数据分析的完整数据流

---

## 客户体验：TUI Cruises邮轮网络

### 演播室访谈

**记者**：Robb Boyd
**嘉宾**：Gordon（CIO，TUI Cruises）、Cisco CX SVP of Engineering

邮轮网络面临的独特挑战：

- 海上环境中的网络连接
- 使用**Open Roaming**技术
- 集成**Cisco Spaces**实现船上导航
- **数字孪生**技术用于船舶管理
- CX团队为复杂部署提供支持

---

## 协作设备：Room Kit Pro G2与Distance Zero

### Center Stage演讲

**演讲者**：Espen Loberg（VP/GM Collaboration Devices，Cisco）
**客户嘉宾**：Darius Langner（Senior Director of Workplace，Adidas）

### Room Kit Pro G2——核心发布

与NVIDIA联合设计的全新计算模块：

- **NVIDIA AI计算模块**：892个组件，30,000个微连接
- **AI计算能力**：比上一代提升**25倍**
- **AV over IP架构**：一根电缆传输媒体、控制和电源
- **支持多达7个4K摄像头和8个Pro麦克风**
- **实时空间感知**：AI驱动的说话人追踪和电影级视图切换
- **Control Hub全面管理**：所有设备和配件的实时分析和远程排障
- **2026年4月发货**

### 其他新产品

- **Desk Pro G2**：新一代桌面协作设备
- **Wireless Phone 9821**：无线话机
- **Samsung合作**：所有Samsung认证显示器纳入Cisco Workspace Designer
- **Control Hub AgenticOps集成**：支持Microsoft Copilot、Amazon等AI平台

### 演播室深度访谈：Room Kit Pro G2设计

**嘉宾**：Agustin（Room Kit Pro G2设计师）

设计亮点：
- 比前代轻近**三分之一**
- 极简设计理念：只保留必要元素
- 冲压金属纹理：兼顾美观和结构强度
- 所有端口（包括模拟端口）在Control Hub中完全可见

---

## 未来办公空间：Wi-Fi 7与智能建筑

### 展厅深度报道

**记者**：Robb Boyd
**嘉宾**：Erik Magnusson

未来办公空间的关键要素：

- **Wi-Fi 7**结合网络、安全、可观测性和协作
- **智能建筑**：温度自动调节、人数统计、空间利用率分析
- **室内导航（Wayfinding）**：帮助员工和访客快速找到目的地
- **Return to Office**：创造"体验磁铁"式的办公环境
- **开放生态**：支持Microsoft Teams等第三方平台
- **零接触部署**：简化大规模设备安装

> **Erik Magnusson**："我们正在为一个人类、机器人和AI无缝协作的世界做准备。Cisco是唯一将网络、安全、可观测性和协作设备结合在一起的公司。"

---

## Connected Intelligence：Webex翻译代理与联络中心

### Center Stage演讲

**核心团队**：
- Snorre Kjesbu（SVP Collaboration，Cisco）
- Amit Barave（Webex）
- Vinod Muthukrishnan（Contact Center）
- Aruna Ravichandran
- Espen Loberg

### Webex Translator Agent——核心发布

**实时语音到语音翻译**，保留说话者的自然声音和语调：

> **Amit Barave**："我们看到AI将文本翻译成数百种语言，将录制音频翻译成数百种语言。但我们还没有看到实时语音到语音翻译——当我说英语时，你用德语或西班牙语实时听到我的声音和语调。"

- 现场进行了**英语-西班牙语实时演示**（大获成功）
- 将支持Webex Calling、Meetings和Contact Center
- 非传统的"语音→文本→翻译→语音"流程，而是**直接语音到语音**

### Microsoft Copilot × Webex集成

- Webex内容（会议、录制）在Microsoft Copilot中可搜索
- SharePoint文档、OneDrive文件、Teams消息在Webex AI Assistant中可搜索
- 跨平台AI查询能力

### 安全与合规

- **零信任安全**：端到端加密，客户可自持加密密钥
- **Pin Drop检测**：已在Meetings中可用，即将扩展至Calling
- **Webex Compliance Hub**：全平台合规管理
- **英国数据驻留**：新增英国区域数据存储和处理

### ServiceNow合作——Webex Contact Center集成

**嘉宾**：Radhika Josyula（Global VP，ServiceNow）

- 统一Webex Contact Center和ServiceNow服务平台
- 代理在ServiceNow平台中获得完整客户上下文
- AI代理协同工作：转录、推荐、自动化
- 消除屏幕切换和断裂的体验

### 联络中心的AI变革

**Vinod Muthukrishnan**（Contact Center）阐述了客户体验的全面AI重构：

- **上下文即控制点**："客户体验的新控制点不是数据，而是上下文。上下文是活跃的数据。"
- **AI质量管理**：重新定义了20多年来的质量评估方式
- **混合劳动力排班**：同时为AI代理和人类代理进行排班预测
- **AI路由优化**：基于实时上下文的智能路由

### 客户案例

**JLL**（Sarina，Corporate Real Estate Technology）：
- 全球112,000名员工，80个国家，340个办公室
- 约2,000台Cisco协作设备
- 最大的ROI：**生产力提升**和**全球体验一致性**
- 使用Workspace Designer简化设计流程

**Terna**（Francesco，IT & Digital Enterprise Services）：
- 意大利高压电力传输系统运营商
- 使用Webex Contact Center实现AI代理+人类代理协作
- 正在将服务扩展至24/7
- 目标：多代理、多平台的深度协作

### Snorre Kjesbu的战略总结

> "信任不应该是一种情感。信任应该与你构建的架构有关。选择正确的架构、正确的构建模块——信任来源于此。**信任是架构性的**（Trust is architectural）。"

四大公告：
1. **零信任安全**融入Webex Suite
2. **Webex Calling Hybrid**：保留UCM控制，添加云端AI创新
3. **Cisco AI Assistant for Contact Center**：AI带到数据所在之处
4. **Cisco AI for Webex**：NVIDIA驱动的零云端AI解决方案

---

## 安全深度专题：Agents on the Wire

### Keynote Deep Dive

**核心演讲者**：
- Tom Gillis（GM Infrastructure & Security，Cisco）
- Peter Bailey（Security Business）
- Rick Miles（Security Cloud Control演示）
- Kamala Hathi（Cisco Data Fabric / Splunk）

### Tom Gillis：平台效应

Tom Gillis用四个层次阐述了安全与网络的深度融合：

1. **AI感知注入网络安全**：防火墙不仅检测传统威胁，还检测AI模型和代理
2. **网络安全注入网络架构**：Hypershield将执行点嵌入每个交换机端口（微分段）
3. **网络架构融入AI计算集群**：后端网络成为GPU间通信的组成结构
4. **全栈遥测汇入Splunk**：统一可观测性和安全分析

> **Tom Gillis**："在这个后AI世界中，平台方法如此重要。因为Cisco拥有网络、拥有跨网络和代理的控制点、拥有分析层——这给了我们提供独特安全成果的能力。"

### Peter Bailey：代理时代的安全新基础

**三大新投资方向**：

**1. 代理身份（Agentic Identity）**
- 代理需要身份：知道它是什么、应该做什么、被允许做什么、不应该做什么
- 持续评估代理行为，基于行为做出调整
- 发现、认证和授权代理的技术

**2. AI工作负载安全**
- Kubernetes是AI工作负载的运行环境，但它曾是"黑箱"
- 模型本身需要保护：对抗越狱（jailbreak）和数据投毒（data poisoning）
- **Cisco AI Defense扩展至代理保护**：确保代理本身可以安全部署

**3. Cisco Data Fabric**
- 利用Splunk处理"荒诞"规模的机器数据
- 联邦式分析（不复制数据，而是将Splunk带到数据所在之处）
- 利用机器数据训练AI模型，实现预测性安全

### Live Protect——eBPF驱动的基础设施防护

- 基于Isovalent的eBPF技术
- 当发现漏洞时，可以快速创建并下发"盾牌"保护
- 在补丁发布前收缩"防御速度差距"（Defense Velocity Gap）
- **2026年夏季发布**

### Hybrid Mesh Firewall

- 将所有传感器和执行点作为系统统一管理
- AI就绪化：深度AI流量检测，模型库识别
- AI Defense集成检查调用
- AgenticOps驱动的主动策略
- 意图驱动策略创建（简化规则编写）

**产品线刷新**：
- **Secure Firewall 200系列和6100系列**（高端）
- 6100系列：16台集群可达**8TB深度包检测**
- 更小机架占用，更低功耗

### Hypershield：Smart Switch

- Nexus数据中心交换机中集成**DPU**（独立安全处理器）
- 提供东西向可见性和微分段
- Hypershield软件运行在DPU上

### Security Cloud Control演示

**演示者**：Rick Miles

**意图驱动策略部署**：
- 只定义策略意图（如"HR部门允许访问X应用"）
- 系统自动发现策略应部署到哪些位置（云边缘、防火墙等）
- 一键部署到多品牌防火墙（包括Cisco和Palo Alto）
- 不需要分别进入各个管理平台

**AgenticOps in Security Cloud Control**：
- 零信任访问策略自动创建
- VPN容量规划
- 主动预防2:00 AM的故障告警

### 零信任安全的核心原则

| 原则 | 说明 |
|------|------|
| **所有实体的身份** | 不仅为人，也为设备和代理建立身份 |
| **最小权限访问** | 只授予所需的最低权限 |
| **无处不在的可见性** | 网络是无处不在的——一切都经过网络 |
| **无处不在的执行** | Hybrid Mesh Firewall + Hypershield + 工作负载代理 |
| **行为监控** | 像监控内部人员一样监控代理行为 |
| **机器速度运行** | 端到端代理攻击在几分钟内完成，防御也必须如此 |

### SASE（安全访问服务边缘）

- SD-WAN + Secure Access的融合
- AI流量分类和优先级排序
- 对延迟敏感的AI应用（如远程手术机器人）的流量优化
- 代理式能力：发现和检查MCP调用

### Splunk Enterprise Security & Cisco Data Fabric

**Kamala Hathi**介绍了Cisco Data Fabric和Agentic SOC：

**Cisco Data Fabric**：
- Splunk平台的演进，提供交钥匙解决方案
- 数据联邦：不移动数据，将Splunk带到数据所在之处
- 统一、关联、洞察

**机器数据的价值**：
> "当我们想到大语言模型和GenAI，它们是用人类数据训练的。但存在于你组织中的数PB和EB级的机器数据，对AI来说是未使用、未触及的。"

**Agentic SOC三部分**：
1. 全面、高扩展的数据平台
2. 完整的分析工具集（XDR到威胁检测）
3. AI驱动的编排、自动化和辅助——从"检测和响应"到"预测和预防"

**Splunk Enterprise Security正式发布**，整合Data Fabric、分析工具和代理式能力。

---

## 安全运营中心（SOC）实战

### 展厅深度报道

**记者**：Robb Boyd
**嘉宾**：Jessica（SOC经理，Cisco）

首次在Cisco Live EMEA设立独立的安全运营中心（SOC），展示实际运行的安全技术栈：

- **全栈部署**：防火墙、Secure Access、DNS、Splunk集成、Secure Network Analytics、恶意软件分析
- **超级碗保护**：该团队是第五次保护NFL超级碗的Cisco安全团队
  - 巴黎奥运会后发现需要更紧密的XDR + Splunk集成
  - 大赛前33天接手，36小时内部署完成
- **XDR + Splunk Enterprise Security集成**：
  - XDR用于快速一、二级分析
  - Enterprise Security用于深度三级调查
  - 自动将事件包从XDR发送到Enterprise Security
  - 关闭循环时自动上传分析师笔记
- **Cisco Live保护**：从阿姆斯特丹SOC保护了超级碗赛事
- 展示期间已处理**43个安全事件**，仅2个尚未审查

---

## 合作伙伴专题：Orange Business与后量子密码学

### 演播室访谈

**主持人**：Lee Peterson（VP Secure WAN，Cisco）
**嘉宾**：Jean Noel和Frank（Orange Business）

- **30年合作伙伴关系**
- **后量子密码学**：应对未来量子计算对当前加密的威胁
- **SD-WAN**：在Orange Business的网络服务中的深度集成
- 共同为客户提供安全的WAN解决方案

---

## 合作伙伴专题：NetApp与FlexPod

### 演播室访谈

**主持人**：Steve Multer
**嘉宾**：Spencer（VP Global Alliances，NetApp）

FlexPod——20年合作的标志性成果：

- **起源**：2009年，为解决裸机到虚拟化的迁移挑战
- **规模**：超过**130亿美元销售额**，近**10,000客户**，**250+参考设计**
- 从虚拟化到Kubernetes到AI的持续演进
- **Cisco Live网络**：过去12年的Cisco Live事件运行在NetApp基础设施上
- **Unified Edge**集成：共同打造AI factory解决方案
- **设计哲学**：不是产品，而是持续联合工程的平台

> **Spencer**："当我们试图讨论是否要终结FlexPod时，行业说'绝对不行'。你们必须继续，因为我们太喜欢它了。"

---

## ThousandEyes与DHL网络保障

### Center Stage演讲：DHL Express案例

**嘉宾**：Richard（DHL Express）、David（DHL）

- DHL Express的全球网络复杂性管理
- 目标：**100%正常运行时间**
- ThousandEyes用于主动监控和问题定位
- AI驱动的网络故障排除演示
- 与Meraki的集成

### 展厅深度报道：ThousandEyes

**记者**：Robb Boyd
**嘉宾**：Marko（ThousandEyes）

ThousandEyes在AI时代的角色：

- **使命**：确保从客户端到应用程序的整个网络路径
- **AI增加的复杂性**：AI代理之间的东西向流量模式增加了网络复杂性
- **关键洞察**：区分信号（signal）和噪声（noise）是AI在网络保障中的核心价值

> **Marko**："就像AI只有在它被训练的数据质量好时才好用，网络保障也是一样——数据的质量决定了洞察的质量。只有正确的数据量才能给你需要的答案。"

---

## AI网络：Nexus AI Fabric Intelligence与Silicon One

### Center Stage演讲

**演讲者**：
- Sunil（Data Networking，Cisco）
- Rakesh Chopra（Common Hardware Group，Cisco）
- Lenny（CVS Health，客户案例）

### AI网络的三大不同

| 特性 | 说明 |
|------|------|
| **海量数据引擎** | AI应用生成和消耗大量数据，推动现有基础设施到极限 |
| **高功耗** | 2026年AI将使数据中心功耗翻倍 |
| **网络敏感性** | 拥塞、延迟、丢包都会导致GPU闲置 |

### Cisco Silicon One G300

**智能集体网络三要素**：
1. **Packet Buffer**：业界最大、全统一的包缓冲区
2. **智能硬件负载均衡引擎**：跨网络集体协作，自主决策最优路径
3. **硬件遥测**：实时监控芯片内部状态并广播至全网

**性能数据**：
- 使用G300技术可实现**33%更高利用率**
- 作业完成时间降低**28%**

**未来证明的基础设施**：
- 可编程引擎支持现场动态更新功能
- 支持多种角色（前端、后端）
- 不需要"拆除重建"——只需软件更新

### 新系统发布

| 产品 | 规格 | 特点 |
|------|------|------|
| **Cisco N9300系列**（G300） | 64×1.6T，风冷 | 支持NX-OS |
| **Cisco N9600/A100系列**（G300） | 液冷版本，无风扇 | 全热量通过液体传导 |
| **Cisco 8223路由系统**（P200） | 面向超大规模和Neo-Cloud | 运行SONiC |
| **Cisco N9600系列**（P200） | 51.2T固定形态 | 补充8100系列 |
| **28.8T模块化线卡** | 用于8800/N9800模块化系统 | 支持NX-OS、ACI、SONiC、iOS XR |

**效率提升**：
- 从6台51.2T风冷系统缩减到**1台G300液冷系统**
- **70%功耗效率提升**

### Nexus One：统一运维平台

- 提供跨不同Fabric类型的运维一致性（ACI、NX-OS、SONiC、HyperFabric）
- 客户可在不同操作系统间自由切换，硬件投资受保护
- 提供验证过的AI Fabric蓝图
- **AI Job Observability**：网络可见性和计算可见性的统一视图
- **Native Splunk嵌入Nexus Dashboard**：更快的遥测接收，支持数据主权
- **European Cloud版本的HyperFabric即将推出**

### AgenticOps with AI Canvas

- 2025年推出AI Canvas（从ThousandEyes和Meraki开始）
- 2026年扩展至数据中心网络
- 不是又一个管理工具——而是**AgenticOps的指挥中心**
- 用AI运维AI基础设施和非AI基础设施

### CVS Health客户案例

**嘉宾**：Lenny（CVS Health）

CVS Health的AI旅程：
- 从传统零售和医疗保健向AI驱动的服务转型
- 利用Cisco网络基础设施支撑AI工作负载
- 展示了企业级AI部署的实际案例

---

## 合作伙伴专题：AMD与UEC标准

### 演播室访谈

**主持人**：James Cole
**嘉宾**：Shane Corbo（Senior Director，AMD）

- **Ultra Ethernet Consortium（UEC）标准**：Cisco和AMD共同推动的AI网络标准
- **AMD Instinct GPU**：包括MI-450
- **Nexus + Silicon One + AMD**：联合AI基础设施方案
- **Hypershield + AMD嵌入式DPU**：在AMD平台上集成安全能力

---

## Cisco IQ：AI驱动的服务平台

### Center Stage演讲

**演讲者**：
- Bhaskar Jayakrishnan（Cisco CX）
- Carlos Pereira（Cisco Fellow）

### Cisco IQ定位

> **Bhaskar**："Cisco IQ不是你购买的东西，而是你体验的东西。所有拥有Cisco支持合同的客户，Cisco IQ就是交付载体——我们将AI能力、自动化和人类专业知识融入统一界面。"

### 从被动到主动的服务演进

| 传统服务 | Cisco IQ服务 |
|---------|-------------|
| 被动响应 | **个性化**：内部文档自动化 |
| 事后排障 | **主动**：提前告知潜在问题 |
| 人工分析 | **预测性**：监控环境并提供预警信号 |

### Support Signature正式GA

将最佳技术和人类专业知识结合，提供更具韧性的网络和基础设施。

### 核心能力演示

**1. 智能资产管理**
- 可视化资产、合同和已发现设备
- AI助手提供超个性化洞察
- AI驱动的分析工具将数千条记录浓缩为简洁报告
- 可导出PDF与决策者分享

**2. 安全加固评估**
- 自动排列Cisco最新安全公告
- 超个性化摘要显示受影响资产数量
- AI代理自动从IOS XE加固文档中提取和转化检查项
- 按需运行诊断评估并验证修复

**3. 后量子密码学就绪评估**
- 硬件物料清单（HBOM）→ 软件物料清单（SBOM）→ **加密物料清单（Crypto BOM）**
- 映射网络设备中的所有密码和密钥
- 为量子计算威胁做准备

**4. AI驱动故障排除**
- **2-4倍更快的解决时间**
- 支持多种模态
- 自动识别漏洞→推荐修复→安排升级→打开支持案例→匹配维护窗口内的工程师
- 端到端无缝体验

### Services as Code

- 基于Red Hat和Terraform的开源框架
- Cisco在其上构建了数据验证和上下文驱动的自动化测试
- 使用DevOps/DevSecOps方法的流水线
- 实际案例：客户从**1-2天**的变更时间缩短至自动化执行
- **25%的Cisco TAC案例**与配置错误相关——Services as Code可以预防

### 迁移框架（AI增强）

支持三种迁移类型：
1. **设备迁移**：旧设备→新设备（包括竞品迁移到Cisco）
2. **运维模型迁移**：如从CLI管理迁移至Meraki控制器或SD-WAN
3. **拓扑迁移**：如从MPLS网络迁移至Segment Routing v6

### 部署模型

| 模型 | 描述 | 适用场景 |
|------|------|---------|
| **SaaS** | 云端运行评估和排障，本地VM作为连接器 | 标准部署 |
| **On-Premises** | 主体功能在本地运行，部分公共服务（如LLM）在云端 | 欧洲合规需求 |
| **Full Air Gap** | 完全在本地运行，包括SLM（小语言模型） | 最严格的主权要求 |

---

## Day 2总结：AI的三大挑战

### Steve Multer闭幕总结

回顾CEO Jeetu Patel在主题演讲中提出的三大可能阻碍AI发展的挑战：

| 挑战 | 说明 | Cisco的应对 |
|------|------|-----------|
| **基础设施约束** | 需要容量、电力、计算、带宽和基础设施来承载AI | Silicon One、液冷系统、FMP、Nexus One |
| **信任赤字** | 如果不信任系统就不会采用和投资 | 安全融入网络、AI Defense、零信任架构 |
| **数据鸿沟** | 人类数据已接近天花板，需要利用机器数据和企业数据 | Splunk/Cisco Data Fabric、机器数据训练AI |

> **Steve Multer**："如果我们不信任这些系统，简单的事实是我们不会采用它们、投资它们或使用它们。安全和安全感是加速采用的关键。"

---

## 关键语录

### 关于能源与可持续性

> **Denise Lee**："你即将听到一项革命性技术……45年来首次出现的全新电力等级——Class Four Fault Managed Power。触摸安全的高压直流电，最高450伏特。"

> **Denise Lee**："如果你拿一个5MW的风冷数据中心，应用直接液冷和FMP电力分配，你可以节省大约76%的能源成本——相当于2.3倍的计算能力。"

### 关于AI自动化

> **Shannon McFarland**："Model Context Protocol让你无需重构现有系统就能将AI引入你的环境。MCP是通向完整AgenticOps环境的入门药物。"

> **Sujith Joseph**："Circuit已成为Cisco使用最多的AI工具。我们有超过100,000名用户，日均125,000条提示，处理了1.45万亿token。"

### 关于协作

> **Snorre Kjesbu**："信任不应该是一种情感。信任应该与你构建的架构有关。**信任是架构性的**。"

> **Vinod Muthukrishnan**："客户体验的新控制点不是数据，而是上下文。上下文是活跃的数据……98%的客户上下文存在于对话中，而直到现在这些上下文完全被丢失。"

### 关于安全

> **Tom Gillis**："AI感知注入网络安全，网络安全注入网络架构，网络架构融入AI计算集群。这就是平台效应。"

> **Peter Bailey**："我们必须开始像对待人类一样思考代理——给予它们身份、授权、监控它们的行为，并在它们偏离时进行调整。"

> **Peter Bailey**："如果你到处都有可见性和控制，这就是我们如何进入零信任的哲学世界——假设网络上有坏人，并能够保护自己。"

### 关于AI网络

> **Sunil**："AI性能以时间衡量——修复时间，最终是价值实现时间。时间是新的货币。"

> **Rakesh Chopra**："使用Cisco Silicon One，采纳新功能只是软件更新，不是拆除重建你的基础设施。"

### 关于服务

> **Bhaskar**："Cisco IQ不是你购买的东西，而是你体验的东西。"

> **Carlos Pereira**："几乎25%的Cisco TAC案例与配置错误相关。Services as Code可以预防这些问题。"

---

## 术语表

| 术语 | 全称/解释 |
|------|---------|
| **FMP** | Fault Managed Power——一种新型触摸安全高压直流电力分配技术（最高450V DC） |
| **PoE** | Power over Ethernet——以太网供电（最高100W） |
| **MCP** | Model Context Protocol——AI代理与现有系统（API、数据库等）通信的标准化协议 |
| **AgenticOps** | Agentic Operations——AI代理驱动的自动化运维 |
| **Circuit** | Cisco内部GenAI应用，类似ChatGPT，支持多模型、RAG、代理注册等 |
| **RAG** | Retrieval-Augmented Generation——检索增强生成 |
| **Cyber Vision** | Cisco OT安全可见性工具，通过网络流量分析发现工业设备和通信模式 |
| **Hypershield** | Cisco在网络交换机DPU上运行的安全软件，实现微分段 |
| **DPU** | Data Processing Unit——数据处理单元，独立于网络处理器的安全处理器 |
| **Silicon One** | Cisco自研硅片系列，支持交换和路由，具备可编程性和高效率 |
| **G300** | Silicon One最新交换芯片，64×1.6T，用于AI数据中心 |
| **P200** | Silicon One路由芯片，51.2T，面向超大规模和Neo-Cloud |
| **Nexus One** | Cisco统一网络运维平台，跨ACI、NX-OS、SONiC、HyperFabric提供一致性 |
| **HyperFabric** | Cisco管理的AI数据中心Fabric解决方案 |
| **AI Canvas** | Cisco AgenticOps的指挥中心，用AI运维网络 |
| **SASE** | Secure Access Service Edge——SD-WAN与安全访问控制的融合 |
| **SD-WAN** | Software-Defined Wide Area Network——软件定义广域网 |
| **XDR** | Extended Detection and Response——扩展检测与响应 |
| **eBPF** | extended Berkeley Packet Filter——Linux内核技术，用于网络和安全监控 |
| **Isovalent** | Cilium/eBPF企业版提供商，Cisco收购 |
| **Live Protect** | Cisco新安全能力，利用eBPF在补丁发布前提供漏洞防护 |
| **Cisco Data Fabric** | 基于Splunk的高扩展数据平台，支持联邦式分析 |
| **Cisco IQ** | Cisco AI驱动的服务平台，统一支持和专业服务交付 |
| **Support Signature** | Cisco增强支持服务层级 |
| **Services as Code** | 基于Terraform/Red Hat的基础设施即代码框架，由Cisco CX增值 |
| **AV over IP** | Audio-Video over Internet Protocol——音视频通过IP网络传输 |
| **Room Kit Pro G2** | Cisco新一代大型协作空间设备，含NVIDIA AI计算模块 |
| **Webex Translator Agent** | 实时语音到语音翻译代理，保留说话者声音和语调 |
| **Control Hub** | Cisco协作设备和服务的统一管理平台 |
| **ThousandEyes** | Cisco网络保障和可见性工具，监控端到端网络路径 |
| **Zero Trust** | 零信任安全模型——假设网络已被入侵，验证每个访问请求 |
| **UEC** | Ultra Ethernet Consortium——AI网络以太网标准联盟 |
| **FlexPod** | Cisco与NetApp的联合验证基础设施解决方案，已有16年历史 |
| **Talos** | Cisco威胁情报团队 |
| **Foundation AI** | Cisco AI研究团队，开发开源安全LLM模型 |
| **OCSF** | Open Cybersecurity Schema Framework——安全运营分析的标准化模式 |
| **SLM** | Small Language Model——小语言模型，用于本地/air-gap部署 |

---

*文档生成时间：2026年2月13日*
*视频ID：cBAoWoFYJ7w*
