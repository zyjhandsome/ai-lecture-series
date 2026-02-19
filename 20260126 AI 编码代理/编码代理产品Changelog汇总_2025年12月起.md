# 编码代理产品 Changelog 汇总（2025年4月 ~ 2026年2月中旬）

> 本文档为[《AI 编码代理产品形态全景（2026年1月）》](./20250126%20AI%20编码代理产品形态全景.md)的配套文档。全景文档回答"有哪些产品、怎么选"，本文档回答"**这些产品最近做了什么、行业往哪走**"。覆盖范围含专业编码代理（Cursor、Copilot、Claude Code、Codex 等）和通用 AI 平台的编码能力（ChatGPT Canvas、Claude.ai Artifacts、Gemini Code Assist、Grok Build 等）。

---

## 0. 执行摘要

| 功能维度 | 核心趋势 | 代表性更新 |
|---------|---------|----------|
| **长时自主代理** | 从"对话式辅助"到"小时级/天级自主编码"，是最新最核心的能力跃迁 | Cursor Long-Running Agents（52 小时 / 151K 行代码）、Self-Driving Codebase（1000 commits/h）、Codex Floating Window（跟随式执行） |
| **多代理/子代理架构** | 从单代理到多代理协作，是最核心的架构演进 | Cursor Subagents、Claude Code Agent Teams（16 实例协作）、Bolt v2 多代理架构、Gemini CLI v0.28 Subagent 进化 |
| **规划模式** | "先规划再执行"成为行业标配 | Cursor / Copilot CLI / Windsurf / Gemini CLI / Gemini Code Assist / Lovable / Bolt 全面支持 |
| **调试与运行时智能** | 从"写代码"向"理解运行时行为"进化 | Cursor Debug Mode、Lovable Browser Testing、ChatGPT Canvas 代码审查 |
| **CLI 代理** | CLI 从辅助终端进化为独立开发入口 | Cursor CLI、Copilot CLI、Gemini CLI、Codex CLI、Grok Build CLI 五线并进 |
| **Skills 与可扩展性** | 从 Prompt Engineering 到 Flow Engineering | SKILL.md / AGENTS.md 生态 + MCP 协议（Figma MCP / Augment Context Engine MCP / Artifacts MCP）+ Extensions GA + GitHub Agentic Workflows |
| **Hooks 与生命周期控制** | 代理不再是黑盒，开发者可注入自定义逻辑 | Claude Code 8 种 Hook 类型、Cursor Hooks **40x** 性能提升 |
| **模型更新** | 多模型并存、编码专用与通用推理分化加速 | Claude Opus 4.6（**1M** 上下文）、GPT-5.3-Codex-Spark（**1000+ tokens/s**）、Gemini 2.5 Pro/Flash、Grok 4/Code Fast 1、GitHub Copilot 旧模型批量淘汰 |
| **企业级功能** | 从个人工具向企业基础设施演进 | Cursor Enterprise、Augment Analytics API、Lovable 环境隔离、Grok Build 空气隔离 |
| **UI/UX 与交互创新** | IDE 从"编辑器中心"向"代理中心"转型，通用平台向编码工作区延伸 | Cursor 四种布局、Windsurf Arena、Codex Steer Mode + Floating Window、ChatGPT Canvas、Claude Code on Web |
| **图像生成与多模态** | 从纯文本走向多模态 | Cursor 图像生成、Figma Make/Vectorize、Claude Artifacts 交互式应用、Gemini 2.5 原生多模态 |

> **关键判断**：2025Q4—2026Q1 是编码代理行业从"功能竞争"向"架构竞争"的转折期。**长时自主代理（Long-Running Agents）** 的出现是 2026 年 2 月最具标志性的突破——Cursor 的代理已能连续自主工作 52 小时生成 15 万行代码，Self-Driving Codebase 研究实现了每小时 1000 次提交。这标志着编码代理正在从"人类监督下的助手"进化为"可独立交付的虚拟开发者"。与此同时，多代理、Skills、Hooks 三个维度的集中爆发，标志着编码代理正在从"一个聪明的对话框"进化为"可编排、可扩展、可审计的软件开发平台"。**通用 AI 平台正从对话界面向专业编码工作区延伸**——ChatGPT Canvas 提供代码审查与实时渲染、Claude Code on Web 支持云端并行编码任务、Gemini Code Assist Agent Mode 直接在 IDE 中实现自主多步骤编码。此外，全栈应用生成器（Bolt、Lovable）和设计工具（Figma）正在从另一端接近同一目标，**xAI 的 Grok Build 作为新进入者**也加入了编码代理竞争。**GitHub Agentic Workflows 的发布**则将代理能力嵌入了 CI/CD 基础设施——行业正在从多方向汇聚，共同推动**"想法到产品"的全链路自动化**。

---

## 1. 产品版本速览表

| 产品 | 覆盖版本/时间段 | 产品形态 | 关键里程碑 |
|------|----------------|---------|-----------|
| **Cursor** | v0.44（v2.2）~ v0.47 / CLI / Long-Running Agents | IDE 内置代理 + 云端长时代理 | **Long-Running Agents**（52h 自主编码）、Self-Driving Codebase（1000 commits/h）、Subagents、Debug Mode |
| **GitHub Copilot** | VS Code / CLI / Coding Agent / Extensions / **Agentic Workflows** | IDE 插件 + CLI 代理 + CI/CD 自动化 | **Agentic Workflows**（Markdown 定义自动化）、GPT-5.3-Codex GA、Extensions GA、旧模型批量淘汰 |
| **Claude Code** | v2.1.0 ~ v2.1.44 / Agent Teams / Opus 4.6 | CLI 代理 | Agent Teams（16 实例）、8 种 Hooks、Windows ARM64 支持 |
| **Trae** | SOLO Stable / Builder / Coder / v1.3.0 MCP | IDE 内置代理 + 全栈生成器 | MCP 协议支持、多模态上下文 |
| **Google Antigravity** | v1.11 ~ v1.16.5 | 多代理 IDE | Agent Manager、Agent Skills、终端沙箱 |
| **Gemini CLI** | v0.24 ~ v0.28.2 | CLI 代理 | Agent Skills、Hook 系统、**后台 Shell 命令**、子代理进化 |
| **Windsurf** | Wave 13 / Wave 14 / v1.12 ~ v1.9544 | IDE 内置代理 | Arena Mode、SWE-1.5、Cascade Hooks、Tab v2 |
| **Augment Code** | Auggie CLI 0.12.0 / Subagents / Analytics API / **Context Engine MCP** | CLI 代理 + IDE 插件 + MCP 服务 | **Context Engine MCP**（跨代理上下文服务）、CLI Subagents、Analytics API |
| **Codex** | v0.97 ~ CLI v0.101 / GPT-5-Codex → **GPT-5.3-Codex-Spark** | 云端 + CLI + IDE 编码代理 | **GPT-5.3-Codex-Spark**（1000+ tokens/s）、Floating Window、JS REPL、Steer Mode |
| **Bolt** | v2（2025年10月~）/ 持续更新 | 全栈应用生成器 | 多代理架构、Plan Mode、**Opus 4.6 集成** |
| **Lovable** | 持续更新 ~ 2026年2月5日大版本 | 全栈应用生成器 | Plan Mode、Browser Testing、Visual Edits、**Opus 4.6 集成** |
| **Gemini Code Assist** | Agent Mode GA / VS Code 2.68.0 / IntelliJ 1.40.0 | IDE 插件 + Agent Mode | Agent Mode GA、MCP 迁移、180K 免费补全/月 |
| **ChatGPT（Canvas）** | Canvas 更新 / o3 / o4-mini | 对话式编码工作区 | HTML/React 实时渲染、内置代码执行、代码审查 |
| **Claude.ai** | Claude Code on Web / Artifacts MCP / Max 计划 | Web 编码 + 应用生成平台 | 云端并行任务、Artifacts 5亿+ 创建、1M 上下文 |
| **Grok / xAI** | Grok Build（2026年2月） / Grok Code Fast 1 / Grok 4 | CLI + Web 编码代理 | 本地优先架构、92 tokens/s 编码模型、Vibe Coding |
| **Figma** | AI 功能持续更新 / MCP Server | 设计工具 + AI | Figma Make、MCP Server、Vectorize、**AI Credits 改革** |

---

## 2. 功能维度索引

1. [长时自主代理（Long-Running & Autonomous Agents）](#4-长时自主代理-long-running--autonomous-agents) ★ 新增
2. [多代理/子代理架构（Multi-Agent & Subagent）](#5-多代理子代理架构-multi-agent--subagent)
3. [规划模式（Plan Mode）](#6-规划模式-plan-mode)
4. [调试与运行时智能（Debug & Runtime Intelligence）](#7-调试与运行时智能-debug--runtime-intelligence)
5. [CLI 代理（CLI Agents）](#8-cli-代理-cli-agents)
6. [Skills 与可扩展性（Skills, MCP & Extensibility）](#9-skills-与可扩展性-skills-mcp--extensibility)
7. [Hooks 与生命周期控制（Hooks & Lifecycle Control）](#10-hooks-与生命周期控制-hooks--lifecycle-control)
8. [模型更新（Model Updates）](#11-模型更新-model-updates)
9. [企业级功能（Enterprise Features）](#12-企业级功能-enterprise-features)
10. [UI/UX 与交互创新（UI/UX & Interaction Innovation）](#13-uiux-与交互创新-uiux--interaction-innovation)
11. [图像生成与多模态（Image Generation & Multimodal）](#14-图像生成与多模态-image-generation--multimodal)

---

## 3. 时间线总览

```
【前置背景：2025年4月~10月 关键模型与平台发布】
──────────────────────────────────────────────────
Apr 16  OpenAI o3 / o4-mini 发布         Jul 9   Grok 4 发布（xAI）
        ∟ SWE-Bench SOTA / 多工具调用             ∟ 256K 上下文 / CodeLiveBench 71.34%

Jul     Claude Artifacts GA               Aug 28  Grok Code Fast 1 发布（xAI）
        ∟ iOS/Android / 5亿+ 创建                 ∟ 314B MoE / 92 tokens/s / SWE-Bench 70.8%

Oct 14  Gemini Code Assist Agent Mode GA  Oct     Claude Code on Web 发布
        ∟ 自主多步骤编码 / MCP 迁移               ∟ 云端并行任务 / GitHub PR 自动创建

Oct     Claude Artifacts 支持 MCP + 持久化存储
        ∟ 交互式应用生成 + 外部工具连接

ChatGPT Canvas 持续更新
        ∟ HTML/React 渲染 / 代码审查 / 内置执行器

2025年12月                          2026年1月                               2026年2月
────────────────────────────────────────────────────────────────────────────────────────

Dec 5   Gemini Code Assist           Jan 8   Cursor CLI 发布               Feb 3   Bolt 集成 Opus 4.6
        IntelliJ 1.40.0                     Augment CLI Subagents                  Antigravity v1.16.5
        ∟ Outline / Finish Changes
                                                                           Feb 4   Gemini CLI v0.27
Dec 8   Antigravity v1.11.17        Jan 12  Augment 集成 GPT-5.2                  ∟ Plan Mode / Hook 迁移 / /rewind
        ∟ Secure Mode
                                                                           Feb 5   Lovable 大版本
Dec 9   Figma AI Credits 更新      Jan 13  Antigravity v1.14                      ∟ Plan Mode / Browser Testing
                                            ∟ Agent Skills                           Prompt Queue / 环境隔离
Dec 10  Cursor v2.2
        ∟ Debug Mode / Plan Mode    Jan 14  GitHub Copilot CLI             Feb 5   Codex v0.98.0
                                            ∟ 4 专用代理 / GPT-5 mini             ∟ GPT-5.3-Codex / Steer Mode
        Windsurf v1.12.41
        ∟ MCP / Cascade Hooks       Jan 16  Cursor CLI Plan Mode           Feb 5   Claude Opus 4.6 发布
                                                                                   ∟ 1M token / adaptive thinking
Dec 16  Auggie CLI v0.12.0                                                         Copilot / Windsurf / Lovable 同步支持
                                    Jan 20  Gemini CLI v0.25
Dec 17  Antigravity 集成                    ∟ Agent Skills 默认启用        Feb 5   Cursor Self-Driving Codebase
        Gemini 3 Flash                                                             ∟ 研究：1000 commits/h、千级代理编排

                                    Jan 22  Cursor v2.4                    Feb 9   GPT-5.3-Codex GA (Copilot)
Dec 18  Cursor Enterprise                   ∟ Subagents / Skills / Hooks
        ∟ 对话洞察 / 沙箱 / 服务账户                                        Feb 10  Gemini CLI v0.28.0
                                    Jan 23  Antigravity v1.15.6                    ∟ 后台 Shell / 子代理进化 / /prompt-suggest
Dec 22  Cursor v2.3                         ∟ macOS 终端沙箱
        ∟ 四种预设布局                                                      Feb 12  ★ Cursor Long-Running Agents
                                    Jan 23  Gemini Code Assist                     ∟ 研究预览：52h / 151K 行代码
Dec 24  Windsurf Wave 13                    VS Code 2.68.0                         自主规划→执行→交付 PR
        ∟ SWE-1.5 / Side-by-side
                                    Jan 25  Windsurf v1.13.12              Feb 12  GPT-5.3-Codex-Spark (OpenAI)
Dec 27  Windsurf 集成                       ∟ Enterprise 命令控制                  ∟ 1000+ tokens/s / Cerebras 合作
        Gemini 3 Flash                                                             Codex CLI v0.100~v0.101
                                    Jan 27  Cursor Secure Codebase Indexing         ∟ JS REPL / 内存管理 / Floating Window
                                            ∟ Merkle-tree 增量同步
                                                                           Feb 13  Claude Code v2.1.41
                                    Jan 28  Augment Analytics API                  ∟ Windows ARM64 / CLI auth 子命令

                                    Jan 30  Windsurf Wave 14               Feb 13  GitHub Agentic Workflows
                                            ∟ Arena Mode / Plan Mode               ∟ Markdown 定义自动化 / 多 AI 引擎

                                    Jan~Feb Claude Code Agent Teams        Feb 17  Copilot 旧模型批量淘汰
                                            ∟ 16 实例协作                          ∟ Claude 4.1 / Gemini 2.5 Pro / GPT-5

                                    持续    Bolt v2 多代理 / Plan Mode     Feb     Grok Build 发布（xAI）
                                            Figma MCP Server (open beta)           ∟ Vibe Coding / 本地优先 / CLI + Web
                                            Lovable Visual Edits 迭代
                                            Codex v0.97 Session-scoped     Feb     Copilot Extensions GA
                                            ChatGPT Canvas 编码工作区              ∟ Marketplace 上线
                                            Augment Context Engine MCP
                                              ∟ 跨代理上下文服务           Feb     Figma Vectorize + AI Credits 改革
```

---

## 4. 长时自主代理 (Long-Running & Autonomous Agents)

> **行业趋势**：2026 年 2 月最具突破性的新能力——代理从"分钟级辅助"进化为"小时级/天级自主编码"，能独立交付完整功能。

### 功能介绍

**长时自主代理**是指 AI 编码代理能够在**数小时甚至数天内持续自主工作**，完成复杂的多步骤开发任务，而无需人类持续监督。这与传统的"对话式"编码代理形成根本差异——后者每次只能处理一个相对简单的请求，需要人类频繁介入引导。

长时自主代理解决了三个关键问题：
- **复杂任务的完整交付**：重构整个认证系统、从零构建移动应用等需要数十小时的任务，代理可以自主规划并执行到底
- **人类注意力瓶颈**：开发者不再需要全程盯着代理工作，可以分配任务后去做其他事情
- **规模化并行**：多个长时代理可以同时处理不同任务，实现一个人同时推进多个项目

### 样例说明

**场景一：Cursor Long-Running Agents 自主实现移动应用**

```
用户在 cursor.com/agents 提交任务：
"基于现有的 Web 应用实现 React Native 移动端"

Long-Running Agent 执行流程：
1. 分析 Web 应用代码库结构和功能（~1 小时）
2. 生成详细的移动端实施计划 → 等待用户审批
3. 用户审批后，代理自主执行：
   - 搭建 React Native 项目结构（~2 小时）
   - 移植认证模块（~4 小时）
   - 实现核心业务页面（~12 小时）
   - 编写测试和修复 Bug（~8 小时）
   - 适配 iOS 和 Android 差异（~4 小时）
4. 总计 30 小时后，提交完整 Pull Request
   → 多个代理交叉检查代码质量
   → merge rate 与普通代理相当
```

**场景二：Cursor Self-Driving Codebase 千级代理协作**

```
研究实验（一周运行）：
├── 递归层级架构：
│   ├── Planner（规划器）：持续探索代码库、创建任务
│   │   └── Sub-planner（子规划器）：针对特定模块深入规划
│   ├── Worker（执行器）：专注执行分配的任务
│   └── Judge（裁判）：决定每个周期是否继续
├── 运行成果：
│   ├── ~1,000 commits/hour（每小时约 1000 次提交）
│   ├── 1,000 万次工具调用
│   ├── 100 万行代码（1000 个文件）
│   └── 代码"几乎完全可运行，无需人类干预"
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | Long-Running Agents（2026年2月12日） | 长时自主代理（研究预览） | 52 小时 / 151K 行代码、Plan-then-execute、多代理交叉检查 |
| **Cursor** | Self-Driving Codebase（2026年2月5日） | 千级代理自主编码研究 | ~1000 commits/h、递归 Planner-Worker 架构 |
| **Codex** | GPT-5.3-Codex（2026年2月5日） | 独立工作超 7 小时 | 复杂任务投入双倍推理时间 |

### 详细更新

#### Cursor

- **Long-Running Agents**（2026年2月12日，研究预览）：Cursor 推出**长时自主代理**，这是编码代理领域最具里程碑意义的突破之一。代理在接收到复杂任务后，先生成详细的执行计划并等待用户审批，然后自主工作数小时甚至数天。与常规代理不同，长时代理通过**多个代理交叉检查**彼此的工作来保持方向正确，产出的 Pull Request 规模远超常规代理且 merge rate 相当。
  - 代表性案例：重构认证和 RBAC 系统（25 小时）、基于现有 Web 应用实现移动端（30 小时）、构建全新聊天平台（36 小时）、一位用户完成了 **52 小时**的任务并产出 **151K 行代码**
  - 适用对象：Ultra、Teams 和 Enterprise 计划用户，入口为 `cursor.com/agents`
- **Self-Driving Codebase**（2026年2月5日，研究博客）：Cursor 发布自主编码系统研究成果。通过**递归 Planner-Worker 层级架构**协调数千个 AI 代理：Planner 持续探索代码库并创建任务（可生成子 Planner 进行并行深度规划），Worker 专注执行单一任务，Judge 决定每个周期是否继续。在一周的测试运行中实现约 **1000 commits/hour**，跨 **1000 万次工具调用**，产出 **100 万行代码**。该研究为 Long-Running Agents 产品化奠定了技术基础。

#### Codex

- **GPT-5.3-Codex**（2026年2月5日）：在复杂任务上代理可独立工作超过 **7 小时**，在简单任务上实现 93.7% 的 token 节省，在复杂任务上投入两倍推理时间。这种"智能资源分配"使得长时自主执行成为可能。

> **注**：长时自主代理是对传统"对话式"编码代理范式的根本性挑战。当代理能够自主工作 52 小时并交付 15 万行代码时，开发者的角色从"代码编写者"进一步向"任务规划者和代码审查者"转变。这一能力目前仍处于研究预览阶段，产出质量和稳定性有待大规模验证。

---

## 5. 多代理/子代理架构 (Multi-Agent & Subagent)

> **行业趋势**：从单代理到多代理协作，是 2025Q4—2026Q1 最核心的架构演进方向。

### 功能介绍

**多代理架构**是指将一个复杂任务拆分给多个独立的 AI 代理并行处理的系统设计。每个子代理拥有**独立的上下文窗口**、**独立的模型配置**和**专属的工具集**，由一个主代理（或调度器）负责任务分配和结果汇总。

这一架构解决了单一代理的两大瓶颈：
- **上下文窗口限制**：单个代理无法同时理解超大型代码库的所有细节
- **注意力分散**：当任务涉及前端、后端、测试等多个领域时，单个代理容易顾此失彼

### 样例说明

**场景一：Claude Code Agent Teams 构建 C 编译器**

```
Team Lead（主代理）
├── Teammate 1：负责词法分析器（lexer）
├── Teammate 2：负责语法解析器（parser）
├── Teammate 3：负责语义分析（semantic analysis）
├── Teammate 4：负责代码生成（code generation）
└── 共享任务列表：team lead 分配任务，teammates 认领执行，通过任务列表同步进度
```

16 个 Claude 实例通过共享任务列表协作，最终构建了一个 **10 万行的 C 编译器**。

**场景二：Cursor Subagents 处理全栈需求**

用户输入"给应用添加用户认证功能"，主代理自动拆分为：
- 子代理 A：设计数据库 schema 和 API 路由
- 子代理 B：实现前端登录/注册页面
- 子代理 C：编写认证中间件和单元测试

三个子代理并行执行，各自拥有独立上下文，互不干扰。

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | v2.4（2026年1月22日） | Subagents — 独立并行子代理 | 各自拥有独立上下文和模型配置 |
| **Claude Code** | v2.1.32（2026年1月~2月） | Agent Teams — 多代理协作 | team lead + teammates + 共享任务列表 |
| **GitHub Copilot** | CLI（2026年1月14日） | 4 个专用代理 | Explore / Task / Plan / Code-review |
| **Augment Code** | CLI（2026年1月8日） | CLI Subagents | 并行子代理 + 自动上下文共享 |
| **Google Antigravity** | v1.11+（2025年11月~） | Agent Manager | 跨编辑器/终端/浏览器协同 |
| **Trae** | SOLO Stable（2025年11月~） | 多任务并行 | 多代理独立模型与上下文 |
| **Gemini CLI** | v0.28.0（2026年2月10日） | 子代理能力进化 | 通用 Checklist 组件 + 结构化任务管理 |
| **Gemini Code Assist** | Agent Mode GA（2025年10月） | Agent Mode — 自主多步骤编码 | 规划→执行→调试→验证全流程自动化 |
| **Bolt** | v2（2025年10月~） | 多代理架构 | agents-of-agents 架构，Claude Agent 可切换 |

### 详细更新

#### Cursor

- **v2.4**（2026年1月22日）：引入 **Subagents** 机制。每个子代理作为独立的并行执行单元运行，拥有自己的上下文窗口和模型配置。主代理可以将复杂任务拆分给多个子代理同时处理，大幅提升复杂任务的完成速度和质量。

#### Claude Code

- **v2.1.32**（2026年1月~2月）：推出 **Agent Teams** 功能——由一个 team lead 和多个 teammates 组成的多代理协作框架，通过**共享任务列表**进行协调。标杆案例：16 个 Claude 实例协作构建了 10 万行 C 编译器，验证了多代理架构在大规模工程项目中的可行性。
- **v2.1.39~v2.1.44**（2026年2月10日~16日）：持续质量改进。**v2.1.41**（2月13日）新增 **CLI auth 子命令**（`claude auth login/status/logout`）、**Windows ARM64 原生二进制支持**、防止嵌套启动的安全保护。**v2.1.42**（2月13日）优化 **prompt cache 命中率**（将日期移出系统提示）和启动性能（延迟 Zod schema 构建），新增 Opus 4.6 effort 级别引导。**v2.1.44**（2月16日）修复了认证刷新错误。

#### GitHub Copilot CLI

- **CLI**（2026年1月14日）：内置 **4 个专用代理**——**Explore**（代码探索）、**Task**（任务执行）、**Plan**（规划）、**Code-review**（代码审查）。支持自动委派与并行运行，将不同类型的开发任务路由到最合适的专用代理。

#### Augment Code

- **CLI**（2026年1月8日）：推出 **CLI Subagents**，允许从单一 CLI 会话中并行启动多个子代理。子代理之间自动共享上下文，无需手动传递信息。

#### Google Antigravity

- **v1.11+**（2025年11月起）：作为原生多代理 IDE，内置 **Agent Manager**（代理调度中心），在编辑器、终端和浏览器之间进行跨环境协同，是多代理架构的最彻底实现。

#### Trae SOLO

- **Stable 版**（2025年11月起）：支持多任务并行处理，每个任务由独立代理执行，拥有独立的模型选择和上下文空间。

#### Gemini CLI

- **v0.28.0**（2026年2月10日）：子代理能力持续进化——引入通用 **Checklist 组件**用于结构化任务管理，使子代理能够更有效地分解和追踪复杂任务。结合后台 Shell 命令执行能力，子代理可以在不阻塞主流程的情况下并行运行长时间任务。

#### Gemini Code Assist

- **Agent Mode GA**（2025年10月）：Google 的 IDE 编码代理插件推出 **Agent Mode**，在 VS Code、IntelliJ、PyCharm、WebStorm 和 Android Studio 中提供自主多步骤编码能力。Agent Mode 能够自动规划复杂的多文件重构任务、生成完整测试、追踪调用栈调试问题，并迭代验证变更。底层使用 Gemini 2.5 模型系列（免费版 Flash / 企业版 Pro），拥有 **1M token 上下文窗口**，可一次性理解整个代码库。免费版提供 **180K 补全/月**（是 GitHub Copilot 免费版的 90 倍），无需信用卡。

> **注**：Gemini Code Assist Agent Mode 与已覆盖的 Gemini CLI 和 Google Antigravity 属于 Google 编码 AI 生态的不同入口——Agent Mode 面向 IDE 内工作流，Gemini CLI 面向命令行自动化，Antigravity 是原生多代理 IDE。三者共享 Gemini 模型底座但产品形态各异。

#### Bolt

- **v2**（2025年10月起）：引入 **agents-of-agents 架构**，允许用户在不离开编辑器的情况下无缝切换不同 AI 编码代理。以 Claude Agent 为主力，支持在 Haiku（快速编辑）、Sonnet（全栈开发）、Opus（复杂架构）之间按任务类型切换，实现了 **98% 的错误循环减少**和 **1000 倍的项目规模提升**。

---

## 6. 规划模式 (Plan Mode)

> **行业趋势**："先规划再执行"成为行业标配，显著降低代理执行失误率。

### 功能介绍

**Plan Mode** 是指 AI 代理在执行代码修改之前，先生成一份结构化的实施方案供开发者审阅和确认的工作模式。这与传统的"立即执行"模式形成对比——后者收到指令就直接开始写代码，容易在复杂任务上偏离方向。

Plan Mode 的核心价值在于：
- **降低失误率**：代理先理解需求、制定方案、征求反馈，再动手执行
- **提升可控性**：开发者可以在代码变更之前审核计划，避免不必要的大规模重构
- **增强协作性**：计划文档可以作为团队沟通的基础

### 样例说明

**场景：用 Cursor Plan Mode 重构认证模块**

```
用户输入："将 JWT 认证改为 OAuth 2.0"

Plan Mode 输出：
┌─────────────────────────────────────────────┐
│ 重构计划                                      │
│                                               │
│ 1. 安装依赖：passport、passport-oauth2       │
│ 2. 新增文件：                                 │
│    - src/auth/oauth.strategy.ts               │
│    - src/auth/oauth.config.ts                 │
│ 3. 修改文件：                                 │
│    - src/auth/auth.module.ts （替换 JWT 策略） │
│    - src/middleware/auth.guard.ts （更新验证）  │
│ 4. 删除文件：                                 │
│    - src/auth/jwt.strategy.ts                 │
│ 5. 更新测试：5 个测试文件需要适配             │
│                                               │
│ [自动生成的 Mermaid 架构图]                    │
└─────────────────────────────────────────────┘

用户确认 → 代理按计划逐步执行
```

**场景：Lovable Plan Mode 规划全栈应用**

```
用户输入："构建一个带用户认证的任务管理应用"

Plan Mode 输出（保存至 .lovable/plan.md）：
- 技术栈选择：React + Supabase + Tailwind CSS
- 数据库设计：users 表、tasks 表、RLS 策略
- 页面规划：登录页、注册页、任务看板、设置页
- 认证方案：Supabase Auth + 邮箱/密码 + Google OAuth

用户可编辑计划 → 确认后 Lovable 按计划生成完整应用
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | v2.2（2025年12月10日） | Plan Mode | 支持内联 Mermaid 图表自动生成 |
| **Cursor** | CLI（2026年1月16日） | CLI Plan Mode | CLI 中的离线规划模式 |
| **GitHub Copilot** | CLI（2026年1月21日） | 协作规划 | Shift+Tab 触发，代理主动提问澄清需求 |
| **Windsurf** | Wave 14（2026年1月30日） | Plan Mode | 加入 Arena 模式 |
| **Gemini CLI** | v0.27（2026年2月4日） | Plan Mode | Shift+Tab 模式循环扩展 |
| **Lovable** | 2026年2月5日 | Plan Mode | Chat Mode 重命名，计划保存至 `.lovable/plan.md` |
| **Gemini Code Assist** | Agent Mode GA（2025年10月） | Plan-before-execute | Agent Mode 先展示执行计划，用户审批后再执行 |
| **Bolt** | v2 持续 | Plan Mode / Discussion Mode | 代理先规划整个项目再编写代码 |

### 详细更新

#### Cursor

- **v2.2**（2025年12月10日）：首次引入 **Plan Mode**，在执行代码修改前先生成结构化计划。亮点是支持**内联 Mermaid 图表自动生成**，让复杂的架构变更计划可视化展示，开发者可以在确认计划后再进入执行阶段。
- **CLI**（2026年1月16日）：将 Plan Mode 扩展到 CLI 环境，支持离线规划模式，让命令行用户也能享受"先规划后执行"的工作流。

#### GitHub Copilot CLI

- **CLI**（2026年1月21日）：通过 **Shift+Tab** 触发协作规划模式。与其他产品不同的是，Copilot CLI 的规划模式强调**协作性**——代理会主动提问以澄清需求，确保理解正确后再制定执行计划。

#### Windsurf

- **Wave 14**（2026年1月30日）：Plan Mode 加入 **Arena 模式**，允许多个模型同时生成规划方案并进行对比，开发者可以选择最优方案执行。

#### Gemini CLI

- **v0.27**（2026年2月4日）：通过 **Shift+Tab** 扩展模式循环，新增 Plan Mode 作为可选模式之一。与 Copilot CLI 采用了相同的触发方式，体现了交互范式的趋同。

#### Lovable

- **2026年2月5日**：将原有的 Chat Mode 重命名为 **Plan Mode**，强调"先规划后执行"的工作流。用户可以在专用视图中审阅和编辑 AI 生成的实施方案，确认后再执行。方案自动保存至 **`.lovable/plan.md`**，提供跨消息的持久上下文。

#### Gemini Code Assist

- **Agent Mode GA**（2025年10月）：Agent Mode 内置 **plan-before-execute** 工作流——在执行多步骤任务前，代理先生成完整的执行计划（涉及哪些文件、具体修改策略、预期影响），开发者可以审阅并批准计划后再开始执行。这种模式特别适合大型代码重构和跨文件修改场景，降低了 Agent Mode 自动化操作的风险。

#### Bolt

- **v2**（持续）：内置 **Plan Mode** 和 **Discussion Mode**。Plan Mode 让代理先规划整个项目结构和技术方案，用户审核每一步后再开始生成代码。Discussion Mode 则用于纯讨论而不消耗代码生成 token，适合需求澄清阶段。

---

## 7. 调试与运行时智能 (Debug & Runtime Intelligence)

> **行业趋势**：代理从"写代码"向"理解运行时行为"进化。

### 功能介绍

**调试与运行时智能**是指 AI 代理不仅能生成和修改代码，还能**理解代码在运行时的实际行为**。传统 AI 编码工具只关注静态代码——补全、重构、生成。但软件 Bug 大多发生在运行时，需要理解变量状态、执行路径和跨组件交互。

这一能力包含两个层面：
- **运行时诊断**：自动在代码中插入日志/探针，追踪执行路径和变量状态
- **视觉验证**：在真实浏览器环境中测试应用，验证 UI 渲染和用户交互

### 样例说明

**场景一：Cursor Debug Mode 诊断间歇性登录失败**

```
用户输入："登录功能偶尔失败，但没有报错"

Debug Mode 自动执行：
1. 在 auth.service.ts 的 login() 方法中插入运行时日志
2. 追踪 token 生成 → session 存储 → cookie 设置的完整链路
3. 捕获到问题：session 存储在高并发时出现竞态条件
4. 输出诊断报告 + 修复建议
```

**场景二：Lovable Browser Testing 验证用户流程**

```
Lovable 在虚拟浏览器中自动执行：
1. 打开应用首页 → 截取截图
2. 点击"注册"按钮 → 填写表单 → 提交
3. 检查控制台日志和网络请求
4. 验证跳转到仪表盘页面
5. 发现问题：表单提交后 loading 状态未清除 → 自动修复
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | v2.2（2025年12月10日） | Debug Mode | 自动插桩运行时日志，跨语言/框架追踪 |
| **Cursor** | v2.2（2025年12月10日） | Browser Layout & Style Editor | 实时 CSS 编辑与组件树操控 |
| **ChatGPT（Canvas）** | 持续更新 | 代码审查与调试 | 内联代码审查、自动添加调试日志、Bug 自动修复 |
| **Lovable** | 2026年2月5日 | Browser Testing | 虚拟浏览器中端到端测试用户流程 |

### 详细更新

#### Cursor

- **v2.2**（2025年12月10日）：推出 **Debug Mode**，这是编码代理领域的一项重要创新。该模式能够**自动在代码中插入运行时日志**，跨语言和框架追踪变量状态和执行路径。开发者无需手动添加 `console.log` 或设置断点，代理会智能地在关键位置插桩，收集运行时信息，然后基于这些信息诊断问题。
- **v2.2**（2025年12月10日）：同步推出 **Browser Layout & Style Editor**，支持在内置浏览器中实时编辑 CSS 样式和操控组件树，将前端调试体验直接整合到 IDE 环境中。

#### Lovable

- **2026年2月5日**：推出 **Browser Testing** 功能。Lovable 可以在**真实浏览器环境**中与应用交互，像真实用户一样进行端到端测试。支持页面导航、截图捕获、点击 UI 元素、填写表单、读取控制台日志和检查网络请求。这使得 Lovable 能够自主发现并修复 UI 和交互问题。

#### ChatGPT（Canvas）

- **持续更新**：ChatGPT Canvas 提供**内联代码审查**功能——AI 可直接在代码中标注改进建议，而非仅在聊天中回复。同时支持**自动添加调试日志**（为代码关键位置插入 log 语句）、**自动修复 Bug**（分析代码逻辑并修正错误）以及**代码注释生成**。这些能力虽不如 Cursor Debug Mode 的运行时诊断深入，但为 ChatGPT 用户提供了轻量级的代码质量保障工具。底层搭载 o3 / o4-mini 等推理模型，在编码任务上达到 SWE-Bench SOTA 水平。

> **注**：ChatGPT Canvas 的调试能力侧重于**静态代码分析和编辑**（审查、标注、修复），而非 Cursor 和 Lovable 的**运行时诊断**（插桩追踪、浏览器测试），两者定位互补。

---

## 8. CLI 代理 (CLI Agents)

> **行业趋势**：CLI 代理从"辅助终端"进化为"独立开发入口"，支持脚本化、自动化和 CI/CD 集成。

### 功能介绍

**CLI 代理**是在命令行终端中运行的 AI 编码助手，无需打开图形化 IDE 即可完成代码生成、修改、审查等开发任务。CLI 代理的核心优势：

- **脚本化与自动化**：天然适合集成到 CI/CD 流水线、Git hooks 和自动化脚本中
- **轻量级**：无需打开完整 IDE，适合远程服务器、SSH 会话等场景
- **可组合**：可与 Shell 管道、其他命令行工具组合使用

### 样例说明

**场景一：Cursor CLI 在终端中规划重构**

```bash
$ cursor --plan "将 monorepo 拆分为微服务架构"

Plan Mode 输出：
1. 分析当前项目结构（3 个模块、12 个共享依赖）
2. 建议拆分为 4 个独立服务：auth, api, worker, shared
3. 生成迁移计划和依赖关系图
4. 等待确认后执行...

$ cursor --approve    # 确认计划，开始执行
```

**场景二：Copilot CLI 在 CI/CD 中自动审查**

```bash
# 在 GitHub Actions 中使用 Copilot CLI
- name: AI Code Review
  run: |
    copilot-cli --silent --code-review \
      --diff "origin/main...HEAD" \
      --output review.md
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor CLI** | 2026年1月8日~16日 | 模型选择、Rules、MCP、Plan/Ask/Cloud 模式 | 全功能 CLI 代理 |
| **GitHub Copilot CLI** | 2026年1月14日 | WinGet/Homebrew 安装、自动化标志 | GPT-5 mini / GPT-4.1 免费使用 |
| **Gemini CLI** | v0.24~v0.28.2（2025年12月~2026年2月） | Agent Skills、/rewind、后台 Shell、子代理进化 | v0.28 后台命令 + /prompt-suggest |
| **Augment Auggie CLI** | 2025年12月16日 | v0.12.0 — /about 命令、导航优化 | 轻量级更新 |
| **Codex CLI** | v0.97 ~ v0.101（2026年1月~2月） | Steer Mode、JS REPL、内存管理、Floating Window | **GPT-5.3-Codex-Spark**（1000+ tokens/s） |
| **Grok Build** | 2026年2月 | CLI + Web UI 编码代理 | Vibe Coding、本地优先、GitHub 集成 |

### 详细更新

#### Cursor CLI

- **2026年1月8日~16日**：Cursor 正式推出独立 CLI 代理，功能快速迭代。支持**模型选择**（在 CLI 中切换不同 AI 模型）、**Rules 管理**（加载和管理 `.cursor/rules` 配置）、**MCP 服务器管理**（连接外部工具）、以及 **Plan / Ask / Cloud** 三种模式（规划模式、问答模式、云端模式）。这使得 Cursor 从纯 IDE 产品扩展为 IDE + CLI 双入口产品。

#### GitHub Copilot CLI

- **2026年1月14日**：推出独立 CLI 代理，支持 **WinGet** 和 **Homebrew** 安装，降低入门门槛。内置 `--silent` 和 `--share` 等**自动化标志**，方便集成到脚本和 CI/CD 流程中。亮点是 **GPT-5 mini** 和 **GPT-4.1** 对订阅用户**免费使用**，大幅降低使用成本。

#### Gemini CLI

- **v0.24~v0.28**（2025年12月~2026年2月）：持续快速迭代。**v0.24** 引入基础架构；**v0.25**（2026年1月20日）默认启用 **Agent Skills**；**v0.26**（2026年1月27日）新增 `skill-creator` 和 `pr-creator` 技能；**v0.27**（2026年2月4日）引入 `/rewind` 命令（回退到之前状态）、**code-reviewer** 内置技能、以及**事件驱动调度器**；**v0.28.0**（2026年2月10日）新增**后台 Shell 命令**（长时间命令可在后台执行而不阻塞主流程）、**`/prompt-suggest` 命令**（AI 自动生成提示建议）、**Positron IDE 支持**、以及通用 **Checklist 组件**用于结构化任务管理。子代理能力持续进化，将 CLI 从简单的命令行工具升级为可编排的自动化平台。

#### Augment Auggie CLI

- **v0.12.0**（2025年12月16日）：轻量级更新，新增 `/about` 命令显示环境信息，优化导航体验。

#### Codex CLI

- **v0.97~v0.101**（2026年1月~2月）：OpenAI Codex CLI 是其**多界面统一产品**的核心入口之一，与 IDE 扩展、Web 端、GitHub 集成和 ChatGPT App 共享同一账户和上下文。**v0.97** 引入 **Session-scoped Approvals**（会话级工具授权——对 MCP 工具调用选择"允许并记住"后，同一会话内自动放行）和 **Live Skill Updates**（技能文件修改后无需重启即可生效）。**v0.98**（2026年2月5日）稳定了 **Steer Mode**（实时引导模式），默认启用，允许在代理执行任务过程中实时发送指令引导方向。底层模型同步升级至 **GPT-5.3-Codex**。**v0.100**（2026年2月12日）引入多项重大更新：**实验性 JavaScript REPL 运行时**（带状态持久化）、**多层速率限制**、**内存管理斜杠命令**（`/m_update`、`/m_drop`）和 **Apps SDK 支持**。**v0.101**（2026年2月12日）优化了内存阶段处理的并发稳定性。底层新增 **GPT-5.3-Codex-Spark** 模型（超过 1000 tokens/s 的实时编码模型）。

#### Grok Build（xAI）

- **2026年2月**：xAI 推出 **Grok Build**，这是 xAI 首款独立编码代理产品。核心理念是 **Vibe Coding**——开发者用自然语言描述软件构想，代理自主处理规划、代码生成和执行。采用 **CLI 优先 + Web UI** 双入口架构：通过 npm 安装 CLI 工具，同时提供 Web 界面通过 WebSocket 同步状态。最大差异化特征是**本地优先架构**——所有代码在用户本地机器上执行，无需上传到云端，满足对数据隐私敏感的企业和开发者需求。支持原生 **GitHub 集成**（仓库、分支、PR 管理）和细粒度的文件访问/脚本执行权限控制。底层使用 Grok 4 和 Grok Code Fast 1 模型。

> **注**：Grok Build 于 2026 年 2 月发布，部分功能（如远程编码代理）计划后续推出，当前以本地 CLI + Web UI 为主要交互形态。

> **注**：Bolt 和 Lovable 作为全栈应用生成器，采用浏览器端而非 CLI 作为交互入口，因此不在本维度覆盖范围内。

---

## 9. Skills 与可扩展性 (Skills, MCP & Extensibility)

> **行业趋势**：从 Prompt Engineering 到 Flow Engineering——Skills 将经验沉淀为可复用流程，MCP 成为工具连接标准。

### 功能介绍

这一维度涵盖三种互补的可扩展机制：

- **Skills（SKILL.md / AGENTS.md）**：将领域知识、编码规范和工作流程编码为可复用的 Markdown 文件。代理在执行任务时自动加载相关技能，按照团队特定的方式工作。Codex 使用 AGENTS.md 实现类似功能，支持层级化的指令范围。
- **MCP（Model Context Protocol）**：连接 AI 代理与外部工具（数据库、API、设计工具等）的标准协议。一个 MCP Server 可以被多个 AI 工具共享。
- **Extensions / 集成**：第三方开发者构建的插件和扩展，通过 Marketplace 分发。

简而言之：**Skills 教代理"怎么做"，MCP 让代理"能做什么"，Extensions 让社区贡献"新能力"**。

### 样例说明

**场景一：Cursor SKILL.md 定义代码审查流程**

```markdown
# SKILL.md — 代码审查技能
## 触发条件
当用户要求"审查代码"或"review PR"时自动加载

## 执行步骤
1. 检查代码风格是否符合团队 .eslintrc 配置
2. 验证所有公开 API 是否有 JSDoc 注释
3. 检查是否有未处理的错误（try-catch）
4. 生成审查报告（Markdown 格式）
```

**场景二：Figma MCP Server 连接设计与编码**

```
开发者在 Cursor 中粘贴 Figma 设计链接：
  → Figma MCP Server 提取设计元数据（布局、颜色、组件、变量）
  → Cursor 代理基于结构化设计数据生成 React 组件
  → 生成的代码精确匹配 Figma 设计稿的间距、颜色和字体
```

**场景三：Bolt System Prompt 定制**

```
在 Bolt 项目设置中配置系统提示：
  "始终使用 Tailwind CSS + shadcn/ui 组件库，
   数据库使用 Supabase，认证使用 Supabase Auth，
   路由使用 React Router v6。"
  → 后续所有代码生成自动遵循这些技术栈偏好
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | v2.4（2026年1月22日） | Skills（SKILL.md） | 动态发现、按需加载 |
| **Claude Code** | v2.1（2026年1月） | SKILL.md 支持 | 热重载、`context: fork` 隔离执行 |
| **Gemini CLI** | v0.25~v0.26（2026年1月20日~27日） | Agent Skills | skill-creator / pr-creator 技能 |
| **Google Antigravity** | v1.14（2026年1月13日） | Agent Skills | Skills 系统引入 |
| **Trae** | v1.3.0 | MCP 协议支持 | stdio + SSE 双协议 |
| **Windsurf** | v1.12.41（2025年12月10日） | MCP Server + Cascade Hooks | 扩展支持 |
| **GitHub Copilot** | Extensions（2026年2月） | Extensions GA | Perplexity / Docker / Mermaid 等 |
| **Figma** | MCP Server（open beta） | Figma MCP Server | 设计数据直连 AI 编码工具 |
| **Codex** | v0.97~v0.98（2026年1月~2月） | AGENTS.md + MCP + Live Skills | 层级化指令 + 会话级工具授权 |
| **Bolt** | 持续 | System Prompt 定制 | 项目级/全局系统提示 + 集成生态 |
| **GitHub Copilot** | Agentic Workflows（2026年2月13日） | GitHub Agentic Workflows（技术预览） | Markdown 定义自动化、多 AI 引擎支持、深度 GitHub 集成 |
| **Augment Code** | Context Engine MCP（2026年2月） | 跨代理上下文服务 | +80% 质量提升（Claude Code）、+71%（Cursor）、任意 MCP 代理可用 |
| **Gemini Code Assist** | Agent Mode GA（2025年10月） | MCP 协议迁移 | Tool Calling API → MCP，2026年3月前完成迁移 |
| **Claude.ai（Artifacts）** | 2025年10月 | Artifacts MCP + 持久化存储 | Artifacts 连接外部工具、数据持久化 |
| **Lovable** | 持续 | Figma 集成 + Supabase | Builder.io 插件实现 Figma→Lovable |

### 详细更新

#### Cursor

- **v2.4**（2026年1月22日）：引入 **Skills** 系统（基于 SKILL.md 文件）。Skills 支持**动态发现**（代理自动扫描工作区中的 SKILL.md 文件）和**按需加载**（仅在相关任务触发时加载对应技能）。这使得领域知识和工作流定义可以像代码一样版本化管理和团队共享。

#### Claude Code

- **v2.1**（2026年1月）：支持 **SKILL.md** 格式，与 Cursor 的 Skills 生态互通。亮点包括**热重载**（修改 SKILL.md 后无需重启即可生效）和 **`context: fork` 隔离执行**（技能在独立上下文中运行，避免污染主会话）。

#### Gemini CLI

- **v0.25**（2026年1月20日）：**Agent Skills** 默认启用，成为 CLI 的核心能力。
- **v0.26**（2026年1月27日）：新增 **skill-creator**（创建新技能的技能）和 **pr-creator**（自动创建 Pull Request 的技能），展示了 Skills 的可组合性——技能可以创建新技能。

#### Google Antigravity

- **v1.14**（2026年1月13日）：引入 **Agent Skills** 系统，使多代理 IDE 中的每个代理都能拥有专业化的技能配置。

#### Trae

- **v1.3.0**：正式支持 **MCP 协议**，同时支持 **stdio**（标准输入输出）和 **SSE**（Server-Sent Events）两种传输方式。同时引入 `.rules` 配置文件系统，允许项目级别的代理行为定制。

#### Windsurf

- **v1.12.41**（2025年12月10日）：新增 **MCP Server** 扩展支持和 **Cascade Hooks**，将 Windsurf 的代理系统（Cascade）开放给外部工具和自定义逻辑。

#### GitHub Copilot Extensions

- **2026年2月**：**Extensions** 正式 GA（General Availability），**Marketplace** 上线 **Perplexity**（搜索）、**Docker**（容器管理）、**Mermaid**（图表生成）等第三方扩展。这标志着 GitHub Copilot 从封闭生态走向开放平台。

#### GitHub Agentic Workflows

- **2026年2月13日**（技术预览）：GitHub 推出 **Agentic Workflows**——一种全新的自动化范式，用**纯 Markdown** 代替复杂的 YAML 来定义 GitHub Actions 自动化工作流。开发者只需描述自动化目标，`gh aw` CLI 工具会将其转换为标准 GitHub Actions 工作流。
  - **多 AI 引擎支持**：同一工作流格式可使用 GitHub Copilot CLI（默认）、Claude（Anthropic）或 OpenAI Codex 作为执行引擎
  - **深度 GitHub 集成**：通过 GitHub MCP Server 原生访问仓库、Issue、PR、Actions 和安全信息，支持浏览器自动化和网页搜索
  - **安全第一**：默认只读权限、沙箱执行、网络隔离、SHA 固定依赖、输出净化
  - **典型场景**：CI 失败自动排查修复、Issue 自动分类和标注、测试覆盖率提升、文档更新、代码简化
  - 开源（MIT 协议），入口为 `.github/workflows/` 目录中的 Markdown 文件

> **注**：GitHub Agentic Workflows 将 AI 代理能力嵌入 CI/CD 基础设施，是"编码代理进入 DevOps 流水线"的标志性事件。与 Cursor Long-Running Agents（面向开发阶段）互补——前者自动化 CI/CD 和仓库维护，后者自动化代码编写。

#### Augment Code（Context Engine MCP）

- **2026年2月**：Augment Code 推出 **Context Engine MCP**——将其代码理解引擎开放为 **MCP Server**，供**任何 MCP 兼容的 AI 编码代理**使用（包括 Claude Code、Cursor、Zed、GitHub Copilot、OpenAI Codex 等）。支持**远程模式**（连接 Augment 托管 MCP，跨仓库上下文）和**本地模式**（通过 Auggie CLI 本地运行，实时索引工作目录），设置仅需约 2 分钟。
  - 在 300 个 Elasticsearch PR 基准测试中表现显著：Claude Code + Opus 4.6 质量提升 **+80%**，Cursor + Opus 4.6 提升 **+71%**（完整度提升 60%、正确性提升 5 倍），代理完成任务速度提升 **2x**
  - 2026 年 2 月每位 Augment 用户获赠 **1000 次免费请求**，之后每次查询消耗 40-70 credits

> **注**：Augment Context Engine MCP 是首个将"代码库理解能力"作为独立服务开放给竞品工具的案例，体现了 MCP 生态的开放性——即使是竞争对手的产品也可以从中受益。

#### Figma

- **MCP Server**（open beta，2025年6月发布，持续更新）：推出官方 **Figma MCP Server**，将设计数据直接连接到 AI 编码工具（Cursor、Windsurf 等）。提供两种连接方式——**远程 MCP 服务器**（`mcp.figma.com/mcp`）和**桌面本地服务器**（`127.0.0.1:3845/mcp`）。支持从 Figma 帧生成代码、提取设计变量和组件数据、与 Code Connect 集成复用代码库组件。

#### Codex

- **v0.97**（2026年1月~2月）：引入 **Session-scoped Approvals**——对 MCP 和 App 工具调用选择"Allow and remember"后，同一会话内自动放行重复调用，大幅减少人工确认频次。同步推出 **Live Skill Updates**——AGENTS.md 等技能文件修改后无需重启即自动生效。
- **AGENTS.md**（持续）：Codex 的自定义指令系统，类似于 Cursor 的 SKILL.md。支持**层级化指令范围**——根目录的 AGENTS.md 提供全局指令，子目录的 AGENTS.md 提供局部覆盖，实现模块级别的差异化代理行为。

#### Bolt

- **持续**：引入**项目级和全局 System Prompt 定制**功能，让用户指定偏好的库和技术栈。同时通过内置集成生态（Figma via Anima、Supabase、GitHub、Netlify、Stripe）实现开箱即用的全栈开发能力。

#### Gemini Code Assist

- **Agent Mode GA**（2025年10月）：完成从 **Tool Calling API 到 MCP 协议的迁移**。Gemini Code Assist 原先使用 Google 自研的 Tool Calling API 连接外部工具，2025年10月正式切换至行业标准 **MCP（Model Context Protocol）**，现有 Tool Calling API 集成须在 **2026年3月前**迁移完毕。这一变更使 Gemini Code Assist 能够复用 MCP 生态中已有的 Server（如 Figma MCP、Sentry MCP、GitHub MCP 等），大幅扩展了工具集成能力。

#### Claude.ai（Artifacts）

- **2025年10月**：**Claude Artifacts** 新增 **MCP 支持**和**持久化存储**。MCP 集成使 Artifacts 生成的交互式应用能够连接外部数据源和服务（如数据库查询、API 调用），持久化存储则让 Artifacts 中的用户数据跨会话保留。这将 Artifacts 从"一次性代码片段"升级为"可持续迭代的交互式应用平台"。结合 Artifacts 已累计超过 **5 亿次创建**的用户基础，MCP 的引入标志着 Claude.ai 从对话助手向可扩展的应用构建平台演进。

#### Lovable

- **持续**：通过 **Builder.io 插件**实现 **Figma to Lovable 集成**——在 Figma 中选择设计帧，点击"Open in Lovable"即可生成完整应用。同时深度集成 Supabase（数据库 + RLS 权限管理）、Resend（邮件）、Replicate（AI 模型）、OpenAI Realtime API 等服务。

---

## 10. Hooks 与生命周期控制 (Hooks & Lifecycle Control)

> **行业趋势**：代理不再是黑盒——开发者可在代理执行的关键节点注入自定义逻辑。

### 功能介绍

**Hooks** 是代理执行流程中的可编程拦截点。开发者可以在代理调用工具（如读写文件、执行命令）之前或之后插入自定义脚本，实现安全防护、质量检查和流程定制。

Hooks 的核心价值：
- **安全合规**：阻止代理执行危险操作（如删除生产数据库）
- **质量保证**：在代码写入后自动运行 linter 和测试
- **审计追踪**：记录代理的每一次工具调用，满足合规要求

### 样例说明

**场景一：Claude Code PreToolUse Hook 阻止危险操作**

```json
{
  "hook": "PreToolUse",
  "tool": "bash",
  "condition": "command contains 'rm -rf' or 'DROP TABLE'",
  "action": "block",
  "message": "已阻止危险命令。请确认是否真的需要删除操作。"
}
```

**场景二：PostToolUse Hook 自动运行测试**

```json
{
  "hook": "PostToolUse",
  "tool": "file_write",
  "condition": "file matches 'src/**/*.ts'",
  "action": "run",
  "command": "npm test -- --related ${file}"
}
```

当代理修改任何 TypeScript 源文件后，Hook 自动运行该文件的关联测试，确保修改不会引入回归。

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | v2.4（2026年1月22日） | Hooks 性能优化 | 性能提升 **40x** |
| **Claude Code** | v2.1 | 8 种 Hook 类型 | PreToolUse / PostToolUse / PermissionRequest 等 |
| **Windsurf** | v1.12.41（2025年12月10日） | Cascade Hooks | 首批支持 Hooks 的 IDE 代理之一 |
| **Gemini CLI** | v0.27（2026年2月4日） | Hook 系统迁移 | beforeTool/afterTool → hookSystem |

### 详细更新

#### Cursor

- **v2.4**（2026年1月22日）：Hooks 系统获得 **40 倍性能提升**。这一优化使得在每次工具调用时执行 Hook 脚本的开销几乎可以忽略不计，让开发者可以放心地添加多个 Hook 而不影响代理的响应速度。

#### Claude Code

- **v2.1**：实现了目前最完整的 Hook 体系，提供 **8 种 Hook 类型**：
  - `PreToolUse`：工具调用前触发
  - `PostToolUse`：工具调用后触发
  - `PermissionRequest`：权限请求时触发
  - 以及其他 5 种生命周期事件的 Hook

  这使得开发者可以对代理行为进行精细化的控制和审计。

#### Windsurf

- **v1.12.41**（2025年12月10日）：引入 **Cascade Hooks**，是首批支持 Hooks 机制的 IDE 内置代理之一。开发者可以在 Cascade（Windsurf 的代理系统）的执行流程中注入自定义逻辑。

#### Gemini CLI

- **v0.27**（2026年2月4日）：完成 **Hook 系统架构迁移**，从早期的 `beforeTool`/`afterTool` 简单回调升级为统一的 `hookSystem` 架构，支持更灵活的事件订阅和处理。

> **注**：Bolt、Lovable 和 Figma 目前未提供开发者可编程的 Hook 机制，这是 IDE 代理/CLI 代理与全栈生成器的功能差异之一。

---

## 11. 模型更新 (Model Updates)

> **行业趋势**：多模型并存成为常态，各产品竞相集成最新模型以保持竞争力。

### 功能介绍

**模型更新**指编码代理集成的底层大语言模型的升级和新增。模型决定了代理的"智力上限"——推理能力、上下文窗口、代码生成质量等。

当前行业呈现两个关键趋势：
- **多模型可切换**：用户可以根据任务复杂度选择不同模型（如简单编辑用快速模型，复杂架构用强模型）
- **模型即基础设施**：模型不再是差异化因素，所有产品都在快速集成最新模型，真正的差异化来自代理架构和开发体验

### 样例说明

**场景：Bolt 按任务类型切换模型**

```
任务 1："修改按钮颜色"
  → 自动选择 Claude Haiku（快速、低成本）
  → 0.5 秒完成

任务 2："实现完整的支付集成"
  → 用户切换至 Claude Opus（强推理能力）
  → 生成 Stripe 集成代码 + 错误处理 + webhook 回调

任务 3："重构数据库架构"
  → 保持 Claude Opus（复杂架构决策）
  → 生成迁移脚本 + 更新所有关联 API

三种模型在同一订阅内免费切换，无额外费用。
```

### 更新总览

| 模型 | 集成产品 | 日期 | 亮点 |
|------|---------|------|------|
| **Claude Opus 4.6** | Claude Code / Claude.ai / Windsurf / **Copilot / Bolt / Lovable** | 2026年2月5日 | **1M token** 上下文（beta）、adaptive thinking、fast mode |
| **GPT-5.3-Codex** | Codex / **GitHub Copilot** | 2026年2月5日 / 2月9日 GA | 编码专用模型，比 GPT-5-Codex 快 **25%** |
| ★ **GPT-5.3-Codex-Spark** | Codex | 2026年2月12日 | **1000+ tokens/s**（15x 提速）、Cerebras 合作、128K 上下文 |
| **o3** | ChatGPT | 2025年4月16日 | SWE-Bench / Codeforces **SOTA**，多工具 agentic 调用 |
| **o4-mini** | ChatGPT | 2025年4月16日 | 编码+数学优化小模型，**128K** 上下文 |
| **GPT-5.2** | Augment Code / Windsurf | 2026年1月12日 / 2025年12月11日 | 最新推理模型 |
| **GPT-5 mini / GPT-4.1** | GitHub Copilot CLI | 2026年1月14日 | 订阅内免费 |
| **Gemini 2.5 Pro** | Gemini Code Assist（企业版） | 持续 | **1M** 上下文、SWE-Bench 63.8%、Deep Think 模式 |
| **Gemini 2.5 Flash** | Gemini Code Assist（免费版） | 持续 | **1M** 上下文、速度优化、首个具备思考能力的 Flash 模型 |
| **Gemini 3 Pro** | Antigravity / Gemini CLI | 持续 | Google 原生集成 |
| **Gemini 3 Flash** | Windsurf / Antigravity | 2025年12月27日 / 2025年12月17日 | 快速推理模型 |
| **Grok 4** | Grok Build / xAI API | 2025年7月9日 | **256K** 上下文、CodeLiveBench 71.34%、实时 X 平台数据 |
| **Grok Code Fast 1** | Grok Build / xAI API | 2025年8月28日 | **314B** MoE、**92 tokens/s**、SWE-Bench 70.8% |
| **SWE-1.5** | Windsurf Wave 13 | 2025年12月24日 | Windsurf 自研免费模型 |
| **Claude Haiku/Sonnet/Opus** | Bolt | v2 持续 | 三模型按任务切换，单一订阅 |
| **DeepSeek 等** | Trae | 持续 | 多模型可选（Claude-3.5-Sonnet、GPT-4o 等） |
| ★ **旧模型批量淘汰** | GitHub Copilot | 2026年2月17日 | Claude Opus 4.1、Gemini 2.5 Pro、GPT-5、GPT-5-Codex 同日下线 |

### 详细更新

#### Claude Opus 4.6

- **2026年2月5日**：Anthropic 发布 **Claude Opus 4.6**，最大亮点是 **1M token 上下文窗口**（beta 阶段），相比 Opus 4.5 的 200K 上下文实现 **5 倍扩展**，可一次性处理约 75 万字、1500 页文本或 3 万行代码。Claude Code（CLI 和 Web）以及 Windsurf 同步支持。同时引入多项新能力：
  - **Adaptive thinking**：模型根据任务复杂度自动调整推理深度
  - **Compaction API**（beta）：服务端上下文压缩，降低长会话的 token 消耗
  - **Fast mode**（research preview）：输出速度最高提升 **2.5 倍**
  - **数据驻留控制**：支持仅在美国推理
  - 1M 上下文窗口同时对 **Sonnet 4.5** 和 **Sonnet 4** 开放（beta）
  - 在 Terminal-Bench 2.0（代理编码）上达到最高分，在 GDPval-AA（经济价值知识工作）上超越 GPT-5.2 约 **144 Elo**
  - **广泛集成**：发布后一周内被 **GitHub Copilot**（2月5日 GA）、**Windsurf**（2月4日，含 fast mode 促销）、**Bolt**（2月3日，含免费限时体验）、**Lovable**（2月5日）同步集成，成为编码代理领域覆盖面最广的模型之一

#### GPT-5.3-Codex

- **2026年2月5日**：OpenAI 发布 **GPT-5.3-Codex**，融合 Codex 和 GPT-5 训练栈，是目前最强的编码专用模型。比 GPT-5-Codex 快约 **25%**，从"代码生成器"转型为"通用编码代理"——用户可以在模型执行任务的过程中通过 Steer Mode 实时引导方向。在简单任务上实现 **93.7% 的 token 用量减少**，在复杂任务上则投入两倍推理时间，可独立工作超过 **7 小时**处理大型项目。基准成绩：SWE-Bench Pro **56.8%**、OSWorld-Verified **64.7%**、Terminal-Bench 2.0 **77.3%**。
- **2026年2月9日**：**GPT-5.3-Codex 在 GitHub Copilot 中 GA**，面向 Copilot Pro、Pro+、Business 和 Enterprise 用户开放，可在 VS Code、GitHub CLI、GitHub Mobile 等平台使用。

#### GPT-5.3-Codex-Spark

- **2026年2月12日**（研究预览）：OpenAI 发布 **GPT-5.3-Codex-Spark**——一款超快速实时编码模型，是 OpenAI 与 **Cerebras**（专用 AI 芯片公司）合作的首个成果。核心指标：
  - **1000+ tokens/s** 生成速度，比标准 GPT-5.3-Codex 快约 **15 倍**
  - **128K token 上下文**，纯文本
  - 针对**交互式编辑**场景优化——快速做出定向修改并即时看到结果
  - 在 SWE-Bench Pro 和 Terminal-Bench 2.0 上保持强性能的同时大幅缩短完成时间
  - 研究预览阶段面向 ChatGPT Pro 用户开放，可在 Codex App、CLI 和 VS Code 中使用

> **注**：GPT-5.3-Codex-Spark 与 Grok Code Fast 1（92 tokens/s）的出现表明，"极速编码模型"正成为一条独立的模型赛道——不追求最强推理能力，而是优化实时交互的速度和延迟。Cerebras 的定制硬件合作模式可能引领"模型+芯片"深度绑定的趋势。

#### GPT-5.2

- **Augment Code**（2026年1月12日）和 **Windsurf**（2025年12月11日）先后集成 GPT-5.2，获得 OpenAI 最新推理能力。

#### GPT-5 mini / GPT-4.1

- **GitHub Copilot CLI**（2026年1月14日）：将 GPT-5 mini 和 GPT-4.1 纳入订阅计划内**免费使用**，大幅降低高质量模型的使用门槛。

#### Gemini 3 系列

- **Gemini 3 Pro**：作为 Google 自家模型，在 **Antigravity** 和 **Gemini CLI** 中原生集成。
- **Gemini 3 Flash**：**Windsurf**（2025年12月27日）和 **Antigravity**（2025年12月17日）先后集成，作为快速推理的轻量级选择。

#### SWE-1.5

- **Windsurf Wave 13**（2025年12月24日）：推出自研模型 **SWE-1.5**，面向所有用户**免费提供**，是首个由 IDE 厂商自主研发并免费分发的编码专用模型。

#### Bolt 多模型策略

- **v2**（持续）：支持 Claude 4.5 系列三个模型的**任务内切换**——**Haiku**（快速编辑和原型）、**Sonnet**（全栈开发平衡之选）、**Opus**（复杂架构和高级功能）。用户可以在项目中途切换模型而不丢失上下文，所有模型包含在单一订阅中无额外费用。

#### OpenAI o3 / o4-mini

- **2025年4月16日**：OpenAI 发布 **o3** 和 **o4-mini** 两款推理模型，为 ChatGPT 和 Codex 生态提供强大的编码推理底座。
  - **o3** 是 OpenAI 最强推理模型，在 **Codeforces** 和 **SWE-Bench** 上创下新 SOTA，在高难度现实编程任务上比 o1 减少 **20%** 重大错误。支持多工具 agentic 调用（Python 代码执行器、网页搜索、文件分析、图像生成），能在一分钟内解决复杂多面问题。
  - **o4-mini** 是编码+数学优化的高效小模型，支持 **128K token 上下文**，在 AIME 2025 上结合代码执行器达到 **99.5% pass@1**，编程和定量任务表现全面超越 o3-mini。同样支持全工具访问。
  - 两款模型均通过 ChatGPT（含 Canvas）向 Plus/Pro/Team/Enterprise 用户开放，也可通过 API 集成到 Codex 等产品中。

#### Gemini 2.5 系列

- **持续**：Google 的 **Gemini 2.5** 系列为 Gemini Code Assist、Gemini CLI 和 Antigravity 提供模型底座，是当前编码 AI 领域上下文窗口最大的模型之一。
  - **Gemini 2.5 Pro**：面向企业版 Gemini Code Assist，拥有 **1M token 上下文窗口**（计划扩展至 2M），在 SWE-Bench Verified 上达到 **63.8%**、Aider Polyglot 达到 **82.2%**。具备 **Deep Think 模式**（复杂算法和数学编码的深度推理）和代码执行能力（自主 agentic 任务）。原生多模态支持文本、代码、图像、音频和视频输入，支持**视频转代码**工作流。
  - **Gemini 2.5 Flash**：面向免费版 Gemini Code Assist，同样拥有 **1M token 上下文**，针对速度和延迟优化。是首个具备思考能力的 Flash 模型，在代码理解和实时生成场景中表现出色。

#### Grok 模型系列（xAI）

- **Grok 4**（2025年7月9日）：xAI 的通用旗舰模型，**256K token 上下文窗口**。编码基准表现：CodeLiveBench **71.34%**、HumanEval **87.8%**，代码质量达到 98.5% 语法正确性和 94.2% 逻辑准确性。独特优势是集成**实时 X 平台数据**访问，可在编码过程中获取最新技术讨论和文档。
- **Grok Code Fast 1**（2025年8月28日）：xAI 的编码专用模型，采用 **314B 参数 MoE 架构**（从头训练，非蒸馏），在编码数据和真实 PR 上预训练。核心指标：**92 tokens/s** 生成速度（发布时最快的编码模型之一）、**256K token 上下文**、SWE-Bench Verified **70.8%**。定价极具竞争力：输入 $0.20/M tokens、输出 $1.50/M tokens。精通 TypeScript、Python、Java、Rust、C++、Go，支持函数调用、结构化输出和推理追踪。

#### GitHub Copilot 旧模型批量淘汰

- **2026年2月17日**：GitHub 在同一天下线四款旧模型——**Claude Opus 4.1**（建议迁移至 Opus 4.5）、**Gemini 2.5 Pro**（建议迁移至 Gemini 3 Pro）、**GPT-5**（建议迁移至 GPT-5.2）、**GPT-5-Codex**（建议迁移至 GPT-5.1-Codex）。影响范围涵盖 Copilot Chat、内联编辑、Ask 和 Agent 模式以及代码补全。企业和团队管理员需在模型策略设置中启用替代模型的访问权限。

> **注**：这是编码代理领域首次出现如此大规模的**跨厂商同步淘汰**，标志着模型迭代周期在显著缩短——一个模型从"旗舰"到"淘汰"仅需 6-12 个月。这也意味着依赖特定模型的工具和工作流需要具备**模型无关性**，能够快速切换到新模型。

#### 多模型策略

- **Trae**：持续支持多模型可选策略，包括 Claude-3.5-Sonnet、GPT-4o、DeepSeek 等，让用户根据任务特性选择最合适的模型。

---

## 12. 企业级功能 (Enterprise Features)

> **行业趋势**：编码代理从个人工具向企业基础设施演进，需要审计、计费、安全沙箱等能力。

### 功能介绍

**企业级功能**是指满足大型组织规模化部署 AI 编码工具时所需的安全、治理和运维能力。个人开发者使用 AI 工具主要关注效率，而企业还需要回答：

- **安全**：代理会不会泄露敏感代码？能否限制代理的操作范围？
- **成本**：团队的 AI 使用费用如何分摊和控制？
- **合规**：代理的操作是否可审计？是否满足行业法规要求？
- **隔离**：开发环境和生产环境是否严格分离？

### 样例说明

**场景一：Cursor Enterprise 管理员视角**

```
管理员仪表盘：
├── 对话洞察：本周团队共发起 2,340 次 AI 对话
│   ├── 最常见任务：代码审查 (35%)、Bug 修复 (28%)、新功能 (22%)
│   └── 平均每人每周节省 4.2 小时
├── 计费分组：
│   ├── 前端团队：$1,200/月（15人）
│   ├── 后端团队：$980/月（12人）
│   └── DevOps 团队：$450/月（5人）
└── 安全策略：
    ├── Linux 沙箱：所有代理操作在隔离容器中执行
    └── 服务账户：CI/CD 流水线使用独立身份
```

**场景二：Lovable Test/Live 环境隔离**

```
开发流程：
1. Test 环境：AI 代理自由修改代码和数据库
   → 独立的 Supabase 实例，数据可随时重置
2. 验收通过后，一键推送至 Live 环境
   → 生产数据库不受开发影响
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | Enterprise（2025年12月18日） | 对话洞察、计费分组、Linux 沙箱、服务账户 | 全套企业治理 |
| **Cursor** | 2026年1月27日 | Secure Codebase Indexing | Merkle-tree 增量同步、队友索引复用 |
| **Augment Code** | 2026年1月28日 | Analytics API | 企业级使用数据 API |
| **Windsurf** | v1.13.12（2026年1月25日） | Enterprise 命令控制 | 自动执行权限管理 |
| **Google Antigravity** | v1.11.17（2025年12月8日） | Secure Mode | 后改名 Strict Mode |
| **Google Antigravity** | v1.15.6（2026年1月23日） | macOS 终端沙箱 | 沙箱隔离执行 |
| **Lovable** | 2026年2月5日 | Test / Live 环境隔离 | 独立数据库的开发/生产环境分离（Beta） |
| **Codex** | 持续 | ChatGPT Enterprise 计划 + 云端沙箱 | 企业级账户管理 + 隔离执行环境 |
| **Grok Build** | 2026年2月 | 本地优先 + 空气隔离 | 代码不离开本地、细粒度权限、域名限制 |
| **Gemini Code Assist** | 持续 | Enterprise 版 + 组织级管控 | Google Cloud IAM 集成、审计日志 |

### 详细更新

#### Cursor

- **Enterprise**（2025年12月18日）：推出企业版功能套件，包括：
  - **对话洞察分析**：管理员可查看团队的 AI 使用模式和效率数据
  - **计费分组**：按团队/项目分别计费
  - **Linux 沙箱**：在隔离环境中运行代理操作
  - **服务账户**：用于 CI/CD 集成的非人类账户
- **2026年1月27日**：推出 **Secure Codebase Indexing**（安全代码库索引），采用 **Merkle-tree** 数据结构实现增量同步，同时支持**队友索引复用**——团队成员可以共享代码索引，避免重复构建。

#### Augment Code

- **2026年1月28日**：发布 **Analytics API**，提供企业级使用数据接口。企业客户可以通过 API 查询团队的代理使用频率、任务完成率、模型偏好等数据，用于成本优化和效率分析。

#### Windsurf

- **v1.13.12**（2026年1月25日）：新增 **Enterprise 命令自动执行控制**，管理员可以设置代理在执行特定命令（如 `rm`、`git push`）时必须获得人工确认，防止误操作。

#### Google Antigravity

- **v1.11.17**（2025年12月8日）：引入 **Secure Mode**（后更名为 **Strict Mode**），限制代理的文件系统和网络访问权限。
- **v1.15.6**（2026年1月23日）：推出 **macOS 终端沙箱**，将代理的终端操作隔离在沙箱环境中执行，防止对主系统产生意外影响。

#### Codex

- **持续**：Codex 包含在 ChatGPT **Business、Enterprise 和 Edu** 计划中，企业客户通过 ChatGPT 的统一管理后台进行用户管理和权限控制。云端任务在**隔离的 Cloud 环境**中执行，支持互联网访问但与用户本地环境隔离，适合处理敏感代码。同时深度集成 **GitHub**（代码审查、GitHub Actions）、**Slack** 和 **Linear**，融入企业现有工作流。

#### Lovable

- **2026年2月5日**：推出 **Test 和 Live 环境隔离**（Beta）。Lovable Cloud 项目现在支持两个独立环境，各自拥有独立的 Supabase 数据库实例。Test 环境用于开发和实验，Live 环境用于生产部署，防止开发过程中的数据污染。

#### Grok Build（xAI）

- **2026年2月**：Grok Build 在安全性上采用**本地优先架构**作为核心差异化——所有代码在用户本地机器上执行，无需上传至云端，从架构层面消除了代码泄露风险。同时提供企业级安全特性：
  - **空气隔离（Air-gap）兼容**：可在完全离线的环境中部署运行
  - **细粒度权限控制**：按文件、目录和脚本级别设置访问权限
  - **域名限制**：配置代理可访问的网络域名白名单
  - **完全透明**：代理的所有操作对用户可见可审计

#### Gemini Code Assist

- **持续**：Gemini Code Assist Enterprise 版基于 **Google Cloud** 基础设施，继承 Google Cloud 的企业安全体系：通过 **IAM（Identity and Access Management）** 进行细粒度权限管理，集成 **Cloud Audit Logs** 提供完整审计追踪，支持 **VPC Service Controls** 实现网络隔离。企业版使用 Gemini 2.5 Pro 模型（免费版使用 Flash），提供更高的请求配额和优先支持。

---

## 13. UI/UX 与交互创新 (UI/UX & Interaction Innovation)

> **行业趋势**：IDE 布局从"编辑器中心"向"代理中心"转型，浏览器内置和模型对比成为差异化方向。

### 功能介绍

**UI/UX 与交互创新**涵盖编码工具在用户界面、布局设计和交互方式上的创新。传统 IDE 围绕代码编辑器设计——侧边栏放文件树，底部放终端。但在 AI 代理时代，新的交互需求涌现：

- **布局适配**：代理对话窗口、浏览器预览、代理输出需要更高优先级的展示空间
- **模型对比**：让多个模型同时生成方案并排比较，帮助用户选择最优解
- **可视化编辑**：非技术用户通过拖拽和点击直接修改 UI，无需编写代码
- **批量处理**：排队多个任务，代理自动依次执行

### 样例说明

**场景一：Cursor 布局快捷切换**

```
开发者一天的工作流：

上午 — 编写功能代码
  → 快捷键切换至 "editor" 布局（代码编辑器占 80%）

下午 — 调试前端 UI
  → 切换至 "browser" 布局（内置浏览器占 50%，编辑器占 50%）

晚上 — 让代理批量处理任务
  → 切换至 "agent" 布局（代理对话窗口占主位）
```

**场景二：Lovable Visual Edits 可视化编辑**

```
非技术产品经理直接在 Lovable 中：
1. 选中"注册按钮" → 在侧边栏修改颜色为品牌蓝
2. 选中标题文字 → 调整字体粗细和对齐方式
3. 选中多个元素 → 批量调整间距和边距
4. 所有修改实时生成对应代码，无需使用 AI credits
```

**场景三：Codex Steer Mode 实时引导**

```
用户启动任务："实现购物车结算功能"

Codex 开始执行...
  → 正在创建 CartCheckout 组件...
  
用户中途发送引导（Enter 键）：
  "使用 Stripe Elements 而不是自定义表单"
  → Codex 立即调整方向，改用 Stripe 集成
  
用户继续引导：
  "别忘了添加优惠券验证"（Tab 键排队）
  → Codex 完成当前步骤后自动处理排队指令
```

**场景四：Windsurf Arena Mode 模型对比**

```
用户输入："优化这个 React 组件的渲染性能"

Arena Mode 并排显示：
┌─────────────────────┬─────────────────────┐
│ Claude Opus 4.6      │ GPT-5.2             │
│                      │                      │
│ 方案：使用 useMemo   │ 方案：拆分为更小组件 │
│ + React.memo 包裹    │ + 使用虚拟列表       │
│                      │                      │
│ 预计性能提升：3x     │ 预计性能提升：5x     │
│ [选择此方案]          │ [选择此方案]          │
└─────────────────────┴─────────────────────┘
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | v2.3（2025年12月22日） | 四种预设布局 | agent / editor / zen / browser 快捷切换 |
| **Windsurf** | Wave 14（2026年1月30日） | Arena Mode | 模型并排对比、Battle Groups、排行榜 |
| **Windsurf** | Wave 13（2025年12月24日） | Side-by-side Cascade | 并排对话窗格 |
| **Google Antigravity** | 持续 | 内置 Chromium 浏览器 | Artifacts 系统（截图/录屏/测试结果） |
| **Trae SOLO** | 持续 | 可视化工作区 | 实时感知反馈 |
| **Cursor** | Long-Running Agents（2026年2月12日） | cursor.com/agents Web 入口 | 浏览器端分配长时任务、实时监控进度 |
| **Codex** | v0.98 ~ App v260212 | Steer Mode + Floating Window + 多界面统一 | 弹出式跟随窗口 + 对话分叉 + CLI/IDE/Web/App 统一 |
| **Lovable** | 2026年1月~2月 | Visual Edits + Prompt Queue | 可视化 UI 编辑 + 批量任务排队 |
| **ChatGPT（Canvas）** | 持续更新 | 协作式编码工作区 | HTML/React 实时渲染、代码版本历史、多语言转换 |
| **Claude.ai** | Claude Code on Web（2025年10月） | Web 端并行编码 | 浏览器端多任务并行、GitHub PR 自动创建 |
| **Grok Build** | 2026年2月 | CLI + Web UI 双入口 | WebSocket 同步、集中式提示栏 |
| **Bolt** | v2 持续 | 浏览器端开发环境 | WebContainer 全浏览器运行时 |

### 详细更新

#### Cursor

- **v2.3**（2025年12月22日）：引入**四种预设布局**——`agent`（代理对话优先）、`editor`（代码编辑优先）、`zen`（极简模式）、`browser`（浏览器预览优先），支持快捷键一键切换。这一设计承认了不同开发阶段需要不同的 UI 焦点。
- **Long-Running Agents Web 入口**（2026年2月12日）：在 `cursor.com/agents` 推出**独立 Web 界面**用于分配和监控长时自主任务。这是 Cursor 首次将交互入口从 IDE 扩展到浏览器——用户可以在浏览器中提交任务、审批计划、查看代理进度，而无需打开 IDE。标志着 Cursor 从"IDE 产品"向"IDE + Web + CLI 多入口平台"演进。

#### Windsurf

- **Wave 14**（2026年1月30日）：推出 **Arena Mode**——允许多个模型同时对同一任务生成解决方案并**并排对比**。支持 **Battle Groups**（将模型分组对决）和**个人/全局排行榜**，通过社区投票评选最佳模型。这是一种创新的模型评估方式。
- **Wave 13**（2025年12月24日）：引入 **Side-by-side Cascade** 窗格，支持同时开启两个代理对话窗口进行并排比较。

#### Google Antigravity

- **持续更新**：**内置 Chromium 浏览器**是其核心差异化特性，代理可以直接在浏览器中预览和调试应用。**Artifacts 系统**自动保存代理操作过程中的截图、录屏和测试结果，形成完整的操作记录。

#### Trae SOLO

- **持续更新**：**可视化工作区**支持实时显示代理的执行状态和进度，提供感知反馈，让开发者了解代理"在做什么"。

#### Codex

- **v0.98**（2026年2月5日）：**Steer Mode** 稳定并默认启用——这是 Codex 独特的交互范式：代理在执行任务的过程中，用户可以用 **Enter** 键实时发送指令引导代理方向，用 **Tab** 键将指令排队等待当前步骤完成后执行。这种"边执行边引导"的交互方式介于 Plan Mode（先规划后执行）和自动模式（完全委托）之间。
- **Codex App v260212**（2026年2月12日）：引入 **Floating Pop-out Window**（弹出式浮动窗口），允许用户将 Codex 对话弹出为独立小窗口，在切换到其他应用时持续跟踪代理工作进度。同步新增**对话分叉**（Conversation Forking）功能——在对话中的任意节点创建分支探索不同方向，无需重新开始。Windows 版本开始 **alpha 测试**。
- **多界面统一**（持续）：Codex 是目前覆盖界面最广的编码代理——**CLI、IDE 扩展（VS Code / Cursor）、Web 端、ChatGPT App、GitHub 集成、Slack 和 Linear 集成**共享同一 ChatGPT 账户，上下文和配置在所有界面间无缝同步。

#### Lovable

- **Visual Edits**（2026年1月~2月，持续迭代）：推出并快速迭代**可视化编辑**功能，允许用户在不编写代码的情况下直接修改 UI。支持编辑**字体粗细**、**对齐方式**、**图片尺寸**，选择父元素进行批量编辑，调整边距、边框、阴影和图标。所有修改实时生成对应代码，不消耗 AI credits。
- **Prompt Queue**（2026年2月5日）：新增**提示词排队**功能，支持批量发送提示词后让 Lovable 逐个处理。用户可以暂停/恢复、重新排序、编辑、复制或删除排队的提示词，支持单个提示词重复执行最多 **500 次**，适合批量自动化工作流。

#### ChatGPT（Canvas）

- **持续更新**：ChatGPT Canvas 是 OpenAI 在 ChatGPT 内构建的**协作式编码工作区**，在对话界面之外提供独立的代码编辑空间。核心交互创新包括：
  - **HTML/React 实时渲染**（2025年1月）：Canvas 内编写的 HTML 和 React 代码可直接在界面中渲染预览，无需离开 ChatGPT 即可看到效果——这与 Claude Artifacts 的交互式应用生成异曲同工
  - **高亮选区编辑**：用户可选中代码片段，针对性地要求 AI 修改选区内容，而非重写整段代码
  - **版本历史**：内置回退按钮，可恢复至之前的代码版本，并高亮显示变更
  - **多语言代码转换**：一键将代码转换为 JavaScript、TypeScript、Python、Java、C++、PHP 等语言
  - **内置 Python 控制台**：直接在 Canvas 中运行 Python 代码片段，查看执行结果
  - 用户可在 Canvas 中选择 o3、o4-mini 等推理模型，获得更强的编码推理能力

> **注**：Canvas 与 Codex 在 OpenAI 生态中定位互补——Canvas 面向"交互式编码对话"场景（快速原型、代码审查、学习），Codex 面向"自主编码代理"场景（大型项目、CI/CD 集成、多文件重构）。

#### Claude.ai（Claude Code on Web）

- **2025年10月**：Anthropic 推出 **Claude Code on Web**（research preview），将 Claude Code 从命令行扩展到浏览器端。用户可在 `claude.com/code` 直接分配编码任务，无需打开终端。核心交互特性：
  - **并行任务执行**：从单一界面同时向多个代码库分配任务，每个任务在独立沙箱中运行并实时显示进度
  - **GitHub 深度集成**：连接 GitHub 仓库，描述需要的变更，Claude 自动实现并创建 PR（含清晰的变更摘要）
  - **隔离安全环境**：每个任务在 Anthropic 托管的云基础设施上运行，网络和文件系统受限，Git 交互通过安全代理
  - **适用场景**：Bug 修复积压处理、常规维护任务、带测试驱动验证的后端开发
  - Pro 和 Max 用户可用，Team 和 Enterprise Premium 用户于 2025年11月获得访问权限

> **注**：Claude Code 至此形成 **CLI + Web + IDE 扩展** 三入口体系——CLI 面向终端重度用户和 CI/CD 集成，Web 面向浏览器端轻量化任务分配，IDE 扩展（VS Code / JetBrains）面向编辑器内工作流。三者共享同一 Claude 账户和模型能力。

#### Grok Build（xAI）

- **2026年2月**：Grok Build 采用 **CLI + Web UI 双入口**设计——通过 npm 安装 CLI 工具后，同时启动一个本地 Web 界面，两者通过 **WebSocket** 实时同步状态。Web UI 提供集中式提示栏，开发者可通过对话式交互驱动编码，显著降低编程门槛。远程编码代理（云端执行）计划后续推出。

#### Bolt

- **v2**（持续）：以**全浏览器开发环境**为核心交互范式。基于 StackBlitz 的 **WebContainer 技术**（WebAssembly 运行时），在浏览器中运行完整的 Node.js 环境，实现即时启动、零延迟开发。用户无需配置任何本地开发环境即可开始全栈开发。

---

## 14. 图像生成与多模态 (Image Generation & Multimodal)

> **行业趋势**：编码代理从纯文本走向多模态，图像生成和视觉验证成为新能力。

### 功能介绍

**多模态能力**使编码工具能够理解和生成文本以外的内容——图像、设计稿、视觉元素等。这一能力在三个方面改变了开发工作流：

- **图像生成**：直接在编码环境中生成 icon、插图、占位图等视觉素材
- **设计转代码**：将 Figma 等设计工具的输出转换为可运行的前端代码
- **视觉验证**：自动截取应用界面，与设计稿对比，发现并修正视觉差异

### 样例说明

**场景一：Cursor 生成应用图标**

```
用户输入："为这个天气应用生成一个 app icon，
         扁平化设计，蓝色渐变背景，白色云朵和太阳"

→ Cursor 调用 Google Nano Banana Pro 模型
→ 生成 PNG 图标 → 自动保存至 public/icons/
→ 更新 manifest.json 中的图标引用
```

**场景二：Figma → Lovable 完整应用生成**

```
设计师在 Figma 中完成设计：
1. 设计登录页、注册页、仪表盘 3 个页面
2. 使用 Auto Layout 确保响应式
3. 在 Figma 中选择所有帧 → 点击 Builder.io 插件 → "Open in Lovable"

Lovable 接收设计数据：
→ 自动生成 React 组件 + Tailwind CSS 样式
→ 添加页面路由和导航
→ 集成 Supabase Auth 实现真实登录功能
→ 部署为可访问的在线应用
```

**场景三：Figma Vectorize 将手绘转为可编辑矢量**

```
设计师上传手绘 logo 草图（PNG 格式）：
→ Figma AI 分析图像轮廓
→ 转换为可编辑的矢量路径
→ 设计师可自由调整颜色、大小、形状
→ 导出为 SVG 供开发者使用
```

### 更新总览

| 产品 | 版本/日期 | 更新内容 | 亮点 |
|------|----------|---------|------|
| **Cursor** | v2.4（2026年1月22日） | 图像生成 | Google Nano Banana Pro 模型 |
| **Trae SOLO** | 持续 | 多模态上下文 | Figma 设计稿转代码 |
| **Google Antigravity** | 持续 | 视觉验证 | 内置浏览器 QA 截图 |
| **Figma** | 持续 ~ 2026年2月 | Make / Vectorize / Buzz | 设计生成 + 图像向量化 + 品牌资产生成 |
| **Lovable** | 持续 | Figma 转代码 + Visual Edits | Builder.io 插件 + 可视化编辑 |
| **Codex** | 持续 | 图像/截图分析 | 前端设计验证 + 视觉输入理解 |
| **Claude.ai（Artifacts）** | 2025年7月 GA / 10月 MCP | 交互式应用生成 | 可视化 React 应用 / 游戏 / 教育工具，5亿+ 创建量 |
| **Gemini 2.5** | 持续 | 原生多模态 | 文本/代码/图像/音频/视频统一输入，视频转代码 |
| **ChatGPT（Canvas）** | 持续 | HTML/React 实时渲染 | 代码即时可视化预览 |
| **Bolt** | 持续 | Figma 转代码 | Anima 集成设计稿导入 |

### 详细更新

#### Cursor

- **v2.4**（2026年1月22日）：新增**图像生成**能力，支持通过文本描述和参考图片生成图像资产，底层使用 Google 的 **Nano Banana Pro** 模型。开发者可以在编码过程中直接生成 icon、placeholder 图片等视觉素材，无需切换到外部设计工具。

#### Trae SOLO

- **持续更新**：支持**多模态上下文理解**，可以接收图片、设计稿等视觉输入。亮点功能是 **Figma 设计稿转代码**——直接将 Figma 设计文件作为输入，生成对应的前端代码。

#### Google Antigravity

- **持续更新**：通过内置 Chromium 浏览器实现**视觉验证**——代理可以自动截取应用的 QA 截图，与预期设计进行视觉对比，并基于对比结果自动修正 CSS 和布局代码。

#### Figma

- **Figma Make**（2025年5月发布，2025年7月 GA，持续更新）：AI 驱动的**设计生成工具**，支持通过自然语言和图片生成可编辑的设计稿和交互原型。用户可以在对话中附加 Figma 组件进行实时迭代，并将原型发布为可访问的网页。
- **Vectorize Images**（2026年2月）：新增 **AI 图像向量化**功能，可将静态图片（手绘草图、PNG 图标、纹理等）转换为可编辑的矢量图形，适用于 Figma Design 和 Draw。
- **Figma Buzz**（beta）：**品牌资产批量生成**工具，支持 42+ 预定义资产类型（Instagram、LinkedIn、Twitter 等社交媒体格式），通过 AI 生成符合品牌规范的营销素材。

#### Lovable

- **Figma 转代码**（持续）：通过 **Builder.io 插件**实现 Figma 设计稿到完整应用的转换。设计师在 Figma 中使用 Auto Layout 完成设计后，一键导入 Lovable，自动生成包含路由、认证和数据库集成的完整前端应用。
- **Visual Edits**（2026年1月~2月）：可视化编辑功能让用户直接在应用预览中修改 UI 元素，支持调整字体、颜色、间距、边框等，修改实时反映为代码变更。

#### Codex

- **持续**：GPT-5-Codex / GPT-5.3-Codex 支持**图像和截图分析**，可以接收前端界面截图作为输入，分析 UI 布局和设计细节，然后生成或修正对应的前端代码。这使得 Codex 能够进行"视觉驱动的开发"——用户上传设计稿或 Bug 截图，代理直接基于视觉信息编写代码。

#### Claude.ai（Artifacts）

- **2025年7月 GA / 10月 MCP 集成**：Claude Artifacts 已发展为一个强大的**交互式应用生成平台**。用户通过自然语言描述，Claude 可直接生成可运行的 React 组件、HTML 网页、SVG 图像、交互式游戏、教育工具和数据可视化。截至文档整理时累计创建量超过 **5 亿个** Artifacts。2025年7月 GA 时扩展至 **iOS 和 Android** 客户端，2025年10月新增 **MCP 集成**和**持久化存储**后，Artifacts 可以连接外部数据源并保持状态跨会话。这使得非技术用户也能"零代码"构建功能完整的交互式应用。

#### Gemini 2.5（原生多模态）

- **持续**：Gemini 2.5 系列（Pro / Flash）是当前 AI 模型中**原生多模态能力最全面的**之一——统一支持文本、代码、图像、音频和视频作为输入。对编码场景的独特价值：
  - **视频转代码**：接收视频输入（如操作录屏、UI 演示），直接生成对应的前端代码实现
  - **图像理解**：分析设计稿截图、错误截图等视觉输入，辅助调试和代码生成
  - **代码执行**：Gemini 2.5 Pro 支持自主执行代码（agentic code execution），在生成后自动验证
  - 这些多模态能力通过 Gemini Code Assist Agent Mode 直接在 IDE 中可用

#### ChatGPT（Canvas）

- **持续**：Canvas 的 **HTML/React 实时渲染**能力使其成为一个轻量级的多模态编码环境——代码编写后即时可视化，开发者无需在编辑器和浏览器之间切换。结合 Code Interpreter 的 Python 执行能力，Canvas 可以生成数据可视化、图表和简单的交互式应用。虽然不如专业 IDE 代理的多模态能力全面，但为数百万 ChatGPT 用户提供了"从文本到可视化代码"的便捷路径。

#### Bolt

- **Figma 集成**（持续）：通过 **Anima 集成**支持 Figma 设计稿导入。用户可以复制 Figma 帧 URL 或在 URL 前添加 `bolt.new:` 前缀直接导入，Anima 将设计转换为响应式 Web 代码。建议设计使用 Auto Layout 和语义化命名以获得最佳转换效果。

---

## 15. 趋势总结与展望

### 七大交叉趋势

回顾 11 个功能维度的更新，可以提炼出 2025Q4—2026Q1 编码代理行业的七大交叉趋势：

1. **从辅助到自主** | ★ *长时自主代理的出现是 2026 年 2 月最具颠覆性的变化*

   这是本次更新周期最值得关注的新趋势。Cursor Long-Running Agents 实现了 **52 小时连续自主编码**并产出 15 万行代码，Self-Driving Codebase 研究达到**每小时 1000 次提交**。GPT-5.3-Codex 可独立工作超过 7 小时。这标志着编码代理正在从"对话式辅助工具"进化为"可独立交付的虚拟开发者"——开发者的角色加速从"代码编写者"向"任务规划者和代码审查者"转变。与此同时，GitHub Agentic Workflows 将代理嵌入 CI/CD 流水线，实现仓库维护的持续自动化。**"人类分配任务，代理自主交付"正在从愿景变为现实。**

2. **从单体到分布式** | *多代理架构 + CLI 代理 + Hooks 共同指向一个方向*

   代理正在从"一个大模型做所有事"演变为"多个专业代理协作"。Subagents 处理并行子任务，CLI 代理负责自动化流水线，Hooks 提供精细化控制点。Cursor Self-Driving Codebase 的递归 Planner-Worker 架构将这一趋势推向极致——数千个代理通过层级结构自动协调，无需人类参与调度。这与微服务架构的演进逻辑高度一致——分解、专业化、可编排。

3. **从黑盒到可控** | *Plan Mode + Hooks + Enterprise 功能共同降低风险*

   行业已经度过了"让 AI 随意写代码"的阶段。先规划后执行（Plan Mode）、关键节点可干预（Hooks）、操作可审计（Enterprise Analytics）——这三层控制机制使企业能够安全地大规模部署编码代理。值得注意的是，**全栈生成器（Lovable、Bolt）也在快速补齐这一能力**——Plan Mode 和环境隔离的引入标志着"零门槛"工具同样重视可控性。Grok Build 的**本地优先+空气隔离**架构则从另一个角度回应了企业对安全性的关切。

4. **从工具到平台** | *Skills + MCP + Extensions + Agentic Workflows 构建可扩展生态*

   编码代理不再是封闭的工具，而是开放的平台。Skills 让社区可以贡献领域知识，MCP 让外部工具可以无缝接入，Extensions 让第三方开发者可以构建插件。**GitHub Agentic Workflows** 更进一步——用 Markdown 定义 CI/CD 自动化，支持多种 AI 引擎，将代理能力嵌入开发基础设施。**Augment Context Engine MCP** 首次将"代码库理解能力"作为独立 MCP 服务开放给所有竞品工具（Claude Code +80%、Cursor +71% 质量提升），验证了 MCP 生态的开放性——即使是竞争对手的产品也能从中受益。

5. **从文本到多模态** | *图像生成 + 视觉验证 + 设计转代码 + 交互式应用生成拓展能力边界*

   代理的"感知—理解—行动"循环正在从纯文本扩展到视觉领域。**Figma Make + Figma MCP + Lovable/Bolt Figma 集成**形成了"设计→结构化数据→代码→部署"的完整多模态管线。**Claude Artifacts** 让非技术用户也能通过自然语言生成交互式应用（5亿+ 创建量），**Gemini 2.5** 的原生多模态（视频转代码）和 **ChatGPT Canvas** 的实时渲染进一步丰富了多模态编码场景。

6. **从差异化到标准化，再到新差异化** | *功能快速趋同的同时，新的差异化方向涌现*

   一个产品的创新功能在 1—2 个月内就会被竞品跟进。Plan Mode 从 Cursor 独有变为行业标配，CLI 代理从 Claude Code 首创变为多款产品支持，MCP 从协议提案变为事实标准。但新的差异化方向正在涌现：Cursor 的 **Long-Running Agents** 开辟了"小时级自主编码"赛道，OpenAI 的 **GPT-5.3-Codex-Spark**（1000+ tokens/s）开辟了"极速实时编码"赛道，GitHub 的 **Agentic Workflows** 开辟了"CI/CD 自动化代理"赛道。GitHub Copilot **同日淘汰四款旧模型**的决定更表明——模型已不再是差异化因素，**代理架构和交互范式才是竞争的核心**。

7. **通用 AI 平台向编码工作区延伸** | *ChatGPT Canvas + Claude Code on Web + Gemini Code Assist + Cursor Web 入口多方向模糊边界*

   通用 AI 平台不再满足于"能写代码的聊天机器人"，而是构建专业级的编码工作区：**ChatGPT Canvas** 提供协作式代码编辑和实时渲染，**Claude Code on Web** 支持云端并行编码任务和 GitHub PR 自动创建，**Gemini Code Assist Agent Mode** 直接在 IDE 中实现自主多步骤编码。反过来，**Cursor 也从 IDE 向 Web 延伸**——Long-Running Agents 的 `cursor.com/agents` 入口标志着 IDE 厂商开始构建浏览器端产品。与此同时，**xAI 的 Grok Build** 和 **Codex 的 Floating Window + 多界面统一**进一步模糊了"IDE 产品"和"通用平台"的边界。编码代理的竞争已经**扩展为 IDE、CLI、Web、App 四入口的全方位竞争**。

### 与《产品形态全景》的呼应

本 Changelog 汇总进一步验证了[《AI 编码代理产品形态全景》](./20250126%20AI%20编码代理产品形态全景.md)中的核心判断：

| 全景文档判断 | Changelog 验证 |
|------------|---------------|
| "五大形态各司其职，专业化分工是必然" | 多代理架构让形态内部也开始分工，Subagents 各有专长；同时通用 AI 平台（ChatGPT、Claude.ai、Gemini）正在跨界进入编码工具领域；**形态边界加速模糊**——Cursor 从 IDE 走向 Web，Codex 从 CLI 走向 Floating Window |
| "MCP 是连接器，Skills 是指挥官" | SKILL.md / AGENTS.md 生态在 8+ 款产品中快速铺开，MCP 成为事实标准；**Augment Context Engine MCP 首次将"代码理解能力"作为 MCP 服务开放给竞品**，验证了 MCP 生态的开放性 |
| "从 Prompt Engineering 到 Flow Engineering" | SKILL.md、Hooks、Plan Mode、**GitHub Agentic Workflows**（Markdown 定义自动化）共同实现了流程化开发 |
| "单一产品无法满足需求，组合策略是王道" | 每款产品都在补齐短板（IDE 加 CLI 加 Web、CLI 加 Skills、生成器加 Plan Mode），通用平台也在构建专业编码入口（Canvas、Claude Code on Web） |
| "从辅助到自主的转型期" | **Long-Running Agents（52h 自主编码）和 Self-Driving Codebase（1000 commits/h）标志着"从辅助到自主"已从趋势变为现实**；Agent Teams（16 实例协作）、GitHub Agentic Workflows（CI/CD 自动化）从不同角度推动自主化 |
| "全栈生成器解决快速验证问题" | Bolt v2 + Lovable 持续强化 Figma 集成、环境隔离等能力；**两者同步集成 Opus 4.6 显著提升代码质量**；Claude Artifacts 5亿+ 创建量证明了"零代码应用生成"的巨大需求 |

### 2026 年展望

基于当前的更新趋势，2026 年上半年编码代理领域可能出现以下发展：

- ★ **长时自主代理从研究走向生产**：Cursor Long-Running Agents 目前处于研究预览阶段，预计 2026 年 H1 将 GA 并被竞品快速跟进。52 小时自主编码的上限可能进一步扩展，"按任务计费"而非"按月订阅"的商业模式可能出现
- ★ **"代理即服务"兴起**：Augment Context Engine MCP 首开先河，将内部能力作为服务开放给竞品。预计更多产品会将核心能力（代码理解、代码审查、测试生成）封装为 MCP 服务，形成**代理能力的"组件化"市场**
- ★ **CI/CD 代理化**：GitHub Agentic Workflows 将代理嵌入 CI/CD 流水线，预计 GitLab、Bitbucket 等平台会快速跟进。"AI 自动修复 CI 失败"、"AI 自动处理依赖更新"等场景将率先落地
- **Agent Teams 规模化**：多代理协作从实验走向生产，支持 50+ 代理实例的大规模协作
- **Debug Mode 普及**：运行时智能从 Cursor 独有扩展到更多产品
- **Skills 生态成熟**：出现专业化的 Skills 市场和社区
- **企业部署加速**：安全沙箱和审计功能成熟，推动大型企业规模化部署；Grok Build 的本地优先架构可能带动"数据不出域"的新范式
- **视觉能力标准化**：图像生成和视觉验证成为编码代理的基础能力
- **设计→代码链路贯通**：Figma MCP + 全栈生成器形成标准化的设计实现管线
- **全栈生成器与 IDE 代理融合**：两类产品互相借鉴，功能边界逐渐模糊
- **通用平台编码能力深化**：ChatGPT Canvas、Claude Code on Web、Gemini Code Assist 将持续从通用对话工具向专业编码工作区演进；**Cursor 的 Web 入口**标志着 IDE 厂商也在反向进入通用平台领域
- **"极速模型"赛道加速**：GPT-5.3-Codex-Spark（1000+ tokens/s / Cerebras）和 Grok Code Fast 1（92 tokens/s）代表了"速度优先"的模型路线。预计更多"模型+专用芯片"的合作模式出现，极速模型可能成为实时编辑场景的标配
- **旧模型淘汰周期缩短至 6 个月**：GitHub Copilot 同日淘汰四款模型的先例表明，模型更新迭代速度正在加快，工具和工作流的"模型无关性"变得至关重要
- **新进入者涌入**：xAI（Grok Build）的加入仅是开端，更多通用 AI 公司和云服务商可能推出独立编码代理产品，行业竞争格局将更加多元

---

## 附录：数据来源与参考链接

本文档的更新信息基于各产品的官方 Changelog 和发布公告：

| 产品 | 官方 Changelog 来源 |
|------|-------------------|
| **Cursor** | [Cursor Changelog](https://www.cursor.com/changelog) |
| **GitHub Copilot** | [GitHub Blog](https://github.blog/) / [Copilot Docs](https://docs.github.com/en/copilot) |
| **Claude Code** | [Anthropic News](https://www.anthropic.com/news) / [Claude Code Changelog](https://docs.anthropic.com/en/docs/claude-code/changelog) |
| **Trae** | [Trae Official](https://trae.ai/) |
| **Google Antigravity** | [Antigravity Release Notes](https://docs.antigravity.dev/) |
| **Gemini CLI** | [Gemini CLI GitHub](https://github.com/google-gemini/gemini-cli) |
| **Windsurf** | [Windsurf Changelog](https://windsurf.com/changelog) |
| **Augment Code** | [Augment Blog](https://www.augmentcode.com/blog) |
| **Codex** | [Codex Changelog](https://developers.openai.com/codex/changelog) / [OpenAI Blog](https://openai.com/index/) |
| **Bolt** | [Bolt Blog](https://bolt.new/blog) / [Bolt Release Notes](https://support.bolt.new/release-notes) |
| **Lovable** | [Lovable Changelog](https://docs.lovable.dev/changelog) / [Lovable Blog](https://lovable.dev/blog) |
| **Gemini Code Assist** | [Gemini Code Assist Release Notes](https://developers.google.com/gemini-code-assist/resources/release-notes) / [Google Cloud Gemini Docs](https://docs.cloud.google.com/gemini/docs/release-notes) |
| **ChatGPT（Canvas）** | [OpenAI Blog](https://openai.com/index/) / [OpenAI Help Center](https://help.openai.com/) |
| **Claude.ai** | [Claude Blog](https://www.claude.com/blog) / [Anthropic News](https://www.anthropic.com/news) / [Claude Platform Release Notes](https://platform.claude.com/docs/en/release-notes/overview) |
| **Grok / xAI** | [xAI Release Notes](https://docs.x.ai/docs/release-notes) / [Grok Build](https://grokai.build/) |
| **Figma** | [Figma Release Notes](https://www.figma.com/release-notes/) / [Figma Blog](https://www.figma.com/blog/) |

> **免责声明**：版本号和日期基于各产品官方发布信息，部分 beta/preview 功能的可用性可能因用户账户类型和地区而异。

---

*文档整理时间：2026年2月18日（增补 Cursor Long-Running Agents / GPT-5.3-Codex-Spark / GitHub Agentic Workflows / Augment Context Engine MCP / 模型淘汰等内容）*
*本文档为[《AI 编码代理产品形态全景（2026年1月）》](./20250126%20AI%20编码代理产品形态全景.md)的配套 Changelog 汇总*
*覆盖 16 个产品/产品线，11 个功能维度，数据来源经过交叉验证，如有更新请以官方最新发布为准*
