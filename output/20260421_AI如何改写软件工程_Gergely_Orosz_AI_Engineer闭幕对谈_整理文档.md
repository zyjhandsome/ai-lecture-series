# AI 如何改写软件工程：与 Gergely Orosz 的闭幕对谈

## 📝 文章元数据

| 项目 | 内容 |
|------|------|
| **原标题** | How AI is changing Software Engineering: A Conversation with Gergely Orosz, @pragmaticengineer |
| **内容链接** | https://www.youtube.com/watch?v=CS5Cmz5FssI |
| **发布时间** | 2026-04-21（YouTube 元数据；频道另标注首播相关日期以平台为准） |
| **对谈人物** | **Shawn Wang**（AI Engineer 等活动组织者、播客与创作者，社区常用名 Swyx）× **Gergely Orosz**（《The Pragmatic Engineer》创办人、前 Uber / Skyscanner 工程师） |
| **内容来源** | YouTube 频道 **AI Engineer**；闭幕主题演讲式对谈；本文依据官方说明与口述整理 |

> **人物背景**
>
> **Gergely Orosz**：Uber、Skyscanner 背景工程师；著 *The Software Engineer's Guidebook*（[engguidebook.com](https://www.engguidebook.com/)）；在阿姆斯特丹从零做起 **Substack** 上订阅量领先的软件/AI 工程通讯 **[The Pragmatic Engineer](https://www.pragmaticengineer.com/)**，全球读者达百万量级。X：[@GergelyOrosz](https://x.com/GergelyOrosz)。
>
> **Shawn Wang**：与 **Gergely Orosz** 在疫情期间因写作社群相识（如《The Coding Career》相关圈子）；组织 **AI Engineer（AIE）** 系列活动，本场为「今日闭幕、明日议程预告」的主持语境。

---

## 🎯 核心导读 (Executive Summary)

> **AI 主笔导语**：**Gergely Orosz** 用一线匿名故事说明：**Token maxing**（为刷高 AI 用量指标而刻意消耗 token）正在多家大厂蔓延——排行榜、同事对比、甚至绩效维度里的「token 数据点」与裁员焦虑叠加，逼出「让 Agent 做低效总结只为数字好看」的扭曲行为；这与当年 **Velocity / Pluralsight Flow** 式「数行数、数 PR」如出一辙，讽刺的是推动者往往是 **Meta、Microsoft** 等头部公司。
>
> 但 **Gergely Orosz** 也指出**治理与测量的初衷**常来自管理层：**工程师在存量代码库上觉得 AI 没用就不用**，领导则看到 **Anthropic** 等「用 **Claude Code** 写很多代码、收入上涨」的外界叙事，容易把相关性与因果搅在一起，于是用目标、预算、榜单「硬推采用」。**Coinbase** 首席执行官 **Brian Armstrong** 发全员邮件要求上 AI 工具、约一周后解雇一名工程师的案例，被拿来形容这种压力的极端版本。**Gergely Orosz** 更抛出一个尖锐类比：**大厂偏爱 LeetCode 式算法面试**，筛的是「聪明且能忍受荒诞规则的人」——进了公司也会忍受 **token maxing** 这类荒诞；**创业公司**则更少在乎刷量，更在乎交付与成本。
>
> 生产力层面：**Gergely Orosz** 认为**个人**往往更快，**团队**整体仍打问号，许多公司难以把 AI 嵌进既有工作流；**Anthropic** 被点名正面例子。**Shawn Wang** 提起 **Meter** 相关盲测研究（约 **30** 人样本）：主观感觉 **+20%** 产出，实测平均 **-20%**——**Gergely Orosz** 提醒样本小、存在极端离群者；**Shawn Wang** 补充组织视角：**把编码 Agent 交给非工程同事**，可能整体更省等待时间，与「单看个人 PR 效率」不是同一回事。**Gergely Orosz** 引用 **Simon Willison**（口述中转录有多处昵称误识）的观点：AI **没有手册**、要很久才熟练，且**懂 Transformer 理论并不自动等于会用工具**——这与工程师熟悉的「懂编译器就更会写底层」直觉相反。高价值团队特质：**低自我、肯学、肯放下先验（priors）**。
>
> 角色变迁：风投支持的创业公司长期「领跑」行业形态——**测试、DevOps** 早已收束到工程师；**产品工程师（product engineer）** 在 **2022 年前后**已出现，AI 加速这一趋势；初级岗也被期待更多「资深行为」与商业理解。**John Deere** 工程副总裁侧故事：**两披萨团队**缩成 **一披萨团队**。「人人都成 AI 的工程经理？」**Gergely Orosz** 强烈反对简单等同：**工程经理**的核心是人际与组织摩擦；调度 Agent 更接近 **Tech Lead / 资深工程师** 的编排，且反馈循环远快于带十人团队半年才见结果；**David Heinemeier Hansson（DHH）** 用 **外骨骼（mech suit）** 比喻「同时推进多件事、仍掌控全局」。**Mitchell Hashimoto**（口述中转录为 Michelle，编者注）自称两个 Agent 就够。
>
> 大厂 **AI 基础设施**：外部不见 **Uber** 等产品大爆发，内部却在重做 **内部基础设施**——定制后台编码 Agent、对接 **monorepo** 的 **MCP 网关**、与服务发现结合的链路、On-call 工具、按风险分层的内部 Code review 等；**Uber、Airbnb、Intercom、Meta、Microsoft** 及中型公司皆类似。**Gergely Orosz** 解释三重动机：① **低风险练手** AI，比乱对客加「没人要的 AI 功能」更稳；② **代码体量远超上下文**，自研 + **RAG** 等定制往往胜过通用厂商方案；③ **预算政治**——「开发者平台」要 headcount 难，「**Agent 体验**」易批（戏言 **Agent 体验差不多就是个 CLI**）。**Shawn Wang** 呼应：**AI 基础设施**尚无教科书，只能靠案例互学。
>
> **Shopify** 案例：**2021** 年工程负责人 **Farhan Thakur**（口述中转录误识，编者注）听说 **GitHub Copilot** 在内测，直接找时任 GitHub 首席执行官 **Thomas Dohmke**（口述中转录误识，编者注），表示**不问是否对外售卖**，愿让约 **3000** 人全员试用换持续真实反馈，因而**提早约一年**拿到权限；早期 **Copilot** 质量差、**流失（churn）** 与排错成本高，但 **Shopify** 选择用**更高费用与折腾**换**比竞争对手领先数月**；**Farhan Thakur** 担心成本但仍认为若限制工具会损害招顶尖人才——**创新、招聘与理性军备竞赛**。**Gergely Orosz** 预告将与 **Shopify** 首席技术官 **Mikhail Parakhin**（口述中转录误识，编者注）做播客。
>
> **The Pragmatic Engineer** 创业史：疫情期 **Uber** 裁员与团队打散促成休整与写作；离开 **Uber** 约一年后在 **Substack** 试水；首篇写 **Uber**「平台 vs 产品项目」拆分的免费长文几乎立刻感到 **PMF**——首周仅靠「装得很懂」的推文就有 **100** 人预付 **100 美元/年**；**六周**内约 **1000** 名付费订户，收入打平其在阿姆斯特丹 **Uber** 时的底薪。策略：**找到 PMF 就重复做对的事**——近两年只坚持**一周一篇**（后变两篇），拒绝大量采访与合作以免分心；随后扩编（如 **Elen**、**Jessica** 等研究/运营）、一年半前开播客；通讯曾约 **四个月**成为 **Substack** 上**排名第一的付费技术类 newsletter**，并保持约**三年**；**Gergely Orosz** 笑谈如今 **SemiAnalysis**、**Dylan Patel** 等与「第一名」之争。**Shawn Wang** 致谢其对 **AIE** 的支持，并肯定其欧洲技术话语权。

---

## 📑 目录

1. [Token maxing：大厂指标、绩效与扭曲激励](#token-maxing大厂指标绩效与扭曲激励)
2. [AI 生产力：测量失灵、组织视角与「没有手册」的熟练曲线](#ai-生产力测量失灵组织视角与没有手册的熟练曲线)
3. [软件工程师角色：折叠的职能、更小的团队与「一披萨」现实](#软件工程师角色折叠的职能更小的团队与一披萨现实)
4. [编排 Agent 不是当工程经理：外骨骼、反馈循环与个人配方](#编排-agent-不是当工程经理外骨骼反馈循环与个人配方)
5. [大厂内部 AI 基建潮：MCP、monorepo 与「Agent 体验」预算学](#大厂内部-ai-基建潮mcpmonorepo-与agent-体验预算学)
6. [Shopify 为何愿意为 AI 的 churn 与成本买单](#shopify-为何愿意为-ai-的-churn-与成本买单)
7. [The Pragmatic Engineer：PMF、增长策略与从 burnout 到团队化](#the-pragmatic-engineerpmf增长策略与从-burnout-到团队化)

---

## Token maxing：大厂指标、绩效与扭曲激励

**Shawn Wang** 在 **AI Engineer** 闭幕环节向 **Gergely Orosz** 发问：什么是 **token maxing**？现场每个人都该这么做吗？

**Gergely Orosz** 自述约一周到十天前才集中听到这个词；自己在社交媒体发帖后，**Meta、Microsoft** 等大厂员工的私信「爆炸」。各公司内部动机与评价不一，但有几条共性主线。

### 💡 核心洞察

> **Token maxing** 本质是 **Goodhart 定律**在 AI 用量上的重演：一旦 **token 支出/输出**被排行、同事可见或与职场结果挂钩，理性人就会为数字优化，甚至牺牲真实效率。

### ✍️ 深度解析

**可见性与排行榜**。部分公司存在 **token** 排行榜或可查同事用量。**Salesforce** 被举例：有内部工具能查每人花在 **AI 相关 token** 上的美元金额。

**与绩效、裁员焦虑的叠加**。行业裁员新闻不断（如 **Block** 等被口头点名）；**Gergely Orosz** 强调有人即使用很多 token 仍被裁，但员工仍会猜：**token 数据会不会进绩效或晋升？** 在 **Meta**，**Gergely Orosz** 与管理者交流得知：**绩效评估里 token 是众多数据点之一**（类似 diff、影响力、代码评审贡献），**有时会被拿出来用**——因此可能被「武器化」：**低绩效 + 低影响 + 低 token** 像「连试都不试」；**高绩效 + 高影响 + 高 token** 则像「创新且有效」。

**具体扭曲行为**。**Meta** 曾有排行榜，上榜者 **token** 量极高，许多工程师感到害怕，于是 **token maxing**。**Microsoft** 也被描述存在排行榜，有人用自主 Agent **堆垃圾产出**只为数字。**Meta** 在相关文章曝光后关掉了排行榜——但 **Gergely Orosz** 指出**人们仍在 token maxing**，因为不确定数据是否真消失，且**高薪岗位**不值得因「token 不够」这种理由冒险。

**Salesforce** 另一类机制：每月有**最低消费目标**（口述约 **175 美元**量级），于是月初出现「刷到线就行」的心态。

**历史回声**。**Gergely Orosz** 回忆早年 **Velocity** 与 **Pluralsight Flow** 一类工具用**代码行数、PR 数量**衡量产出，已知愚蠢却仍有人优化指标；而今类似逻辑出现在**顶级运行的大厂**，让他觉得「鼓励人做蠢事」。

> **Gergely Orosz**：「**We're engineers**… **you don't really want to lose a job over something stupid** as… **you didn't have enough token count** — **that's how it feels**.」

---

## AI 生产力：测量失灵、组织视角与「没有手册」的熟练曲线

**Shawn Wang** 追问：在 **Goodhart** 式扭曲之下，**AI 是否仍值得**？整体是否仍让人更快？

### 💡 核心洞察

> **个人**层面 **Gergely Orosz** 倾向肯定；**团队/公司**层面仍大量「问号」，**Anthropic** 被举为正面反例；**懂理论 ≠ 会用工具** 是工程师最难消化的一点。

### ✍️ 深度解析

**为何大厂要测、要推？** **Gergely Orosz** 回溯约半年前阿姆斯特丹一场 **CTO** 晚宴：荷兰大型电商 **CTO** 抱怨团队**不信任 AI、用得少**（当时尚未到 **Claude Opus 4.5** 等模型阶段，**Cursor** 等已有订阅但**在存量代码库上帮助有限**）；邻座 **荷兰央行** 人士则称监管使命驱动、工程师愿意用。领导层看到 **Anthropic** 宣称大量代码用 **Claude Code** 完成、收入攀升，容易得出「**得多用，否则落后**」的结论——**测量与目标**由此而来，尽管可能存在**相关 vs 因果**混淆。

**Coinbase** 被作为强推样本：**Brian Armstrong** 邮件要求全员使用 AI 工具，否则一周内约谈；约一周后（口述为周六）**解雇一名工程师**；**底薪约三四十万美元级**另加股权——之后「大家都懂了」。**Gergely Orosz** 将此与 **LeetCode 面试**并论：筛选能忍受不合理规则的人，入职后也会忍受 **token maxing** 类规则；**创业公司**更关心做事与成本，而非刷榜。

**Meter 研究与样本争议**。**Shawn Wang** 引用一项盲测：受试者**主观**生产力 **+20%**，**客观**产出平均 **-20%**。**Gergely Orosz** 反驳样本仅约 **30** 人且有一名**极高**离群者；**Shawn Wang** 提到播客曾采访该离群者（口述名 **Anthony**，未核全名）。

**组织解锁**。**Shawn Wang** 观察：若让**非技术同事**也能用编码 Agent，**端到端等待工程排期**减少，整体可能更快——像出现「**serverless developers**」；这与单看工程师个人 PR 指标不同。

**Simon Willison**（**2024** 与 **Gergely Orosz** 交谈，**ChatGPT** 问世约两年后）的观点被复述：**AI 很难练、没有手册**；他自称两年后仍在试错的路上。**Gergely Orosz** 总结两大反直觉：① **熟练要时间、要持续练**；② **理解注意力、概率等理论并不能替代「手感」**——不像懂编译器就更会写汇编。**团队上下文一变，又要重学**；但投入多的团队若**低自我、肯放下先验**，收益更明显。

> **Gergely Orosz**：「**Leave your priors behind.** … **Don't leave your experience behind** but… **be open to it**.」

---

## 软件工程师角色：折叠的职能、更小的团队与「一披萨」现实

### 💡 核心洞察

> **AI** 只是加速器：**测试、DevOps** 已并入工程师；**产品**能力进一步下沉；**团队更小、期望更高**——**John Deere** 例子中 **两披萨 → 一披萨**。

### ✍️ 深度解析

**风投创业公司的「前跑」**。**Gergely Orosz** 认为 **2010 年代中**期起，**VC** 背书的创业公司里**每人对自己部署的代码负责**更普遍，传统企业则常设独立 **DevOps**。

**职能折叠**。专职测试已极少；**DevOps** 并入；**2022** 年前已有 **product engineer** 招聘趋势，**AI** 加快。**初级工程师**也被期待更多规划、商业理解与「资深味」。

**John Deere**（**200** 年历史量级公司）工程副总裁侧信息：**两披萨团队**正在变成 **一披萨团队**，部分归因于工具。**Shawn Wang** 插科打诨：「一披萨」取决于一个人吃多少披萨。

---

## 编排 Agent 不是当工程经理：外骨骼、反馈循环与个人配方

**Shawn Wang** 转述听众常见说法：「不再是工程师，人人是 **AI** 的**工程经理**。」**Gergely Orosz** 曾做工程经理，直言这种类比「**扯淡**」。

### 💡 核心洞察

> **工程经理**的痛点是**人际与组织泥潭**与**离产品变远**；**Agent 编排**更像 **Tech Lead**，且**反馈极快**。**DHH** 的 **mech suit** 比喻：**同时多线程、仍掌控**。

### ✍️ 深度解析

**现场互动**。**Gergely Orosz** 让当过或想当工程经理的观众举手——想当者约 **15%–20%**，他调侃会后要「劝退」。

**与带人的对比**。除非未来 Agent 互相「打架」，否则没有人类 drama。**Mitchell Hashimoto**（采访对象；口述 **Michelle**，编者注）习惯**一个后台 Agent** 等简单配置，认为**两个就够**。

> **Gergely Orosz** 转述 **David Heinemeier Hansson（DHH）**：不像「管理」Agent，更像 **mech suit**——「**seven things at once**… **faster**… **you're in control**。」

---

## 大厂内部 AI 基建潮：MCP、monorepo 与「Agent 体验」预算学

**Shawn Wang** 与 **Gergely Orosz** 都对「好基建」有执念，追问大厂内部所见。

### 💡 核心洞察

> 外部难见 **Uber** 级产品大爆发，内部却在**系统性重做**：**定制 Agent、MCP 网关、on-call、风险分层 code review**——**Uber** 是典型案例，**Airbnb、Intercom、Meta、Microsoft** 等同理。

### ✍️ 深度解析

**Gergely Orosz** 在 **Uber** 工作四年后的理解：① **内部平台**是**低风险**把 **AI** 做深的路径；② **代码规模**决定**通用工具 + 小上下文**不够，**自研 + RAG** 等更赢；③ **凡带 AI 的 headcount 更好批**——「**Agent 体验**」比「开发者平台」好要钱。**Shawn Wang** 吐槽：**Agent 体验**「基本上就是个 **CLI**」。**Gergely Orosz** 预测**明年**各厂仍会继续撞车式建设；**大厂若还没做 MCP 网关**会被反问「在干什么」。

**Shawn Wang** 说明本场为次日 **MCP** 等架构演讲「开胃菜」，并感叹 **AI infra** 仍缺系统教材，只能靠**同行案例**互学。

---

## Shopify 为何愿意为 AI 的 churn 与成本买单

**Shawn Wang** 以 **Shopify** 理解「看似浪费」的大厂投入：**2021** 年 **Farhan Thakur** 听说 **GitHub** 内部开发 **Copilot**，联系 **Thomas Dohmke**，强调**不是问卖不卖**，而是愿**全公司约 3000 人**试用换持续反馈，因而**提早约一年**获得访问。

### 💡 核心洞察

> **Shopify** 主动承受早期 **Copilot** **质量差、churn、修 bug** 的成本，买的是**相对竞品领先数月**的时间窗口；限制工具会伤害**顶尖招聘**。**人人同时军备**显得蠢，但**个体理性**。

### ✍️ 深度解析

**Farhan Thakur** 对成本有顾虑，但仍认为**不能用最好工具**在招聘上说不过去。**Gergely Orosz** 预告将对话 **Shopify** 首席技术官 **Mikhail Parakhin**，并称赞其 **ML** 与客户基础设施之强。

---

## The Pragmatic Engineer：PMF、增长策略与从 burnout 到团队化

### 💡 核心洞察

> **Uber** 裁员与士气低谷意外促成通讯创业；**PMF** 信号极强时，**Gergely Orosz** 用「**只做有效的那一件事**」对抗机会噪音；两年后意识到需**防 burnout** 才团队化。

### ✍️ 深度解析

若非典疫情期 **Uber** 裁员、团队使命失效，**Gergely Orosz** 自称可能不会创业。原计划写书再做「**Uber** 内部平台工程 **Ctrl+C Ctrl+V**」式创业（笑谈 **Temporal** 等 **Uber** 校友公司）。

**Substack** 起步时少有人写**深度软件工程**；首篇 **Uber** 平台/项目拆分长文带来「这就是 **PMF**」感。**100** 人预付年费、**六周** **~1000** 付费用户打平旧底薪等数据均出自其口述。

约两年仅 **1→2** 篇周刊、拒绝大量曝光以守住核心；后招 **Elen**、**Jessica** 等，一年半前开播客。**Substack** 付费技术类排名第一约 **四年**达成、保持约 **三年**；**SemiAnalysis** 与 **Dylan Patel** 等被随口提到为「榜一」竞争者。

---

## 🎙️ 关键语录与交锋时刻

> **Gergely Orosz**：「**It selects for the person who's smart and willing to put up with absolute [nonsense] to get the job.**」

> **Gergely Orosz**（谈 **token** 与饭碗）：「**You don't really want to lose a job over something stupid**… **token count** — **that's how it feels**.」

> **Gergely Orosz**（谈先验）：「**Leave your priors behind.** … **be open to it**.」

> **Shawn Wang** / **Gergely Orosz**（幽默纠正 **Simon Willison** 的头衔）：「**top commenter on Hacker News**」——「**that's not his title man**」——「**Django**… **prompt injections**。」

> **Gergely Orosz**（谈 **DHH**）：**mech suit** — 「**seven things at once**… **in control**。」

> **Gergely Orosz**（谈 **MCP 网关**）：「**If you're at a large company and you're not already building an MCP gateway, what are you even doing?**」

---

## 📚 延伸术语表（可选）

| 术语 | 解释 |
|------|------|
| **Token maxing** | 为抬高可观测的 AI token 使用/支出指标而采取的刻意消耗行为，常与排行榜或绩效语境相关。 |
| **Goodhart 定律** | 当指标被当作目标，便不再是个好指标；测量失真引发博弈。 |
| **Claude Code** | **Anthropic** 面向编码工作流的工具（口述中 **cloth code** 等为 ASR 误识）。 |
| **MCP** | Model Context Protocol；对话中指大厂自建的网关与工具链集成。 |
| **Churn** | 此处指工具早期不稳定带来的折腾、返工与废弃成本。 |
| **PMF（Product-market fit）** | 产品与市场匹配；文中指订阅与收入增长自证的契合状态。 |

---

### 🔍 自检报告 (Quality Check)

| 检查项 | 结果 | 备注 |
|--------|------|------|
| 术语校验（Claude Code、ChatGPT、LeetCode、Pluralsight Flow、monorepo、RAG、Goodhart 等） | ✅ | **Entrophic/lead code/Chad GPT/cloud code** 等已按语境校正；**internal** 基础设施口述为 **IM** 处按文意写作 **内部基础设施**。 |
| 纯净排版校验 | ✅ | 控制段落长度；标题无 `{#锚点}`；未使用时间轴逐句堆砌。 |
| 说话人对齐校验 | ✅ | 问答归属与现场互动（举手、玩笑）已按逻辑对齐。 |
| 人称与全名 | ✅ | 正文以 **Gergely Orosz、Shawn Wang、Brian Armstrong、David Heinemeier Hansson、Simon Willison、Thomas Dohmke、Farhan Thakur、Mikhail Parakhin、Mitchell Hashimoto** 等为主；**DHH、PMF、MCP、CLI、Uber、Meta** 等为公认缩写或专名。 |
| 防幻觉与盲区标注 | ⚠️ | **Meter** 研究、**Anthony** 离群者、**175** 美元/月、**30** 人样本、**100 / 1000** 订户、**3000** 人试用等均来自口述；未逐条核对原始论文或公司财报。**「一周后解雇工程师」**等敏感事实为转述，未独立核实法律或公关细节。 |

*文档生成时间：2026-04-27*
