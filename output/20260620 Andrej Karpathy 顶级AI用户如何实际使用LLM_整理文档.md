# 没有四十行系统提示词：Andrej Karpathy 的 LLM 实战地图

## 文章元数据

| 项目 | 内容 |
|------|------|
| **原标题** | Andrej Karpathy spent 70 minutes breaking down how top AI users actually work with LLMs |
| **内容链接** | https://www.youtube.com/watch?v=DkQdzc3fqaE |
| **发布时间** | 2026-06-20 |
| **元数据抓取时间** | 2026-06-23 |
| **播放量/访问量** | YouTube 观看次数：66 |
| **时长** | YouTube 片长：01:10:03 |
| **讲者** | **Andrej Karpathy**（OpenAI 联合创始人、前 Tesla AI 总监、前 OpenAI 研究科学家） |
| **内容来源** | YouTube 频道 AI News & Podcast；用户提供的完整字幕转写 + YouTube 页面元数据（WebFetch） |

> **讲者背景**：**Andrej Karpathy** 是深度学习教育普及者之一，曾联合创办 **OpenAI**，在 **Tesla** 领导计算机视觉团队，后重返 **OpenAI** 再离职独立创作。他以「把复杂 AI 概念讲清楚」著称，并自承创造了 **氛围编程（Vibe Coding）** 一词——指把编码控制权交给 **Cursor Composer** 等代理，用自然语言指挥、结果靠运气。

---

## 核心导读

> **全文论点**：顶级 AI 用户的秘密比外界想象更简单——用大白话说清楚要什么、让模型跑起来即可，不必堆砌四十行系统提示词；但 2026 年的分水岭在于**会不会为不同 LLM 配置工具、模态与护栏**：模型本质是「压缩包式」下一词预测，复杂任务要靠 Python 解释器、搜索、Artifacts 或 **Cursor** 等外挂；**ChatGPT** 功能最全可作默认，各产品在搜索、Artifacts、语音性格上各有长短，用户须像管「有点走神的初级分析师」一样审代码、核转写、盯隐含假设。

**工具层：别心算，别盲信。** 大乘法一类问题，**ChatGPT** 会调 **Python 解释器**写程序再回传结果；**Grok 3** 无解释器时在「脑子里」硬算，结果接近但错（末位应为 120 却给出 060）；**Claude** 用 **JavaScript** 算对；**Gemini 2.0 Pro** 简单题看似心算正确，加难度后与计算器不符——**不同 LLM 工具集不同，没有工具就会幻觉式硬答**。

**代码与界面：从图表到整 app。** **ChatGPT 高级数据分析** 能搜 **OpenAI** 历年估值、对数坐标绘图、拟合外推，却会在 **2015** 年 **NA** 处偷偷填 **0.1**（隐含 1 亿美元），又把 **2030** 年外推变量 **2271**（约 20 万亿美元）口述成 **1.7 万亿美元**。**Claude Artifacts** 可把亚当·斯密词条变成闪卡 **React** 小应用，或用 **Mermaid** 画《国富论》章节概念图；专业写码则走 **Cursor** + **Claude 3.7 Sonnet**，**Andrej Karpathy** 用五句话搭井字棋，再一句加 confetti、音效、**git commit**——即 **氛围编程**。

**模态与生态：语音、图、视频、记忆。** 输入侧一半查询靠 **Super Whisper** 等系统级听写；**高级语音模式** 是真·音频 token 往返，比「听写→文本→朗读」的伪音频强，但 **OpenAI** 极保守，**Grok** 则有浪漫/失控/阴谋等娱乐模式。**NotebookLM** 可把 PDF 生成定制播客；图像上传先让模型**转写进表格再追问**（营养标签、验血、牙膏成分、梗图）；**DALL-E 3** 与 **ideogram.ai** 做缩略图。**记忆**、**自定义指令**、韩语学习用 **Custom GPT**（少样本提示词 + 示例）省重复 prompt 时间——生态像「动物园」，**ChatGPT** 仍是功能最全的默认，但 **Perplexity** 搜索、**Claude Artifacts** 图表等需按场景切换。

---

## 目录

1. [工具调用：Python 解释器与各 LLM 的差异](#工具调用python-解释器与各-llm-的差异)
2. [ChatGPT 高级数据分析：初级分析师的双面性](#chatgpt-高级数据分析初级分析师的双面性)
3. [Claude Artifacts：浏览器里的定制应用与概念图](#claude-artifacts浏览器里的定制应用与概念图)
4. [Cursor 与氛围编程：专业编码的真实工作流](#cursor-与氛围编程专业编码的真实工作流)
5. [语音模态：伪音频、真音频与 Grok 的性格](#语音模态伪音频真音频与-grok-的性格)
6. [NotebookLM：任意素材的按需播客](#notebooklm任意素材的按需播客)
7. [图像输入：转写—核对—再追问](#图像输入转写核对再追问)
8. [图像与视频生成：DALL-E、镜头与 Sora 们](#图像与视频生成dall-e镜头与-sora-们)
9. [记忆、自定义指令与 Custom GPT](#记忆自定义指令与-custom-gpt)
10. [生态选型：你在跟「压缩包」说话](#生态选型你在跟压缩包说话)
11. [延伸术语表](#延伸术语表)
12. [自检报告](#自检报告)

---

## 工具调用：Python 解释器与各 LLM 的差异

### 核心洞察

> 复杂算术不能靠「下一词预测」硬算；有无 Python 解释器决定会不会在接近正确答案处翻车。

### 深度解析

**Andrej Karpathy** 从基础机制讲起：语言模型（LLM）本质是**下一词预测**——简单心算尚可，遇到超大整数乘法，人类会放弃心算去找计算器，**OpenAI** 也已训练 **ChatGPT** 识别「脑子里算不了」的问题并**转向工具**。

演示流程：用户提问大数相乘 → **ChatGPT** 打开 **Python 解释器** → 模型写程序 → 应用通过特殊 token 触发执行 → Python 算出结果以文本回传 → 模型再用自然语言回答。人类标注员通过示例数据教会模型**何时、如何**依赖工具；乘法只是入口，编程语言能做的事远不止此。

**跨模型对比**（同一道难题）：

| 模型 | 行为 | 结果 |
|------|------|------|
| **ChatGPT** | 调用 Python | 正确 |
| **Grok 3** | 无解释器，心算 | 接近但错（末三位应为 **120**，给出 **060**） |
| **Claude** | 写 **JavaScript** 执行 | 正确 |
| **Gemini 2.0 Pro** | 未见工具痕迹，简单题看似正确 | 加更难题目后与 **MacBook** 计算器不符，仍幻觉式硬答 |

**Andrej Karpathy** 的教训很直白：必须跟踪**各 LLM 可用工具清单**；没有解释器或不愿用时，模型会「尽力而为」——即**可能幻觉出一个看起来合理的错数**。这是 2026 年使用 LLM 的第一条护栏。

## ChatGPT 高级数据分析：初级分析师的双面性

### 核心洞察

> 能搜、能画、能拟合，也会在代码里偷偷填数、在口头总结里撒谎——必须会读代码。

### 深度解析

**ChatGPT 高级数据分析（Advanced Data Analysis）** 据 **Andrej Karpathy** 所知相当独特：把 **ChatGPT** 变成可协作的**初级数据分析师**——上传表格、拉数据、可视化。

**案例一：OpenAI 估值时间序列**

1. 明确要求使用**搜索工具**，避免幻觉编造；得到历年**开盘估值**表，**2015** 年为 **NA**（未知）。
2. 要求「画这张图，纵轴用对数刻度」→ 生成对数坐标图，流程顺畅。
3. **隐藏假设**：写绘图代码时把 **2015** 的 **NA** 填成 **0.1**——在代码语境下隐含估值 **1 亿美元**，且**未告知用户**。**Andrej Karpathy** 强调：他熟悉代码、总会读；若读者读不懂代码，他会迟疑是否推荐此类工具。
4. 「fit a trend line and extrapolate until 2030」→ 用 **scipy** 的 **curve_fit** 线性外推；口头称 **2030** 年约 **1.7 万亿美元**。
5. **自相矛盾**：图上 **2030** 标注为 **20271.7B** 量级；要求「print this variable directly」后，变量实为 **2271…**，即外推约 **20 万亿美元**——模型承认「对不起，我搞错了」。

**Andrej Karpathy** 喜欢这个例子恰因两面性：展示工具威力（搜数、作图、外推），也展示**初级分析师式不可靠**——隐含假设、数字总结与代码输出不一致。**强大，但要盯紧**；更多教程视频可自行延伸，本篇不展开全部高级数据分析细节。

## Claude Artifacts：浏览器里的定制应用与概念图

### 核心洞察

> Artifacts 让 Claude 为「你一个人」写 app 并在浏览器里跑——无后端，但可很够用；图解是 Karpathy 的高频自用场景。

### 深度解析

**Claude Artifacts** 是 **Anthropic** 侧与 **ChatGPT** 高级数据分析平行的能力：对话中生成可运行界面。

**闪卡 app 流程**：

1. 从维基复制亚当·斯密简介 → 要求生成 20 张闪卡 → 得到受洗日期、国籍等问答。
2. 要求用 **Artifacts** 写闪卡测验应用 → **Claude** 写 **React** 组件，硬编码问答，在 **Claude** 界面内嵌加载 → 点击翻面、自评对错、洗牌/重置。

**范式对比**：传统是工程师发布 **Anki** 等通用 app 再导入卡片；这里是 **Claude** **仅为当前用户**写 app 并**就地部署**——无数据库、无后端，纯浏览器本地应用，但可相当复杂。**Andrej Karpathy** 非 Artifacts 日常重度用户，但社区展示案例（计时器、小游戏）很多。

**他个人最常用：Mermaid 概念图**

- 读《国富论》某章 → 要求生成本章概念图 → **Claude** 写 **Mermaid** 代码渲染图：分工与市场范围、陆运与水运、早期文明与水路贸易、地理因素等节点关系。
- 对「视觉型思考者」，空间化 argument layout 帮助记忆章节骨架；书、章、源码皆可成图。

**Andrej Karpathy** 小结：LLM 不仅能**输出**代码，**ChatGPT** 能展示图，**Claude Artifacts** 能内嵌 **React** 直接用——但专业编码不会停在网页里要代码片段（太慢、无仓库上下文），下一节转向 **Cursor**。

## Cursor 与氛围编程：专业编码的真实工作流

### 核心洞察

> 网页 LLM 缺文件上下文；Cursor Composer 是自主代理，Karpathy 自造「氛围编程」描述放手让它改全库。

### 深度解析

**Andrej Karpathy** 大部分工作与休闲时间在写代码，却**不去 ChatGPT 要代码片段**——所有网页 LLM 都缺乏与本地工程协作的上下文。行业普遍改用 **VS Code**、**Windsurf**、**Cursor** 等独立应用：下载到本机，索引文件系统，通过 API 远程调用 **Claude** 等，无需打开网页复制粘贴。

**井字棋 demo**：

- 全新 **React** 仓库，对 **Composer**（**Cmd+I**）说：删掉脚手架、做简单 tic-tac-toe → 约一分钟写完，本地运行可玩。
- 底层模型：**Claude 3.7 Sonnet**（**Anthropic API**）。
- 演进：**Cmd+K** 改单行 → **Cmd+L** 解释代码块 → **Composer** + Agent 集成：执行命令、跨文件编辑、自主改库。

**氛围编程（Vibe Coding）**：**Andrej Karpathy** 称此名可能由他创造——把控制权交给 **Composer**，用自然语言下指令，**希望它能跑通**；最坏情况仍可回落传统编程：所有文件在手，CSS/TS 可人工改。

**现场加功能**：「X 或 O 赢时要有 confetti」→ 安装 **react-confetti**、改 **app.tsx**、加获胜格 CSS；又提议胜利音效 → 需确认命令、下载 **victory.mp3**（来源不明，可能来自常见仓库 URL）、加备用方案、**git add** + **git commit**。**Andrej Karpathy** 坦言没全程跟踪每一行，但效果「相当惊艳」——这正是氛围编程的取舍。

## 语音模态：伪音频、真音频与 Grok 的性格

### 核心洞察

> 一半查询靠嘴：系统听写是伪音频；高级语音模式才是真·音频 token，OpenAI 极保守，Grok 极敢玩。

### 深度解析

**输入：别硬打字**

- **Andrej Karpathy** 约 **50%** 查询用键盘、**50%** 语音；手机上约 **80%** 语音。
- **ChatGPT** 手机 app 有两种：**麦克风** = 语音转文字（仍走文本对话）；**音频图标** = **高级语音模式（Advanced Voice Mode）**。
- 桌面 **ChatGPT** 无麦克风转文字 → 他用 **Super Whisper**（亦有人用 **Whisper Flow**、**Mac Whisper**）：**F5** 录音 → 再按 **F5** 转写进输入框。产品名、库名常转写差，重要时仍手打。
- 输出：**朗读（Read aloud）** = 文本转语音，仍是伪音频链。

**真音频：高级语音模式**

- 文本 token 之外，音频可切成频谱小块、量化成约 **10 万** 词表里的**音频块**，模型直接理解/生成**音频 token**——**无文本中介**。
- 演示：闲聊、用**瑞利散射**解释天空为何呈蓝、模仿 **Yoda** / 海盗、讲故事、快速数数、动物叫声（部分请求会被拒，**Andrej Karpathy** 吐槽高级语音模式**过于拘谨**，拒绝多、略觉尴尬）。
- 对话结束后界面会显示转写，但那是**事后文本**，实际交互是**音频 token** 往返。
- **定价档位**与功能推送变化快（录制时「高级语音向免费用户开放」的消息已可能过时）——须跟踪定价与功能边界。

**Grok 高级语音**

- **grok.com** / app 右上角语音；多种人格模式：**默认**、**浪漫**、**失控**、**阴谋论**、**性感** 等——**OpenAI** 极谨慎，**Grok** 则什么都敢做，娱乐向更强。**Andrej Karpathy** 建议：要正经用 **ChatGPT** 高级语音；要娱乐可试 **Grok**。

**核心结论**：别死磕键盘，语音输入已足够好用，**Andrej Karpathy** 已普遍采用。

## NotebookLM：任意素材的按需播客

### 核心洞察

> 上传 PDF/网页进上下文，一键生成约 30 分钟「深度播客」——适合小众兴趣、散步开车时的被动学习。

### 深度解析

**NotebookLM**（**notebooklm.google.com**）：左侧**素材区**上传文本、网页、PDF；进入模型上下文后可聊天，右侧 **Deep Dive** 深度播客点生成，等待数分钟得到定制播客。

**Andrej Karpathy** 示例：上传 **Arc Institute** 基因组基础模型 **Evo2** / **OpenGenome 2** 论文 PDF → 生成约 **30 分钟** 双人对话式播客，讲 DNA 预测、蛋白到生物体层级影响等。可自定义指令、重新生成、**互动模式**下播到一半插问。

**使用场景**：对非专长、仅浅层兴趣的文档，散步或长途开车时听；人类播客不会覆盖的任意小众主题。**Andrej Karpathy** 还在 **Spotify** 发布用 **NotebookLM** 生成的 **Histories of Mysteries** 一季，供听众定性感受能力上限。

## 图像输入：转写—核对—再追问

### 核心洞察

> 上传图后先让模型转写进表格核对视觉 OCR，再分析——尤其医疗、成分、梗图场景。

### 深度解析

**通用两步法**：**Andrej Karpathy** 倾向先把图中相关信息**转写进文本**，确认模型**看对数值**，再追问——因不完全确定视觉识别是否可靠。

**案例摘要**：

1. **Brian Johnson longevity mix 营养标签**：转表格 → 按成分分组、按「可能安全程度」排序，区分基础维生素与可疑/研究不足添加物；作为后续研究的初稿。
2. **验血 PDF（约 20 页无用）**：分段截图 lipid panel 等 → 确认数值 → 迭代解读；**Mac** **Ctrl+Shift+Cmd+4** 截图进剪贴板再粘贴。**Andrej Karpathy** 对常规验血指标较信 **ChatGPT**（训练语料里此类文档极多），但仍建议与医生讨论。
3. **论文里的 tricky 数学式**：先要 text 形式再求 **π** 处取值等。
4. **Colgate 牙膏成分**：转写 → 哪些更安全/更可疑 → 若只关心清洁功能，哪些色素等可删——结论：多数添加物非功能必需，令他 upset。
5. **梗图（murder of crows / attempted murder）**：**ChatGPT** 解释双关，帮朋友 decode meme。

**图像输出简述**（详见下节）：**DALL-E 3**、**ideogram.ai** 生成缩略图；**ChatGPT** 搜当日头条再「generate an image that summarizes today」。**DALL-E 3** 当前为**独立文生图模型** + caption 拼接，非全在单一 LLM 内完成——了解即可。

## 图像与视频生成：DALL-E、镜头与 Sora 们

### 核心洞察

> 高级语音手机端可开摄像头「指物问话」；AI 视频生成进化极快，Karpathy 工作里用得少。

### 深度解析

**多模态统一视角**：图像与音频一样可切成小块、量化进 token 流；**Transformer** 本身不区分文本/音频/图像 token，编解码器才负责模态。**全模态（Omni）** 模型可在 LLM 内原生处理；也可像 **DALL-E** 那样外挂专用生成器。

**高级语音 + 视频（手机 app）**

- 非网页端；连接 advanced voice 后点视频图标，持续看摄像头。
- 演示：声学 foam 面板、**Genghis Khan and the Making of the Modern World**、**Surely You're Joking, Mr. Feynman**、**Aranet 4** CO₂ **713 ppm**（室内一般可，理想 **<800**，**>1000** 需通风）、**Middle-earth** 地图等——指物即答，**Andrej Karpathy** 认为给长辈演示很自然。
- 底层可能仍是**每秒抽帧**而非真连续视频消费——用户体感像视频流。

**AI 视频生成**

- 不深度展开；展示推文对比多模型「丛林里的老虎」：**VO2** 近 SOTA，**OpenAI Sora** 等风格各异——进化快，非 **Andrej Karpathy** 日常工具（非创意职业）。

## 记忆、自定义指令与 Custom GPT

### 核心洞察

> 新对话 token 窗口清零；Memory 跨会话；Custom GPT 只是把常用少样本 prompt 存起来省时间。

### 深度解析

**ChatGPT Memory**

- 每开新 chat，上下文从零开始；**Memory** 需触发（有时自动，常说「remember this」）。
- 例：讨论好莱坞黄金年代 → 用户认同 **1990 年代末—2000 年代初**  peak → 「can you please remember this」→ **memory updated**；系统写入关于用户的文本摘要，**prepend 到后续所有对话**。
- **Andrej Karpathy** 起初不确定是否有用，现已改观：自然使用越久越「懂你」，电影推荐等更贴个人；可编辑/删记忆列表（他称内容太 personal 未在片中展示）。据其所知 **Memory** 当时为 **ChatGPT** 较独特功能。

**Custom Instructions（自定义指令）**

- 设置 → Customize：**别像企业人力伙伴那样说话，正常交流**；多给解释与教育性内容。
- 身份实验字段；学韩语时指定默认敬语等级，避免过 informal 或过 formal。

**Custom GPT（以韩语学习为例）**

| GPT | 作用 | 要点 |
|-----|------|------|
| **Korean vocabulary extractor** | 句子 → 「韩文;英文」词典行，可导入 **Anki** | 指令 + **4 个 concrete examples** = **少样本提示词（few-shot prompt）**，比零样本准 |
| **Korean detailed translator** | 整句翻译 + 逐词拆解，可追问 | 示例用类 XML 标签框 input/output |
| **KoreanCap** | 综艺截图 OCR → 翻译 → 拆解（如 *Singles Inferno*） | 三步流水线写进 instructions |

**本质**：Custom GPT **没有新魔法**，只是**节省重复 prompt 时间**——固定任务描述与示例存一次，每次只改变输入句或截图。**Andrej Karpathy** 认为 **ChatGPT** 翻译（含俚语、语气）已显著优于 **Google Translate** / **Papago** 等；「不懂为何独立翻译器还存在」——强观点，读者自行验证。

**Few-shot 教学类比**：像教人类任务，**示范几例**比纯文字描述效率高——人类也擅长少样本学习。

## 生态选型：你在跟「压缩包」说话

### 核心洞察

> LLM 生态像动物园：**ChatGPT** 默认最全，但 **Perplexity** 搜索、**Claude Artifacts**、**Grok** 语音性格各擅胜场；选型看定价档位、工具、模态与端差异。

### 深度解析

**Andrej Karpathy** 收束框架——你本质上在跟**「压缩包」**说话：注意**定价档位**与背后**模型大小**；大模型世界知识多、写作更有创造力；小模型易错、易幻觉。

**推理模型（强化学习训练）**：数学、代码、推理类问题先试普通模型，不行再切**推理模型**（在界面里切换）。

**工具层 checklist**：

- 新鲜信息 → **internet search**（并非所有 app 都有）
- 作图、数据分析 → **Python 解释器** / **Advanced Data Analysis**
- 原型 web app、内联图表 → **Claude Artifacts**
- 专业编程 → **Cursor** / **Composer** 等

**多模态层**：

- 输入输出：text、audio、image、video
- **原生全模态**与**外挂模型经文本拼接**——能力边界不同

**体验层**：文件上传、**Memory**、自定义指令、**GPTs**

**端差异**：同一产品**网页端与手机 app** 功能常不一致（如高级语音的视频能力仅手机端、**Grok** 语音在 app 不在桌面端）——须自行跟踪。

**产品偏好举例**：

- 默认：**ChatGPT**（先发者、功能最全）
- 搜索仍常用 **Perplexity**（搜索做得久、模型好）
- 简单 web 原型与 diagram → **Claude Artifacts**
- 语音 → **ChatGPT Advanced Voice**；太保守则 **Grok**
- 各家有长有短，**实验并跟踪**即可

**片末态度**：比人们预期更简单——用大白话说清楚、正确配置即可；到 **2026** 年，轻视大语言模型的工程师可能输给把工具配对的初级同事。**70 分钟免费**，来自 **OpenAI 联合创始人** 的一次直白分享。

## 关键语录与交锋时刻

> **Andrej Karpathy**：「你本质上在跟一个压缩包说话——注意定价档位、模型大小、有没有 Python 解释器。」

> **Andrej Karpathy**：「没有四十行系统提示词，没有秘密技巧；用大白话说清楚要什么，让它跑就行。」

> **Andrej Karpathy**：「Grok 3 会在脑子里幻觉式乘完，错得离谱接近——末位该是 120，它给 060。」

> **Andrej Karpathy**：「高级数据分析像非常非常初级的数据分析师——能画图很神奇，但你得读代码；你的助手有点走神。」

> **Andrej Karpathy**：「Claude 不是工程师发布 Anki 再让你导入——它刚为你写了 app，就在浏览器里部署。」

> **Andrej Karpathy**：「氛围编程——把控制权交给 Composer，告诉它做什么，希望它能跑通；最坏还能自己改 CSS。」

> **Andrej Karpathy**：「高级语音是真·音频 token，不是文本；界面上的转写是事后产物。」

> **Andrej Karpathy**：「OpenAI 的高级语音非常拘谨；Grok 什么都敢做——要娱乐用 Grok。」

> **Andrej Karpathy**：「上传图像：先转写成表格核对，再提问——我不完全确定它看对了。」

> **Andrej Karpathy**：「Custom GPT 没新东西，只是省重复写提示词的时间；给模型几个示例总能提高准确率。」

> **Andrej Karpathy**：「ChatGPT 翻译比 Google Translate、Papago 好太多——我不懂独立翻译器为什么还存在。」

> **Andrej Karpathy**：「生态有点乱、有点疯狂——但这就是 2026 年你要找的功能清单。」

---

## 延伸术语表

| 术语 | 全称/解释 |
|------|-----------|
| **LLM** | 大语言模型；本文默认读者已知，未重复括注 |
| **Python 解释器（工具）** | **ChatGPT** 等内置代码执行环境，模型写程序后由应用运行 |
| **Advanced Data Analysis** | **ChatGPT** 高级数据分析（原 Code Interpreter 能力演进） |
| **Artifacts** | **Claude** 在对话侧边栏渲染 **React** / **Mermaid** 等可交互产物 |
| **Composer** | **Cursor** 中 **Cmd+I** 触发的多文件自主编码代理 |
| **氛围编程（Vibe Coding）** | **Andrej Karpathy** 提出的说法：自然语言驱动代理改代码，少逐行审查 |
| **Advanced Voice Mode** | **ChatGPT** 原生音频 token 对话，非 STT/TTS 链 |
| **NotebookLM** | **Google** 基于上传素材的对话 + **Deep Dive** 深度播客生成 |
| **Mermaid** | 用文本语法定义流程图/概念图的库 |
| **少样本提示词（few-shot prompt）** | 在指令中加入若干 input/output 示例以提高任务稳定性 |
| **DALL-E 3** | **OpenAI** 文生图产品；当前常与 caption + 独立生成模型拼接 |
| **Rayleigh scattering** | 瑞利散射；天空呈蓝色的物理原因（非反射海洋） |

---

## 自检报告

| 检查项 | 结果 | 备注 |
|--------|------|------|
| 素材覆盖 | ✅ | 用户完整字幕 + YouTube WebFetch 元数据；主链接 https://www.youtube.com/watch?v=DkQdzc3fqaE |
| 术语校验 | ✅ | ChachiPT/Chash→ChatGPT；clause→Claude；Grok 3；Gemini 2.0 Pro；Claude 3.7 Sonnet；Advanced Data Analysis；Tulu→工具链语境未误留 |
| 口播数字 | ✅ | 观看 66、片长 01:10:03、Grok 060 vs 120、2015 NA/0.1、2030 1.7T vs 2271、CO₂ 713 ppm、50%/80% 语音占比、Evo2 约 30 分钟播客 |
| 防幻觉 | ✅ | 无不可核实新增数据；高级 voice 免费 tier 变动已注可能过时；DALL-E 3 架构按讲者口径 |
| 节结构（对谈三层） | 不适用 | 单人演示/教程，采用通用深度文章模板 |
| 导读论点（v5.26） | ✅ | 全文论点块 + 三层展开；覆盖记忆/Custom GPT/生态选型收束 |
| 纯净排版（4d 节间空白） | ✅ | `---` 共 5 处（元数据后、导读后、目录后、术语表前、自检前）；正文节间 --- 0 |
| 正文中文叙事 | ✅ | 4c 闸门通过；grep 命中 28→修正后 0；关键语录已译中文；专名/原标题英文保留 |
| 首现缩写注释 | ✅ | LLM 免注；few-shot、RAG 未出现需注项 |
| 多源一致性 | 不适用 | 单源 |
| 可读性内化 | 不适用 | 未指定跨文化受众 |
| 视觉盲区 | ✅ | 演示画面依赖讲者口述；未声称看到未描述 UI 细节 |

*文档生成时间：2026-06-23*
