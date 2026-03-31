![GitHub stars](https://img.shields.io/github/stars/phuryn/pm-skills)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](https://github.com/phuryn/pm-skills/blob/main/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](https://github.com/phuryn/pm-skills/blob/main/CONTRIBUTING.md)

# PM Skills Marketplace：AI 驱动的产品决策操作系统

> 8 个插件包含 65 项 PM 技能和 36 个链式工作流。支持 Claude Code、Cowork 等工具。覆盖从发现、策略、执行、发布到增长的完整产品管理流程。

![插件概览](.docs/images/plugins-overview.webp)

专为 Claude Code 和 Cowork 设计。技能与其他 AI 助手兼容。

## 从这里开始

有新想法？→ `/discover`  
需要战略清晰？→ `/strategy`  
正在写 PRD？→ `/write-prd`  
规划产品发布？→ `/plan-launch`  
定义指标？→ `/north-star`

如果这个项目对你有帮助，请给仓库 ⭐ 星标。

## 为什么选择 PM Skills Marketplace？

通用 AI 给你文本。PM Skills Marketplace 给你结构。

每项技能都编码了一个经过验证的 PM 框架——发现、假设映射、优先级排序、策略——并逐步引导你完成。你将 Teresa Torres、Marty Cagan 和 Alberto Savoia 的严谨方法论融入日常工作流程，而不是让它们束之高阁。

结果：更好的产品决策，而不仅仅是更快的文档。

## 工作原理（技能、命令、插件）

**技能**是市场的构建模块。每项技能为 Claude 提供特定 PM 任务的领域知识、分析框架或引导式工作流。有些技能还作为多个命令共享的可复用基础。

技能在与对话相关时自动加载——无需显式调用。如果需要（例如，优先使用技能而非通用知识），你可以使用 `/plugin-name:skill-name` 或 `/skill-name`（Claude 会自动添加前缀）**强制加载技能**。

**命令**是用户通过 `/command-name` 触发的工作流。它们将一个或多个技能链接成端到端流程。例如，`/discover` 将四个技能链接在一起：头脑风暴想法 → 识别假设 → 优先级排序假设 → 头脑风暴实验。

**插件**将相关技能和命令分组为可安装的包。每个插件覆盖一个 PM 领域——发现、策略、执行等。安装市场即可一次性获得全部 8 个插件。

![技能工作原理](.docs/images/how-skills-work.webp)

命令使用技能。有些技能服务于多个命令。有些技能（如 `prioritization-frameworks` 或 `opportunity-solution-tree`）是独立参考资料，Claude 会在相关时随时调用——无需命令。

命令设计为相互衔接，匹配 PM 工作流。任何命令完成后，都会建议相关的下一步命令——只需跟随提示即可。

## 安装

### Claude Cowork（推荐给非开发者）

1. 打开 **Customize**（左下角）
2. 进入 **Browse plugins** → **Personal** → **+**
3. 选择 **Add marketplace from GitHub**
4. 输入：`phuryn/pm-skills`

所有 8 个插件将自动安装。你将获得命令（`/discover`、`/strategy` 等）和技能。

![在 Claude Cowork 中安装 PM Skills](.docs/images/pm-skills-install.gif)

### Claude Code（CLI）

```bash
# 步骤 1：添加市场
claude plugin marketplace add phuryn/pm-skills

# 步骤 2：安装单个插件
claude plugin install pm-toolkit@pm-skills
claude plugin install pm-product-strategy@pm-skills
claude plugin install pm-product-discovery@pm-skills 
claude plugin install pm-market-research@pm-skills 
claude plugin install pm-data-analytics@pm-skills
claude plugin install pm-marketing-growth@pm-skills
claude plugin install pm-go-to-market@pm-skills
claude plugin install pm-execution@pm-skills
```

### 其他 AI 助手（仅技能）

`skills/*/SKILL.md` 文件遵循通用技能格式，适用于任何读取它的工具。命令（`/slash-commands`）是 Claude 特有的。

| 工具 | 使用方法 | 适用内容 |
|------|---------|---------|
| **Gemini CLI** | 将技能文件夹复制到 `.gemini/skills/` | 仅技能 |
| **OpenCode** | 将技能文件夹复制到 `.opencode/skills/` | 仅技能 |
| **Cursor** | 将技能文件夹复制到 `.cursor/skills/` | 仅技能 |
| **Codex CLI** | 将技能文件夹复制到 `.codex/skills/` | 仅技能 |
| **Kiro** | 将技能文件夹复制到 `.kiro/skills/` | 仅技能 |

```bash
# 示例：为 OpenCode 复制所有技能（项目级）
for plugin in pm-*/; do
  mkdir -p .opencode/skills/
  cp -r "$plugin/skills/"* .opencode/skills/ 2>/dev/null
done

# 示例：为 Gemini CLI 复制所有技能（全局）
for plugin in pm-*/; do
  cp -r "$plugin/skills/"* ~/.gemini/skills/ 2>/dev/null
done
```

---

## 可用插件

<details>
<summary><strong>1. pm-product-discovery</strong> — 创意构思、实验、假设测试、OST、访谈（13 项技能，5 个命令）</summary>

**技能（13）：**

- `brainstorm-ideas-existing` — 针对现有产品的多视角创意构思（PM、设计师、工程师）
- `brainstorm-ideas-new` — 针对新产品初期发现的创意构思
- `brainstorm-experiments-existing` — 为现有产品设计实验以测试假设
- `brainstorm-experiments-new` — 为新产品设计精益创业原型（Alberto Savoia）
- `identify-assumptions-existing` — 识别价值、可用性、可行性和可实施性方面的风险假设
- `identify-assumptions-new` — 识别包括市场进入、战略和团队在内的 8 个风险类别的风险假设
- `prioritize-assumptions` — 使用影响 × 风险矩阵对假设进行优先级排序，并提供实验建议
- `prioritize-features` — 基于影响、工作量、风险和战略一致性对功能待办列表进行优先级排序
- `analyze-feature-requests` — 按主题和战略契合度分析和分类客户功能请求
- `opportunity-solution-tree` — 构建机会解决方案树（Teresa Torres）——成果 → 机会 → 解决方案 → 实验
- `interview-script` — 创建结构化客户访谈脚本，包含 JTBD 探询问题
- `summarize-interview` — 将访谈记录总结为 JTBD、满意度信号和行动项
- `metrics-dashboard` — 设计产品指标仪表板，包含北极星指标、输入指标和警报阈值

**命令（5）：**

- `/discover` — 完整发现周期：创意构思 → 假设映射 → 优先级排序 → 实验设计
- `/brainstorm` — 多视角创意构思（`想法|实验` × `现有|新`）
- `/triage-requests` — 分析和优先级排序一批功能请求
- `/interview` — 准备访谈脚本或总结记录（`prep|summarize`）
- `/setup-metrics` — 设计产品指标仪表板

**示例：**

技能：
- `我们的 AI 写作助手想法有哪些最危险的假设？`
- `帮我为改善用户激活构建一个机会解决方案树`
- `为我们的企业客户的这 12 个功能请求进行优先级排序 [附加 CSV]`

命令：
- `/discover 面向远程团队的 AI 会议摘要工具`
- `/brainstorm experiments existing — 我们需要减少入职流程中的流失`
- `/interview prep — 我们正在访谈企业买家关于他们的采购工作流`

</details>

<details>
<summary><strong>2. pm-product-strategy</strong> — 愿景、商业模式、定价、竞争格局（12 项技能，5 个命令）</summary>

产品战略、愿景、商业模式、定价和宏观环境分析。涵盖从愿景制定到竞争格局扫描的完整战略工具包。

**技能（12）：**

- `product-strategy` — 全面的 9 部分产品战略画布（愿景 → 防御性）
- `startup-canvas` — 结合产品战略（9 部分）+ 商业模式的创业画布——新产品替代 BMC 和精益画布的选择
- `product-vision` — 制定鼓舞人心、可实现且富有情感的产品愿景
- `value-proposition` — 6 部分 JTBD 价值主张（谁、为什么、之前是什么、如何、之后是什么、替代方案）
- `lean-canvas` — 针对创业和新产品的精益画布商业模式
- `business-model` — 包含全部 9 个构建模块的商业模式画布
- `monetization-strategy` — 头脑风暴 3-5 种变现策略及验证实验
- `pricing-strategy` — 定价模型、竞争分析、支付意愿和价格弹性
- `swot-analysis` — 包含可行建议的 SWOT 分析
- `pestle-analysis` — 宏观环境：政治、经济、社会、技术、法律、环境
- `porters-five-forces` — 竞争力分析（竞争、供应商、买家、替代品、新进入者）
- `ansoff-matrix` — 跨市场和产品的增长战略映射

**命令（5）：**

- `/strategy` — 创建完整的 9 部分产品战略画布
- `/business-model` — 探索商业模式（`lean|full|startup|value-prop|all`）
- `/value-proposition` — 使用 6 部分 JTBD 模板设计价值主张
- `/market-scan` — 结合 SWOT + PESTLE + 波特五力 + 安索夫的宏观环境分析
- `/pricing` — 设计包含竞争分析和实验的定价策略

**示例：**

技能：
- `为我的市场创业比较精益画布 vs 商业模式画布 vs 创业画布`
- `为我们的 AI 写作助手针对非英语母语者设计价值主张`
- `对项目管理 SaaS 市场进行波特五力分析`

命令：
- `/strategy 面向代理机构的 B2B 项目管理工具`
- `/business-model startup — 面向非英语母语者的 AI 写作工具`
- `/value-proposition 面向企业客户的 SaaS 入职工具`

</details>

<details>
<summary><strong>3. pm-execution</strong> — PRD、OKR、路线图、冲刺、回顾、发布说明、利益相关者管理（15 项技能，10 个命令）</summary>

日常产品管理：PRD、OKR、路线图、冲刺、回顾、发布说明、事前分析、利益相关者管理、用户故事和优先级排序框架。

**技能（15）：**

- `create-prd` — 全面的 8 部分 PRD 模板
- `brainstorm-okrs` — 与公司目标对齐的团队级 OKR
- `outcome-roadmap` — 将功能列表转化为以成果为中心的路线图
- `sprint-plan` — 包含容量估算、故事选择和风险识别的冲刺规划
- `retro` — 结构化冲刺回顾引导
- `release-notes` — 从工单、PRD 或变更日志生成面向用户的发布说明
- `pre-mortem` — 包含老虎/纸老虎/大象分类的风险分析
- `stakeholder-map` — 权力 × 利益网格及定制沟通计划
- `summarize-meeting` — 会议记录 → 决策 + 行动项
- `user-stories` — 遵循 3C 和 INVEST 标准的用户故事
- `job-stories` — 工作故事：当[情境]时，我想要[动机]，以便我能[结果]
- `wwas` — 采用为什么-什么-验收格式的产品待办事项
- `test-scenarios` — 测试场景：快乐路径、边缘情况、错误处理
- `dummy-dataset` — 逼真的虚拟数据集，格式为 CSV、JSON、SQL 或 Python
- `prioritization-frameworks` — 9 种优先级排序框架参考指南（机会分数、ICE、RICE、MoSCoW、Kano 等）

**命令（10）：**

- `/write-prd` — 从功能想法或问题陈述创建 PRD
- `/plan-okrs` — 头脑风暴团队级 OKR
- `/transform-roadmap` — 将基于功能的路线图转化为以成果为中心
- `/sprint` — 冲刺生命周期（`plan|retro|release`）
- `/pre-mortem` — 对 PRD 或发布计划进行事前风险分析
- `/meeting-notes` — 将会议记录总结为结构化笔记
- `/stakeholder-map` — 绘制利益相关者地图并创建沟通计划
- `/write-stories` — 将功能分解为待办事项（`user|job|wwa`）
- `/test-scenarios` — 从用户故事生成测试场景
- `/generate-data` — 创建逼真的虚拟数据集

**示例：**

技能：
- `对于 50 项待办列表，我应该使用哪种优先级排序框架？`
- `为平台迁移项目绘制我们的利益相关者地图`
- `机会分数、ICE 和 RICE 之间有什么区别？`

命令：
- `/write-prd 减少警报疲劳的智能通知系统`
- `/sprint retro — 这是我们上次冲刺的笔记`
- `/write-stories job — 将"团队仪表板"功能分解为工作故事`

</details>

<details>
<summary><strong>4. pm-market-research</strong> — 用户画像、细分、旅程地图、市场规模、竞品分析（7 项技能，3 个命令）</summary>

用户研究和竞争分析：用户画像、细分、旅程地图、市场规模、竞品分析和反馈分析。

**技能（7）：**

- `user-personas` — 从研究数据创建精细的用户画像
- `market-segments` — 识别 3-5 个客户细分，包含人口统计、JTBD 和产品契合度
- `user-segmentation` — 基于行为、JTBD 和需求从反馈数据细分用户
- `customer-journey-map` — 端到端旅程地图，包含阶段、触点、情感和痛点
- `market-sizing` — TAM、SAM、SOM，包含自上而下和自下而上的方法
- `competitor-analysis` — 竞品优势、劣势和差异化机会
- `sentiment-analysis` — 用户反馈的情感分析和主题提取

**命令（3）：**

- `/research-users` — 构建画像、细分用户并绘制客户旅程
- `/competitive-analysis` — 分析竞争格局
- `/analyze-feedback` — 用户反馈的情感分析和细分洞察

**示例：**

技能：
- `估算美国市场 AI 代码审查工具的 TAM/SAM/SOM`
- `为我们的电商结账流程创建客户旅程地图`
- `按行为和需求对这些调查受访者进行细分 [附加 CSV]`

命令：
- `/research-users 我们有来自 12 位健身应用用户的访谈数据`
- `/competitive-analysis 设计工具领域的 Figma 竞品`
- `/analyze-feedback 这是 Q4 的 200 条 NPS 回复 [附加文件]`

</details>

<details>
<summary><strong>5. pm-data-analytics</strong> — SQL 生成、队列分析、A/B 测试分析（3 项技能，3 个命令）</summary>

PM 的数据分析：SQL 查询生成、队列分析和 A/B 测试分析。

**技能（3）：**

- `sql-queries` — 从自然语言生成 SQL（BigQuery、PostgreSQL、MySQL）
- `cohort-analysis` — 按队列的留存曲线、功能采用和参与趋势
- `ab-test-analysis` — 统计显著性、样本量验证和发布/延长/停止建议

**命令（3）：**

- `/write-query` — 从自然语言生成 SQL 查询
- `/analyze-cohorts` — 用户参与数据的队列分析
- `/analyze-test` — 分析 A/B 测试结果

**示例：**

技能：
- `对于 95% 置信度和 2% MDE，我需要多大的样本量？`
- `对于订阅应用，我应该追踪哪些留存指标？`

命令：
- `/write-query 显示 2025 年 Q4 按国家划分的月活跃用户（BigQuery）`
- `/analyze-test 这是我们结账流程 A/B 测试的结果 [附加 CSV]`
- `/analyze-cohorts 1 月 vs 2 月注册用户的周留存率`

</details>

<details>
<summary><strong>6. pm-go-to-market</strong> — 滩头细分市场、ICP、信息传递、增长循环、GTM 动作、战卡（6 项技能，3 个命令）</summary>

市场进入策略：滩头细分市场、理想客户画像、信息传递、增长循环、GTM 动作和竞争战卡。

**技能（6）：**

- `gtm-strategy` — 完整的 GTM 策略：渠道、信息传递、成功指标和发布计划
- `beachhead-segment` — 识别第一个滩头市场细分
- `ideal-customer-profile` — 包含人口统计、行为、JTBD 和需求的 ICP
- `growth-loops` — 设计可持续的增长循环（飞轮）
- `gtm-motions` — 评估 GTM 动作和工具（产品驱动、销售驱动等）
- `competitive-battlecard` — 包含异议处理和获胜策略的销售就绪战卡

**命令（3）：**

- `/plan-launch` — 从滩头到发布计划的完整 GTM 策略
- `/growth-strategy` — 设计增长循环并评估 GTM 动作
- `/battlecard` — 创建竞争战卡

**示例：**

技能：
- `开发者生产力工具的最佳滩头细分市场是什么？`
- `为具有免费增值层的 B2B SaaS 设计增长循环`
- `为 AI 驱动的 HR 筛选平台定义我们的 ICP`

命令：
- `/plan-launch 面向中型工程团队的 AI 代码审查工具`
- `/battlecard 我们的 CRM vs Salesforce 针对 SMB 市场`
- `/growth-strategy 连接自由职业者和创业公司的双边市场`

</details>

<details>
<summary><strong>7. pm-marketing-growth</strong> — 营销创意、定位、价值主张、命名、北极星指标（5 项技能，2 个命令）</summary>

产品营销和增长：营销创意、定位、价值主张陈述、产品命名和北极星指标。

**技能（5）：**

- `marketing-ideas` — 具有渠道和信息传递的创意、高性价比营销创意
- `positioning-ideas` — 与竞品差异化的产品定位
- `value-prop-statements` — 用于营销、销售和入职的价值主张陈述
- `product-name` — 与品牌价值和受众一致的产品名称头脑风暴
- `north-star-metric` — 北极星指标 + 输入指标及业务游戏分类

**命令（2）：**

- `/market-product` — 头脑风暴营销创意、定位、价值主张和产品名称
- `/north-star` — 定义你的北极星指标和支持性输入指标

**示例：**

技能：
- `头脑风暴 5 个与 Notion 差异化的定位角度`
- `双边市场的良好北极星指标是什么？`
- `为我们的销售团队推销文稿生成价值主张陈述`

命令：
- `/market-product 面向电商经理的 B2B 分析仪表板`
- `/north-star 连接自由职业者和客户的双边市场`

</details>

<details>
<summary><strong>8. pm-toolkit</strong> — 简历审查、法律文件、校对（4 项技能，5 个命令）</summary>

核心产品工作之外的 PM 工具：简历审查、法律文件和校对。

**技能（4）：**

- `review-resume` — PM 简历审查和针对 10 项最佳实践的定制（XYZ+S 公式、关键词、结构）
- `draft-nda` — 包含司法管辖区适当条款的保密协议
- `privacy-policy` — 涵盖 GDPR/CCPA 合规的隐私政策
- `grammar-check` — 语法、逻辑和流畅性检查及针对性修复

**命令（5）：**

- `/review-resume` — 全面的 PM 简历审查
- `/tailor-resume` — 针对特定职位描述定制简历
- `/draft-nda` — 起草保密协议
- `/privacy-policy` — 起草隐私政策
- `/proofread` — 检查语法、逻辑和流畅性

**示例：**

技能：
- `根据最佳实践审查我的 PM 简历 [附加 PDF]`
- `检查此产品公告的语法和清晰度`

命令：
- `/review-resume [附加你的 PM 简历]`
- `/tailor-resume [附加简历 + 粘贴职位描述]`
- `/proofread 这是我们 Q1 投资者更新的草稿`

</details>

---

## 关于

这个市场随着产品实践和 AI 能力的发展而演进。

精选技能基于以下专家的工作：

- Teresa Torres — [*Continuous Discovery Habits*](https://www.amazon.com/Continuous-Discovery-Habits-Discover-Products/dp/1736633309/)
- Marty Cagan — [*INSPIRED*](https://www.amazon.com/INSPIRED-Create-Tech-Products-Customers/dp/1119387507/) 和 [*TRANSFORMED*](https://www.amazon.com/dp/1119697336/)
- Alberto Savoia — [*The Right It*](https://www.amazon.com/Right-Many-Ideas-Yours-Succeed/dp/0062884654)
- Dan Olsen — [*The Lean Product Playbook*](https://www.amazon.com/dp/1118960874/)
- Roger L. Martin — [*Playing to Win*](https://www.amazon.com/Playing-Win-Expanded-Bonus-Articles/dp/B0F25SDYWV/)
- Ash Maurya — [*Running Lean*](https://www.amazon.com/dp/B004J4XGN6/)
- Strategyzer — [*Business Model Generation*](https://www.amazon.com/dp/0470876417/) 和 [*Value Proposition Design*](https://www.amazon.com/dp/1118968050/)
