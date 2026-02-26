# AI Skills 完整技术指南：从概念到实践

> 最后更新：2026年2月27日 | 基于 Anthropic 官方规范与 Agent Skills 开放标准
> 

---

## 目录

1. [序言：AI 应用逻辑的质变](about:blank#1-%E5%BA%8F%E8%A8%80ai-%E5%BA%94%E7%94%A8%E9%80%BB%E8%BE%91%E7%9A%84%E8%B4%A8%E5%8F%98)
2. [核心定义：什么是 Skill](about:blank#2-%E6%A0%B8%E5%BF%83%E5%AE%9A%E4%B9%89%E4%BB%80%E4%B9%88%E6%98%AF-skill)
3. [技术架构：渐进式披露机制](about:blank#3-%E6%8A%80%E6%9C%AF%E6%9E%B6%E6%9E%84%E6%B8%90%E8%BF%9B%E5%BC%8F%E6%8A%AB%E9%9C%B2%E6%9C%BA%E5%88%B6)
4. [Skills 的真实价值](about:blank#4-skills-%E7%9A%84%E7%9C%9F%E5%AE%9E%E4%BB%B7%E5%80%BC)
5. [使用教程：从安装到运行](about:blank#5-%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B%E4%BB%8E%E5%AE%89%E8%A3%85%E5%88%B0%E8%BF%90%E8%A1%8C)
6. [开发方法论：构建你自己的 Skill](about:blank#6-%E5%BC%80%E5%8F%91%E6%96%B9%E6%B3%95%E8%AE%BA%E6%9E%84%E5%BB%BA%E4%BD%A0%E8%87%AA%E5%B7%B1%E7%9A%84-skill)
7. [资源图谱：四层架构](about:blank#7-%E8%B5%84%E6%BA%90%E5%9B%BE%E8%B0%B1%E5%9B%9B%E5%B1%82%E6%9E%B6%E6%9E%84)
8. [安全与治理](about:blank#8-%E5%AE%89%E5%85%A8%E4%B8%8E%E6%B2%BB%E7%90%86)
9. [附录：模板与快速参考](about:blank#9-%E9%99%84%E5%BD%95%E6%A8%A1%E6%9D%BF%E4%B8%8E%E5%BF%AB%E9%80%9F%E5%8F%82%E8%80%83)

---

## 1. 序言：AI 应用逻辑的质变

把你工作中反复执行、有固定流程的任务，拆解成 AI 能理解、能稳定复用、能自动执行的一套流程——这不仅仅是”玩法”的升级，更是 AI 应用逻辑的一次质变。

我们正在经历从 **Prompt Engineering（提示词工程）** 向 **Flow Engineering（流程工程）** 的跨越。Claude Skills 的爆发，正是这一趋势的最佳注脚。哪怕是现在流行的 Vibe Coding（氛围编程），其尽头其实也是 Skills——将经验沉淀为流程，将直觉固化为逻辑。

### 1.1 重要里程碑

### 核心标准发布

- **2025年10月16日**：Anthropic 正式发布 Claude Skills，首次在 Claude 应用中支持技能系统
- **2025年12月18日**：Agent Skills 作为开放标准正式发布，实现跨平台互操作，规范发布于 agentskills.io

### 主流平台支持时间线

| 平台 | 支持时间 | 版本/说明 | 备注 |
| --- | --- | --- | --- |
| **Anthropic Claude** | 2025年10月16日 | Claude Skills 首次发布 | Pro/Max/Team/Enterprise 用户可用 |
| **Anthropic Claude API** | 2025年12月18日 | 开放标准发布后 | 通过 `/v1/skills` 端点支持 |
| **GitHub Copilot** | 2025年12月18日 | 同日支持开放标准 | Copilot coding agent、CLI、VS Code Insiders |
| **VS Code** | 2026年1月8日 | v1.108 | 实验性支持，需启用 `chat.useAgentSkills` 设置 |
| **VS Code（稳定版）** | 2026年1月 | v1.109 | Skills 作为斜杠命令、多 Agent 支持（Copilot/Claude/Codex） |
| **Google Anti-Gravity** | 2026年1月13日 | 正式支持 | 工作区技能和全局技能支持 |
| **Gemini CLI** | 2026年1月7日 | v0.24.0-preview | 预览版支持 |
| **Gemini CLI（稳定版）** | 2026年1月27日 | v0.26.0 | Skills 默认启用，内置 skill-creator，最新 v0.30.0 |
| **Cursor** | 2026年1月22日 | v2.4 | 编辑器与 CLI 全面支持，支持 `.cursor/skills/` 和 `~/.cursor/skills/` |
| **OpenAI Codex** | 2026年1月22日 | v0.89.0 | 新增 `/skill` UI 和斜杠命令选择改进 |
| **Skills CLI（Vercel）** | 2026年1月26日 | v1.1.1（开源） | `npx skills` 命令，支持 40+ Agent，最新 v1.4.1 |

### 其他相关平台

- **JetBrains IDEs**：通过 Agent Client Protocol (ACP) 支持，2025年11月18日发布自定义代理预览版
- **ChatGPT**：2025年7月17日发布 ChatGPT Agent，但 Agent Skills 支持情况未明确公开
- **Eclipse / Xcode**：2025年11月18日 GitHub Copilot 自定义代理预览版支持

### 标准演进时间线

1. **2025年10月16日**：Anthropic 发布 Claude Skills（专有实现）
2. **2025年12月9日**：Anthropic 将 Model Context Protocol (MCP) 捐赠给 Linux 基金会
3. **2025年12月18日**：Agent Skills 开放标准发布，GitHub Copilot 同日支持
4. **2026年1月**：主流开发工具全面支持（Cursor、Gemini CLI、VS Code 稳定版等），生态系统初步形成
5. **2026年1月26日**：Vercel 开源 Skills CLI（`npx skills`），发布 skills.sh 精选排行榜
6. **2026年2月**：生态爆发期，skills.sh 收录超 76,000 个 Skills，安全研究密集涌现

---

## 2. 核心定义：什么是 Skill

在传统的对话框交互中，我们给 AI 一个指令，AI 给一个反馈。但在工程化视角下，**Skill ≠ Prompt**。

### 2.1 基本概念

| 概念 | 定义 | 特点 |
| --- | --- | --- |
| **Prompt（提示词）** | 一次性的、非结构化的文本指令 | 临时性、难以复用 |
| **Skill（技能）** | 可复用的能力封装单元 | 模块化、版本控制、跨平台 |

根据 Anthropic 发布的官方规范，每个 Skill 是一个**目录（文件夹）**，其核心结构如下：

```
my-skill/
├── SKILL.md          # 必需：技能定义文件
├── scripts/          # 可选：可执行脚本
├── references/       # 可选：参考文档、模板
└── assets/           # 可选：静态资源（图片、数据等）
```

### 2.2 SKILL.md 文件规范

`SKILL.md` 是 Skill 的核心，包含两个部分：

### YAML Frontmatter（元数据）

```yaml
---
name: pdf-analyzer                    # 必需：唯一标识符（kebab-case，1-64字符）
description: 分析PDF文档并提取关键信息    # 必需：描述何时使用此技能（最大1024字符）
license: MIT                          # 可选：许可证
compatibility: Requires poppler, jq   # 可选：环境依赖说明（最大500字符）
metadata:                             # 可选：自定义键值对
  author: your-name
  version: "1.0"
allowed-tools: Bash(jq:*) Read        # 可选（实验性）：预授权工具列表
---
```

**元数据字段速查**：

| 字段 | 必需 | 约束 |
| --- | --- | --- |
| `name` | 是 | 1-64 字符，小写字母+数字+连字符，必须与目录名一致 |
| `description` | 是 | 1-1024 字符，说明"做什么"和"什么时候用" |
| `license` | 否 | 许可证名称或许可证文件的引用 |
| `compatibility` | 否 | 1-500 字符，环境要求（目标产品、系统依赖、网络需求等） |
| `metadata` | 否 | 任意键值对，用于 author、version 等扩展信息 |
| `allowed-tools` | 否 | 空格分隔的预授权工具列表（实验性，支持因平台而异） |

**命名规范**：
- 长度：1-64 字符
- 格式：小写字母、数字、连字符（kebab-case）
- 禁止：前导/尾随/连续连字符，保留名称（如 “anthropic”、“claude”）
- 推荐：使用动名词形式（如 `processing-pdfs`、`testing-code`）

### Markdown 正文（指令与说明）

- 功能描述与使用场景
- 具体操作步骤
- 输入/输出示例
- 边界条件与异常处理
- 注意事项

### 2.3 Skills vs MCP：定位区分

| 维度 | Skills | MCP (Model Context Protocol) |
| --- | --- | --- |
| **本质** | 流程/经验的封装 | 工具/接口的协议 |
| **核心内容** | 自然语言指令 + 可选脚本 | API schema + 函数调用 |
| **门槛** | 低（Markdown即可） | 中等（需要开发能力） |
| **适用场景** | 重复性流程、SOP自动化 | 外部工具集成、数据访问 |
| **关系** | 可以在 Skill 中调用 MCP 工具 | 提供底层能力支撑 |

**一句话总结**：MCP 是”连接器”，Skills 是”指挥官”。

### 2.4 理解 Skill 的直观类比

Skill 就像给 Agent 准备的**工作交接 SOP 大礼包**：

想象你要把一项工作交给新同事。若不靠口口相传，只靠文档交接，你会准备什么？

- 任务的执行 SOP 与必要背景知识（这件事大致怎么做）
- 工具的使用说明（用什么软件、怎么操作）
- 要用到的模板、素材（历史案例、格式规范）
- 可能遇到的问题、规范、解决方案（细节指引补充）

Skill 的设计架构，几乎是交接大礼包的数字版本：

| 组件 | 作用 | 对应交接材料 |
| --- | --- | --- |
| SKILL.md | 核心指令与元数据 | SOP文档 |
| scripts/ | 可执行脚本 | 工具使用手册 |
| references/ | 参考文档 | 背景知识材料 |
| assets/ | 静态资源 | 模板与素材 |

---

## 3. 技术架构：渐进式披露机制

### 3.1 为什么需要渐进式披露

正如有效的 Context 工程所证明的，上下文过长容易导致模型能力下降。由于 Skills 的本质就是 Context 工程，这个问题需要在 Skill Agent 中特别注意。

### 3.2 三层披露架构

| 层级 | 内容 | 加载时机 | Token 消耗 |
| --- | --- | --- | --- |
| **Level 1** | YAML 元数据（name + description） | 系统启动时 | ~100 tokens/技能 |
| **Level 2** | SKILL.md 正文 | 任务匹配时 | 建议 < 5000 tokens |
| **Level 3** | 脚本/资源文件 | 执行操作时 | 按需加载，无限制 |

### 3.3 加载流程详解

```
用户发送消息
    ↓
Agent 检查所有 Skills 的元数据（Level 1）
    ↓
判断消息是否与某个 Skill 的 description 匹配
    ↓
[匹配成功] → 读取 SKILL.md 完整内容（Level 2）
    ↓
根据任务需要，动态加载脚本/资源（Level 3）
    ↓
执行任务，返回结果
```

### 3.4 Token 管理策略

这种设计使得即使注册 50+ 个技能，初始上下文消耗也仅约 5000 tokens，极大优化了资源管理。

**最佳实践**：
- Level 1：保持元数据简洁，description 控制在 200 字符以内
- Level 2：SKILL.md 正文建议控制在 500 行以内
- Level 3：复杂子技能拆分为独立文档，按需加载

---

## 4. Skills 的真实价值

Skills 与其他 AI 应用开发方式有底层机制的不同：**人给出专业知识与工具方法，通用 Agent 提供智能，自主理解，主动执行。**

### 4.1 零代码创建垂直 Agent

**入门门槛极低，智能上限极高**。

### 简单示例：品牌设计规范 Skill

Anthropic 官方的 `brand-guidelines` skill 仅有一个 SKILL.md，纯自然语言写成：

```yaml
---
name: brand-guidelines
description: 当设计需要遵循 Anthropic 品牌规范时使用此技能
---

# 品牌设计规范

## 品牌颜色
- 主色：#CC785C（Anthropic Orange）
- 辅助色：#191919（Near Black）
- 背景色：#FAFAF8（Off White）

## 字体规范
- 标题：Tiempos Headline
- 正文：Söhne
```

这就足以引导 Agent 变成符合 Anthropic 品牌设计的垂直 Agent，可用于品牌官网、海报、PPT 设计。

### 复杂示例：AI 伴侣 Skill

包含 SKILL 文档、向量数据库构建指南、向量数据库使用脚本、AI 伴侣与用户的 Persona 模板资源。Agent 能够：

1. 引导用户上传包含个人记忆的文档语料
2. 在用户端智能切分笔记片段，构建向量数据
3. 解析用户记忆文档，提炼个性化的 AI 伴侣与用户画像设定
4. 智能检索用户记忆，提供懂用户的对话体验

### 4.2 灵活应对边界情况

Workflow 或传统程序的核心问题是，它们假设所有情况都能预设。但现实往往是：

- 需要教育用户在哪点击「导入」
- 用户只有预期之外的格式：预期支持 md，但实际只有 doc
- 数据字段不符：预期每个文件需要一个标题，但用户文件没有标题

**通用 Agent + Skill 的运作方式完全不同**：

| 传统方式 | Agent + Skill |
| --- | --- |
| 只能按预设路径执行 | 能在统一对话框接收各类数据 |
| 遇到意外就报错 | 自主调用其他 Skill 或编写脚本转换格式 |
| 要求用户自行消除差距 | 基于 LLM 推理弥合各类边缘问题 |

### 4.3 多 Skills 自由联用

Skills 在实际应用中极其灵活，甚至在一次任务中能调用多个 Skill：

| 联用场景 | Skills 组合 |
| --- | --- |
| 品牌规范 PPT | brand-guidelines + pptx |
| 个性化写作 | AI-Partner-Chat + Article-Copilot |
| 产品分析报告 | Web Scraping + PDF + Data Analysis + PPTX |

每多一个 Skill，就多一种能力，N 个 Skill 可以应对远超 N 的应用场景。

### 4.4 对 AI 产品设计的影响

Skills-based 的 Agent 产品，能用同一个多模态输入框，处理用户各种不同的输入，也能灵活应对未被规划的边缘问题、为用户提供绝对个性化的生成需求。

**未来趋势推演**：

```
传统 APP 逻辑：用户输入 → 代码逻辑 → 固定处理
    ↓
AI Native 逻辑：用户输入 → Agent 判断 → 匹配 Skill → 智能处理
```

---

## 5. 使用教程：从安装到运行

### 5.1 Claude Code 安装

Claude Code 是目前使用 Skills 最推荐的本地方式。

### Step 1：安装 Claude Code

打开「终端/命令行」工具，遵循官方安装指引：

- 官方文档：https://docs.claude.com/en/docs/claude-code/quickstart

安装完成后验证：

```bash
claude --version
```

看到版本号即表示安装成功。

### Step 2：模型配置（可选）

如果需要使用非 Claude 模型，可以替换：

**方法一：手动配置**

参考各模型厂商的 Claude Code 接入教程（如 GLM 4.7、Kimi K2-thinking）。

**方法二：使用 CC Switch 工具**

项目地址：https://github.com/farion1231/cc-switch

```bash
pip install cc-switch
cc-switch list
cc-switch use <model-name>
```

### 5.2 Skills 安装方法

Skills 有三种存放位置（以 Claude Code 为例，其他平台路径类似）：

| 类型 | 路径（Claude Code） | 路径（Cursor） | 作用范围 |
| --- | --- | --- | --- |
| **个人 Skills** | `~/.claude/skills/` | `~/.cursor/skills/` | 所有项目可用 |
| **项目 Skills** | `.claude/skills/`（项目根目录） | `.cursor/skills/`（项目根目录） | 仅当前项目 |
| **插件 Skills** | 通过 `/plugin install` 安装 | — | 取决于插件配置 |

### 方法一：使用 Skills CLI（推荐）

Vercel 开源的 Skills CLI 是目前最便捷的跨平台安装方式，支持 40+ 种 Agent：

```bash
npx skills add <github-repo-path>
```

**常用命令**：

| 命令 | 功能 |
| --- | --- |
| `npx skills find [query]` | 交互式搜索 Skills（支持边输边搜） |
| `npx skills add <package>` | 从 GitHub 等来源安装 Skill |
| `npx skills check` | 检查已安装 Skills 的更新 |
| `npx skills update` | 更新所有已安装 Skills |

**示例**：

```bash
npx skills add vercel-labs/agent-skills
npx skills add anthropics/skills
npx skills find "react best practices"
```

### 方法二：手动安装

```bash
mkdir -p ~/.claude/skills/my-skill
cp -r downloaded-skill/* ~/.claude/skills/my-skill/
```

### 方法三：让 Claude Code 自动安装

在 Claude Code 中发送：

```
安装 skill，skill 项目地址为：https://github.com/anthropics/skills/tree/main/skills/pdf
```

### 方法四：使用插件系统

```
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

### 5.3 使用 Skills

### 显式调用

```
开始使用 pdf skill
```

### 隐式触发

当用户消息与 skill 元数据的 description 匹配时，Agent 会自动调用：

```
帮我把这个 PDF 文件提取成文本
```

（如果已安装 pdf skill，会自动触发）

### 5.4 使用 skill-creator 创建 Skill

Anthropic 官方提供了 `skill-creator` 这个元 Skill，用来帮助自动开发 Skill。

### 安装 skill-creator

```
安装 skill，skill 项目地址为：https://github.com/anthropics/skills/tree/main/skills/skill-creator
```

### 创建自定义 Skill

在 Claude Code 中发送创建需求：

```
创建一个 skill，能够自动将 PDF 转换为 Word 文档
```

Claude Code 会自动调用 skill-creator，生成 SKILL.md 和必要的脚本文件。

---

## 6. 开发方法论：构建你自己的 Skill

### 6.1 SDTK 开发流程

建议遵循 **SDTK（Specify-Design-Test-Keep）** 开发流程：

### Step 1: Specify（明确规格）

在动手之前，先回答这些问题：

| 问题 | 说明 |
| --- | --- |
| 触发条件 | 用户说什么话会激活这个技能？ |
| 输入格式 | 需要什么数据？文件/文本/参数？ |
| 输出格式 | 返回什么？JSON/文件/操作结果？ |
| 边界条件 | 哪些情况不处理？如何优雅失败？ |

### Step 2: Design（设计流程）

编写 SKILL.md 正文时的关键原则：

- **Chain of Thought (CoT)**：在指令中强制 AI 先思考再行动
- **防御性 Prompting**：明确边界条件，“如果缺少数据，请返回说明，不要编造”
- **确定性优先**：对于计算、格式转换等任务，优先使用脚本而非让 LLM 直接处理

```markdown
## 执行步骤

1.首先检查输入文件是否为有效代码文件
2.如果不是代码文件，返回：`"错误：请提供有效的代码文件"`
3.分析代码结构...
```

### Step 3: Test（测试验证）

| 测试类型 | 检查内容 |
| --- | --- |
| 正向测试 | 技能是否在预期情况下被正确调用？ |
| 边界测试 | 模糊输入、错误输入时表现如何？ |
| 性能测试 | Token 消耗是否在预期范围内？ |

### Step 4: Keep（固化与复用）

- **项目级技能**：放在项目的 `.claude/skills/` 目录下
- **全局技能**：放在用户级别的 `~/.claude/skills/` 目录
- **版本控制**：将技能纳入 Git 管理，记录变更历史

### 6.2 SKILL.md 编写最佳实践

### 元数据编写

```yaml
---
name: code-reviewer
description: 当用户请求代码审查、Review代码、检查代码质量时使用此技能。支持多种编程语言，提供详细的代码质量报告。
license: MIT
metadata:
  author: your-name
  version: "1.0"
---
```

**description 要点**：
- 明确说明”做什么”和”什么时候用”
- 包含关键触发词
- 控制在 200 字符以内

### 正文结构建议

```markdown
# 技能名称

## 概述
简要说明技能的核心功能。

## 使用场景
-场景1：具体描述
-场景2：具体描述

## 执行步骤
1.步骤一：具体操作
2.步骤二：具体操作

## 输入/输出示例

**输入**：
用户提供的代码文件

**输出**：
代码审查报告，包含问题列表和改进建议

## 边界条件与错误处理
-如果输入无效，返回错误提示
-如果文件过大，提示分段处理

## 注意事项
-不要修改原始代码
-保持客观中立的评价
```

---

## 7. 资源图谱：四层架构

### 到哪里去找好用的 Skills？推荐三个网站 + 1 个 Skill

在深入各层资源之前，先回答最常见的问题——**去哪里找？**

| 推荐 | 名称 | 地址 | 特点 |
| --- | --- | --- | --- |
| 网站 1 | **SkillsMP** | [skillsmp.com](https://skillsmp.com/) | 全网最大的 Skills 聚合平台（70,000+），分类齐全，适合浏览发现 |
| 网站 2 | **Claude Skills 中文站** | [skills.deeptoai.com](https://skills.deeptoai.com/) | 深度技术分析、开发指南，适合学习 Skills 原理和最佳实践 |
| 网站 3 | **Skills.sh** | [skills.sh](https://skills.sh/) | Vercel 开源排行榜（76,000+），有安装量数据和 AI 安全审查，适合找高质量 Skills |
| Skill | **find-skills** | `npx skills find` | 安装量 334.2K 的元技能，让 Agent 自己帮你搜索和安装 Skills |

**快速上手**：如果只记一个命令，记住 `npx skills find`——在任何支持 Agent Skills 的工具中，它能帮你搜索、发现、安装所需的 Skills。

### 7.1 第一层：官方标准（The Gold Standard）

### Anthropic Skills 官方仓库

- **地址**：https://github.com/anthropics/skills
- **Stars**：76k+（截至2026年2月）

**包含的核心 Skills**：

| Skill ID | 功能 | skills.sh 安装量 |
| --- | --- | --- |
| `frontend-design` | 前端设计最佳实践 | 102.2K |
| `skill-creator` | 帮助创建新 Skill 的元技能 | 50.3K |
| `pdf` | PDF 提取（文本、表格、元数据、合并） | 22.4K |
| `pptx` | PPT 生成与调整 | 18.7K |
| `docx` | Word 文档处理（创建、编辑、追踪修改） | 17.1K |
| `xlsx` | Excel 操作（公式、图表、数据转换） | 16.5K |
| `webapp-testing` | Web 应用测试 | 15.1K |
| `mcp-builder` | MCP 服务构建器 | 13.4K |
| `canvas-design` | Canvas 画布设计 | 11.5K |
| `brand-guidelines` | 品牌设计规范示例 | 8.5K |

**仓库结构**：

```
anthropics/skills/
├── skills/           # 生产级 Skills
├── template/         # Skill 模板
├── spec/             # 官方规范文档
└── README.md
```

### Agent Skills 开放标准

- **官网**：[https://agentskills.io](https://agentskills.io/)
- **规范文档**：https://agentskills.io/specification
- **规范仓库**：https://github.com/agentskills/agentskills（11k+ Stars，30+ 贡献者）
- **验证工具**：`skills-ref validate ./my-skill`（官方验证库）

**已支持的平台（40+）**：
- Anthropic Claude（Claude Code、Claude.ai、API）
- OpenAI Codex CLI
- Microsoft VS Code、GitHub Copilot
- Google Gemini CLI、Anti-Gravity
- Cursor、Amp、Letta、OpenCode
- Windsurf、Goose、ElevenLabs Agents 等

### 7.2 第二层：开源模式库（The Open Source Patterns）

### ComposioHQ/awesome-claude-skills

- **地址**：https://github.com/ComposioHQ/awesome-claude-skills
- **特点**：强调实用工作流，覆盖文档处理、编码工具、业务营销、项目管理等

**精选 Skills**：
- Connect Apps：通过 Composio 连接 500+ 应用
- Changelog Generator：自动生成变更日志
- AWS Skills：AWS 服务操作技能
- Playwright Browser Automation：浏览器自动化

### VoltAgent/awesome-claude-skills

- **地址**：https://github.com/VoltAgent/awesome-claude-skills
- **特点**：官方和社区 Skills 的精选集合

### 7.3 第三层：Skills 市场（The App Store）

### Skills.sh（Vercel 开源生态与排行榜）

- **地址**：[https://skills.sh](https://skills.sh/)
- **规模**：**76,000+** Skills（截至2026年2月）
- **CLI 仓库**：https://github.com/vercel-labs/skills（6.5k+ Stars，已开源）
- **CLI 最新版本**：v1.4.1
- **特点**：Vercel 推出的**开放 Agent Skills 生态系统**，集排行榜、CLI 工具、安全审查于一体

**四大优势**：

| 特点 | 说明 |
| --- | --- |
| **有背书** | 排行榜上的 Skills 来自 Vercel、Anthropic、Microsoft、Expo、Google 等知名团队 |
| **多平台兼容** | 支持 **40+** 种 AI Agent：Claude Code、Cursor、GitHub Copilot、Windsurf、Codex、Gemini CLI、OpenCode 等 |
| **下载量透明** | 基于 `npx skills add` 匿名遥测数据，社区自动筛选，无人工推荐干预 |
| **AI 安全审查** | 每个安装的 Skill 自动经过 AI 安全扫描（恶意代码、混淆、可疑模式检测），排行榜完整性由 AI Agent 监控 |

**一键安装**：

```bash
npx skills add vercel-labs/agent-skills
```

**热门 Skills 示例**（截至2026年2月）：
- `find-skills`：334.2K 安装（Skills 发现与安装元技能）
- `vercel-react-best-practices`：170.4K 安装
- `web-design-guidelines`：130.3K 安装
- `remotion-best-practices`：113.5K 安装

### SkillsMP

- **地址**：[https://skillsmp.com](https://skillsmp.com/)
- **规模**：70,000+ Skills（从公开 GitHub 仓库自动聚合）
- **月访问量**：约 120 万
- **功能**：智能搜索、分类筛选、一键安装、自定义 Skill 创建

**分类**：
Tools、Development、Data & AI、Business、DevOps、Testing & Security、Documentation、Content & Media、Research、Databases、Lifestyle、Blockchain

> 生态观察：Skills 可能是唯一一个开发者比用户还多的技术。这说明有太多聪明人、有能力的人，愿意把自己的经验和智慧封装成 Skill 分享给全世界。而 skills.sh、SkillsMP 这样的平台，正是帮助用户轻松用起这些优质 Skills 的桥梁。

### Claude Skills 中文站

- **地址**：[https://skills.deeptoai.com](https://skills.deeptoai.com/)
- **特点**：提供中英法多语言支持，包含深度技术分析文章、Skill 架构解析、开发最佳实践等 20+ 篇专题内容
- **亮点**：包括"Claude Agent Skills: A First Principles Deep Dive"等高质量技术文档，以及 `skill-article-writer`、`skill-creator` 等工具实战指南

### 7.4 第四层：热门项目

### obra/superpowers

- **地址**：https://github.com/obra/superpowers
- **Stars**：55k+（截至2026年2月）
- **最新版本**：v4.1.1（2026年1月23日）
- **作者**：Jesse Vincent

**核心理念**：
- 强制 TDD（测试驱动开发）
- YAGNI 原则（不写用不到的代码）
- DRY 原则（不重复自己）

**包含的核心技能**（skills.sh 安装量）：

| 技能 | 作用 | 安装量 |
| --- | --- | --- |
| `brainstorming` | 结构化头脑风暴 | 32.1K |
| `systematic-debugging` | 系统化定位问题 | 17.5K |
| `writing-plans` | 编写实施计划 | 15.7K |
| `test-driven-development` | 红-绿-重构的 TDD 流程 | 14.4K |
| `executing-plans` | 按计划执行开发 | 13.3K |
| `requesting-code-review` | 发起代码审查 | 12.6K |
| `subagent-driven-development` | 子 Agent 驱动开发 | 10.7K |
| `verification-before-completion` | 完成前验证 | 10.2K |

**安装方式**：

```bash
npx skills add obra/superpowers
```

或通过插件系统：

```
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

**用户反馈**：用 superpowers 之后，Claude 可以自主编程 2 小时以上不跑偏。

### Skills CLI 与 find-skills（Vercel Labs）

- **CLI 仓库**：https://github.com/vercel-labs/skills（6.5k+ Stars，已完全开源）
- **Skills.sh 安装量**：find-skills 334.2K（排名第1）
- **最新版本**：v1.4.1（2026年2月）
- **支持 Agent**：40+ 种（Claude Code、OpenCode、Codex、Cursor、Gemini CLI、GitHub Copilot 等）

Skills CLI（`npx skills`）是 Agent Skills 生态的**包管理器**，相当于 Skills 界的 npm。它同时包含一个名为 `find-skills` 的元 Skill，可以在 Agent 内部直接搜索和安装 Skills。

**CLI 命令**：

```bash
npx skills add <github-repo-path>
npx skills find [query]
npx skills check
npx skills update
```

**find-skills 跨平台安装统计**（截至2026年2月）：

| Agent 平台 | 安装量 |
| --- | --- |
| OpenCode | 145.6K |
| Codex | 142.3K |
| Gemini CLI | 132.4K |
| GitHub Copilot | 129.7K |
| Amp | 124.8K |
| Claude Code | 123.4K |

> 注：`npx add-skill` 为旧版命令，已在 v1.1.1 中弃用，请统一使用 `npx skills`。

### videocut-skills（视频剪辑 Skill）

- **地址**：https://github.com/Ceeon/videocut-skills
- **功能**：辅助视频处理，识别口误、静音片段、语气词并自动剪辑

**核心技术**：
- 使用 **Whisper 模型**生成字幕，支持词典纠错
- 利用 **FFmpeg** 进行底层视频剪辑
- 智能体具备自我更新能力，根据使用习惯优化剪辑规则

**安装**：

```bash
git clone https://github.com/Ceeon/videocut-skills.git ~/.claude/skills/videocut
```

**使用**：在 Claude Code 中输入 `/videocut:安装`，AI 会自动安装依赖、下载模型（约 5GB）。

**适用场景**：频繁制作口播类视频的创作者。

### Humanizer-zh（去除 AI 味儿）

- **地址**：https://github.com/op7418/Humanizer-zh
- **功能**：消除文本中 AI 生成痕迹，让文章语气更真实、生动

基于维基百科关于 AI 写作特征的指南，内置多种检测维度：内容、语言语法、风格、交流模式。识别 AI 常有的表达方式并针对性重写。

**安装**：

```bash
git clone https://github.com/op7418/Humanizer-zh.git ~/.claude/skills/humanizer-zh
```

**使用**：重启 Claude Code 后，输入 `/humanizer-zh` 激活，然后接上想要去除 AI 味儿的文本。

### Auto-Redbook-Skills（小红书发布）

- **地址**：https://github.com/comeonzhj/Auto-Redbook-Skills
- **功能**：撰写、制作并发布小红书笔记

**核心特性**：
- 根据设定主题自动生成符合平台风格的文案
- 利用 **Playwright** 浏览器自动化将 Markdown 渲染为精美图片
- 支持自定义背景渐变和封面样式
- 一键发布到小红书平台

**技术支持**：提供 Python 和 Node.js 两种脚本方案。

### 7.5 Skills.sh 全站排行榜 TOP 20（2026年2月）

数据来源：[skills.sh](https://skills.sh/) All Time 排行榜，基于 `npx skills add` 匿名安装遥测。

| 排名 | Skill 名称 | 来源 | 安装量 | 功能介绍 |
| --- | --- | --- | --- | --- |
| 1 | find-skills | vercel-labs/skills | 334.2K | Skills 发现与安装元技能 |
| 2 | vercel-react-best-practices | vercel-labs/agent-skills | 170.4K | React 开发最佳实践 |
| 3 | web-design-guidelines | vercel-labs/agent-skills | 130.3K | Web 设计规范指南 |
| 4 | remotion-best-practices | remotion-dev/skills | 113.5K | Remotion 视频开发最佳实践 |
| 5 | frontend-design | anthropics/skills | 102.2K | 前端设计（Anthropic 官方） |
| 6-22 | azure-* 系列 | microsoft/github-copilot-for-azure | ~69.8K | Microsoft Azure 全套云服务技能（17个） |
| 23 | agent-browser | vercel-labs/agent-browser | 62.0K | Agent 浏览器自动化 |
| 24 | vercel-composition-patterns | vercel-labs/agent-skills | 58.9K | Vercel 组合模式 |
| 25 | skill-creator | anthropics/skills | 50.3K | Skill 创建元技能（Anthropic 官方） |
| 26 | browser-use | browser-use/browser-use | 40.5K | 浏览器操控 |
| 27 | ui-ux-pro-max | nextlevelbuilder/... | 39.6K | UI/UX 专业设计 |
| 28 | brainstorming | obra/superpowers | 32.1K | 结构化头脑风暴 |
| 29 | audit-website | squirrelscan/skills | 27.6K | 网站审计 |
| 30 | seo-audit | coreyhaines31/marketingskills | 27.6K | SEO 审计 |

**生态亮点**：
- **Microsoft** 通过 `github-copilot-for-azure` 一次性贡献了 17 个 Azure 云服务 Skills，占据排行榜 6-22 位
- **Vercel** 和 **Anthropic** 是头部 Skills 的主要贡献者
- **营销类 Skills**（coreyhaines31/marketingskills）覆盖 SEO、文案、定价策略等 15+ 个子技能，显示 Skills 已超越纯编程领域

---

## 8. 安全与治理

> 重要提醒：2026年初的多项独立安全研究表明，Skills 生态存在显著的安全风险。不同研究的检出率从 26.1% 到 36.8% 不等，攻击成功率高达 80-85%。这是当前 Agent Skills 生态中最值得重视的问题。

### 8.1 最新安全研究概览

| 研究/来源 | 发现 | 时间 |
| --- | --- | --- |
| **学术研究**（arXiv 2601.10338） | 26.1% 的公开 Skills 存在至少一个安全漏洞，涉及 14 种不同漏洞模式 | 2026年1月 |
| **Snyk ToxicSkills 研究** | 36.82%（1,467个）Skills 存在安全缺陷，其中 13.4% 为严重级别；确认 157 个恶意 Skills | 2026年2月 |
| **SkillInject 基准**（arXiv 2602.20156） | 前沿 LLM Agent 面对 Skill 注入攻击时，成功率高达 **80%**，可执行数据窃取、破坏性操作甚至勒索软件行为 | 2026年2月 |
| **Agentic 编码助手分析**（arXiv 2601.17548） | 对 Claude Code、GitHub Copilot、Cursor 等的多向量攻击成功率超过 **85%**，现有防御措施缓解率不足 50% | 2026年1月 |

**关键发现**：包含可执行脚本（scripts/）的 Skills 出现漏洞的概率是纯指令型 Skills 的 **2.12 倍**。

### 8.2 主要风险类型

| 风险类型 | 说明 | 危害程度 | 检出占比 |
| --- | --- | --- | --- |
| **Prompt Injection** | 恶意 SKILL.md 内容注入 | 高 | 36%+ |
| **数据泄露** | 敏感信息通过技能外流 | 高 | 13.3% |
| **权限提升** | 脚本获取超出预期的权限 | 高 | 11.8% |
| **恶意代码执行** | scripts/ 中的恶意脚本 | 严重 | — |
| **供应链攻击** | 第三方 Skill 被篡改或植入恶意代码 | 严重 | 157 例确认 |

### 8.3 攻击向量详解

### Prompt Injection

攻击者在文档、代码注释、文件上传或网页内容中隐藏恶意指令。AI 无法始终区分用户指令和嵌入内容中的恶意指令。最新研究表明，即使是最先进的防御机制，缓解率也不足 50%，说明这需要架构级别的解决方案。

### 恶意 Skill 植入

已有研究证明：修改合法的 Skills 插件（如 GIF Creator），插入隐藏 payload，在用户启用 Skill 后下载并执行勒索软件（如 MedusaLocker）。Snyk 研究确认了 157 个此类恶意 Skills，共包含 632 个漏洞。

### 数据外泄

攻击者可利用 Claude 的沙箱 + File API 写出数据（如对话历史、集成服务中的文件），然后使用攻击者的 API key 上传到恶意端点。

### 8.4 平台级安全措施

skills.sh 作为生态中心，已引入 AI 驱动的安全机制：
- **自动安全审查**：每个通过 `npx skills add` 安装的 Skill 自动接受 AI 扫描，检测恶意代码、混淆和可疑模式
- **排行榜完整性监控**：AI Agent 持续分析安装模式，检测并标记人为刷量行为
- **规范验证**：官方提供 `skills-ref validate` 工具，验证 SKILL.md 格式合规性

### 8.5 最佳安全实践

| 策略 | 说明 |
| --- | --- |
| **来源可信** | 优先使用 skills.sh 排行榜前列的知名团队 Skills |
| **代码审查** | 使用前务必检查 scripts/ 目录内容（含脚本的 Skills 风险高 2.12 倍） |
| **最小权限** | 限制技能可访问的资源范围，善用 `allowed-tools` 字段 |
| **日志审计** | 记录技能执行的关键操作 |
| **沙箱执行** | 在隔离环境中运行脚本 |
| **网络限制** | 使用域名白名单，限制出站连接 |
| **运行时监控** | 记录所有文件/代码下载、外部连接 |
| **定期更新** | 使用 `npx skills check` 和 `npx skills update` 保持 Skills 最新 |

### 8.6 企业部署建议

1. **集中管理**：通过 Team/Enterprise 账户统一部署和管理 Skills
2. **审批流程**：建立 Skill 上架前的安全审查流程
3. **权限分级**：根据 Skill 风险等级设置不同的执行权限
4. **定期审计**：定期检查已部署 Skills 的安全状态
5. **应急响应**：制定 Skill 安全事件的应急处理预案

### 8.7 Anthropic 的官方立场

Anthropic 表示：
- 用户有责任确保 Skills 来源可信
- Skills 被设计为”可执行代码”，用户在启用前会收到警告
- 提供的缓解措施包括：禁用网络访问、使用域名白名单、运行时行为监控

---

## 9. 附录：模板与快速参考

### 9.1 SKILL.md 完整模板

```yaml
---
name: my-skill-name
description: 简洁描述这个技能做什么，以及什么时候应该使用它
license: MIT
metadata:
  author: your-name
  version: "1.0"
---

# 技能名称

## 概述

这个技能用于...

## 使用场景

- 场景1：当用户需要...
- 场景2：当用户请求...

## 执行步骤

1. 首先，检查输入是否有效
2. 然后，执行核心操作
3. 最后，返回结果

## 输入/输出示例

**输入**：
```

示例输入内容

```

**输出**：
```

示例输出内容

```

## 边界条件与错误处理

- 如果输入无效，返回：`"错误：请提供有效的输入"`
- 如果资源不可用，提示用户检查配置

## 注意事项

- 注意事项1
- 注意事项2
```

### 9.2 Skills 目录结构模板

```
my-skill/
├── SKILL.md                 # 必需：核心指令文件
├── scripts/                 # 可选：可执行脚本
│   ├── main.py
│   └── utils.py
├── references/              # 可选：参考文档
│   └── api-guide.md
├── assets/                  # 可选：静态资源
│   ├── template.docx
│   └── logo.png
└── README.md                # 可选：说明文档
```

### 9.3 按用途速查表

| 你要干什么 | 装这个 | 来源 | 安装量 |
| --- | --- | --- | --- |
| 搜索和安装 Skills | find-skills (`npx skills find`) | Vercel Labs | 334.2K |
| React 最佳实践 | vercel-react-best-practices | Vercel Labs | 170.4K |
| Web 设计规范 | web-design-guidelines | Vercel Labs | 130.3K |
| 前端设计 | frontend-design | Anthropic 官方 | 102.2K |
| Azure 云服务全套 | azure-* 系列 | Microsoft | ~69.8K |
| 浏览器自动化 | agent-browser | Vercel Labs | 62.0K |
| 创建自己的 Skill | skill-creator | Anthropic 官方 | 50.3K |
| 像高级工程师一样写代码 | obra/superpowers | 社区 | 32.1K |
| SEO 审计 | seo-audit | 社区 | 27.6K |
| Supabase 最佳实践 | supabase-postgres-best-practices | Supabase | 24.7K |
| 处理 PDF 文档 | pdf | Anthropic 官方 | 22.4K |
| 处理 PPT/Word/Excel | pptx / docx / xlsx | Anthropic 官方 | 17-19K |
| 视频剪辑（口误/静音/语气词处理） | videocut-skills | 社区 | — |
| 去除文本的 AI 味儿 | Humanizer-zh | 社区 | 4.7K |
| 自动发布小红书笔记 | Auto-Redbook-Skills | 社区 | — |
| 跨平台安装 Skills | Skills CLI (`npx skills add`) | Vercel Labs | — |

### 9.4 什么时候应该用 Skills？

### 场景1：反复向 AI 解释同一件事

最典型的信号：为了完成某个任务，在多轮对话中不断向 AI 解释规范和流程。

### 场景2：任务需要特定知识、模板、材料

典型场景：
- 技术文档写作：需要参考代码规范、术语表
- 品牌设计：需要参考品牌手册、色彩规范
- 数据分析：需要参考指标定义、计算公式

### 场景3：任务需要多个流程协同

典型场景：
- 竞品分析报告：检索数据 + 分析 + 制作 PPT
- 内容生产：收集资料 + 学习风格 + 大纲协作 + 正文写作

### 9.5 相关资源链接

| 类型 | 链接 |
| --- | --- |
| **官方仓库** | https://github.com/anthropics/skills |
| **官方文档** | https://docs.claude.com/en/docs/claude-code/skills |
| **Agent Skills 规范** | https://agentskills.io/specification |
| **Agent Skills 规范仓库** | https://github.com/agentskills/agentskills |
| **Skills CLI（Vercel 开源）** | https://github.com/vercel-labs/skills |
| **Skills.sh（排行榜与生态）** | [https://skills.sh](https://skills.sh/) |
| **Skills 市场（SkillsMP）** | [https://skillsmp.com](https://skillsmp.com/) |
| **Claude Skills 中文站** | [https://skills.deeptoai.com](https://skills.deeptoai.com/) |
| **awesome-claude-skills (ComposioHQ)** | https://github.com/ComposioHQ/awesome-claude-skills |
| **awesome-claude-skills (VoltAgent)** | https://github.com/VoltAgent/awesome-claude-skills |
| **obra/superpowers** | https://github.com/obra/superpowers |
| **videocut-skills（视频剪辑）** | https://github.com/Ceeon/videocut-skills |
| **Humanizer-zh（去 AI 味儿）** | https://github.com/op7418/Humanizer-zh |
| **Auto-Redbook-Skills（小红书）** | https://github.com/comeonzhj/Auto-Redbook-Skills |
| **Cursor Rules** | https://github.com/patrickjs/awesome-cursorrules |

---

## 结语：未来的竞争壁垒

未来真正有价值的，不是谁的 Prompt 写得最花，也不是谁一次能生成最多内容。

**真正的壁垒在于**：

1. **谁最懂业务流程**：能够识别出那些值得自动化的关键节点
2. **谁能沉淀 SOP**：将隐性的经验转化为显性的标准化作业程序
3. **谁能驾驭 AI 执行**：把这些 SOP 封装成 robust（鲁棒）的 Skills，交给 AI 稳定执行
4. **谁能确保安全合规**：在效率与风险之间找到平衡点

Agent Skills 开放标准，正是这条路上最值得研究的一套范式。从 Anthropic 的专有实现到跨平台开放标准，从 76,000+ Skills 的生态爆发到 AI 驱动的安全审查，这个生态正在以惊人的速度成熟。

**巧借通用 Agent 内核，只靠 Skills 设计，就能低成本创造具有通用 AI 智能上限的垂直 Agent 应用。**

---

*文档生成时间：2026年1月24日*

*最后数据更新：2026年2月27日（全面更新：规范字段、平台时间线、排行榜数据、安全研究、Skills 发现指南）*