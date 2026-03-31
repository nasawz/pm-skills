---
name: metrics-dashboard
description: "定义和设计产品指标仪表板，包含关键指标、数据源、可视化类型和告警阈值。适用于创建指标仪表板、定义KPI、设置产品分析或构建数据监控计划。"
---

## 产品指标仪表板

设计一个综合的产品指标仪表板，包含恰当的指标、可视化图表和告警阈值。

### 背景

您正在为 **$ARGUMENTS** 设计指标仪表板。

如果用户提供了文件（现有仪表板、分析数据、OKR或战略文档），请先阅读这些文件。

### 领域背景

**指标 vs KPI vs 北极星指标**：指标 = 所有可衡量的事物。KPI = 少数在较长时间内追踪的关键量化指标。北极星指标（North Star Metric）= 单一以客户为中心的KPI，是业务成功的领先指标。

**好指标的4个标准**（Ben Yoskovitz，《精益分析》）：（1）可理解 — 创造共同语言。（2）可比较 — 基于时间维度，而非快照。（3）比率或速率 — 比整数更能揭示真相。（4）改变行为 — 黄金法则："如果一个指标不会改变你的行为，那它就是一个坏指标。"

**8种指标类型**：虚荣指标 vs 可行动指标（只有可行动指标才能改变行为），定性 vs 定量（WHAT vs WHY — 两者都需要；永远不要停止与客户对话），探索性 vs 汇报性（探索数据以发现意外洞察），滞后 vs 领先（领先指标实现更快的学习周期，例如客户投诉预测流失）。

**5个行动步骤**：（1）对照4个好指标标准审查指标。（2）更新仪表板 — 确保所有关键指标都是好指标。（3）识别虚荣指标 — 谨慎使用它们。（4）分类领先指标和滞后指标。（5）选择一个问题并深入挖掘数据。

案例研究和更多详情参见：Ben Yoskovitz的 [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)（英文）

### 指导步骤

1. **确定指标框架** — 将指标分层组织：

   **北极星指标**：最能体现核心价值交付的单一指标

   **输入指标**（3-5个）：驱动北极星指标的杠杆

   **健康指标**：确保产品整体健康的护栏

   **业务指标**：收入、成本和单位经济效益

2. **为每个指标定义**：

   | 指标 | 定义 | 数据源 | 可视化 | 目标 | 告警阈值 |
   |---|---|---|---|---|---|
   | [名称] | [精确计算：分子/分母，时间窗口] | [数据来源] | [折线图 / 柱状图 / 数字 / 漏斗图] | [目标值] | [何时触发告警] |

3. **设计仪表板布局**：

   ```
   ┌─────────────────────────────────────────────┐
   │  北极星：[指标] — [当前值]                   │
   │  趋势：[↑/↓ X% vs 上周期]                    │
   ├──────────────────┬──────────────────────────┤
   │  输入指标 1      │  输入指标 2               │
   │  [迷你图]        │  [迷你图]                 │
   ├──────────────────┼──────────────────────────┤
   │  输入指标 3      │  输入指标 4               │
   │  [迷你图]        │  [迷你图]                 │
   ├──────────────────┴──────────────────────────┤
   │  健康：[延迟] [错误率] [NPS]                │
   ├─────────────────────────────────────────────┤
   │  业务：[MRR] [CAC] [LTV] [流失率]           │
   └─────────────────────────────────────────────┘
   ```

4. **设定审查节奏**：
   - **每日**：运营健康（错误、延迟、关键流程）
   - **每周**：输入指标和参与度趋势
   - **每月**：北极星指标、业务指标、OKR进展
   - **每季度**：战略审查和指标重新校准

5. **定义告警**：
   - 什么阈值会触发调查？
   - 谁收到告警以及通过什么渠道？
   - 预期的响应时间是多少？

6. **根据用户背景推荐工具**：
   - Amplitude、Mixpanel、PostHog 用于产品分析
   - Looker、Metabase、Mode 用于基于SQL的仪表板
   - Datadog、Grafana 用于运营健康监控

逐步思考。将仪表板规范保存为markdown文档。

---

### 延伸阅读

- [The Ultimate List of Product Metrics](https://www.productcompass.pm/p/the-ultimate-list-of-product-metrics)（英文）
- [The North Star Framework 101](https://www.productcompass.pm/p/the-north-star-framework-101)（英文）
- [The Product Analytics Playbook: AARRR, HEART, Cohorts & Funnels for PMs](https://www.productcompass.pm/p/the-product-analytics-playbook-aarrr)（英文）
- [AARRR (Pirate) Metrics: The 5-Stage Framework for Growth](https://www.productcompass.pm/p/aarrr-pirate-metrics)（英文）
- [The Google HEART Framework: Your Guide to Measuring User-Centric Success](https://www.productcompass.pm/p/the-google-heart-framework)（英文）
- [Funnel Analysis 101: How to Track and Optimize Your User Journey](https://www.productcompass.pm/p/funnel-analysis)（英文）
- [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)（英文）
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (video course)（英文视频课程）
