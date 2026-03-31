---
name: prioritization-frameworks
description: "9种优先级排序框架参考指南，包含公式、使用场景指导和模板 — RICE、ICE、Kano、MoSCoW、机会评分等。用于选择优先级排序方法、比较框架（如RICE vs ICE），或学习不同优先级排序方法的工作原理。"
---

## 优先级排序框架参考指南

帮助您根据具体情境选择和应用合适优先级排序框架的参考指南。

### 核心原则

绝不要让客户设计解决方案。优先排序**问题（机会）**，而非功能。

### 机会评分（Opportunity Score，Dan Olsen，《精益产品管理手册》）

推荐用于对客户问题进行优先级排序的框架。

针对每个需求调查客户的**重要性**和**满意度**（归一化为0-1量表）。

三个相关公式：
- **当前价值** = 重要性 × 满意度
- **机会评分** = 重要性 × (1 − 满意度)
- **创造的客户价值** = 重要性 × (S2 − S1)，其中 S1 = 改善前满意度，S2 = 改善后满意度

高重要性 + 低满意度 = 最高机会评分 = 最佳机会。在重要性vs满意度图表上绘制 — 左上象限是最佳区域。优先排序客户问题，而非解决方案。

### ICE框架

适用于对计划和想法进行优先级排序。不仅考虑价值，还考虑风险和经济因素。

- **I**（Impact，影响）= 机会评分 × 受影响客户数量
- **C**（Confidence，置信度）= 我们有多大把握？（1-10分）。用于考虑风险。
- **E**（Ease，易用性）= 实施难度有多大？（1-10分）。用于考虑经济因素。

**评分** = I × C × E。分数越高 = 优先级越高。

### RICE框架

将ICE框架的影响因素拆分为两个独立因素。适用于需要更精细度的大型团队。

- **R**（Reach，触达范围）= 受影响客户数量
- **I**（Impact，影响）= 机会评分（每位客户的价值）
- **C**（Confidence，置信度）= 我们有多大把握？（0-100%）
- **E**（Effort，工作量）= 实施需要多少工作量？（人月）

**评分** = (R × I × C) / E

### 9种框架概览

| 框架 | 最适用于 | 核心洞察 |
|-----------|----------|-------------|
| 艾森豪威尔矩阵 | 个人任务 | 紧急vs重要 — 用于个人PM任务管理 |
| 影响vs工作量 | 任务/计划 | 简单2×2 — 快速分诊，不适合战略决策的严谨分析 |
| 风险vs回报 | 计划 | 类似影响vs工作量，但考虑了不确定性 |
| **机会评分** | 客户问题 | **推荐。** 重要性 × (1 − 满意度)。归一化为0-1。 |
| Kano模型 | 理解期望 | 必备型、期望型、魅力型、无差异型、反向型。用于理解，而非优先级排序。 |
| 加权决策矩阵 | 多因素决策 | 为标准分配权重，对每个选项评分。有助于获得利益相关者支持。 |
| **ICE** | 想法/计划 | 影响力 × 置信度 × 易用性。推荐用于快速优先级排序。 |
| **RICE** | 大规模想法 | (触达范围 × 影响力 × 置信度) / 工作量。在ICE基础上增加了触达范围。 |
| MoSCoW | 需求 | 必须/应该/可以/不做。注意：源自项目管理领域。 |

### 模板

- [机会评分介绍（PDF）](https://drive.google.com/file/d/1ENbYPmk1i1AKO7UnfyTuULL5GucTVufW/view)
- [重要性vs满意度模板 — Dan Olsen（Google Slides）](https://docs.google.com/presentation/d/1jg-LuF_3QHsf6f1nE1f98i4C0aulnRNMOO1jftgti8M/edit#slide=id.g796641d975_0_3)
- [ICE模板（Google Sheets）](https://docs.google.com/spreadsheets/d/1LUfnsPolhZgm7X2oij-7EUe0CJT-Dwr-/edit?usp=share_link&ouid=111307342557889008106&rtpof=true&sd=true)
- [RICE模板（Google Sheets）](https://docs.google.com/spreadsheets/d/1S-6QpyOz5MCrV7B67LUWdZkAzn38Eahv/edit?usp=sharing&ouid=111307342557889008106&rtpof=true&sd=true)

---

### 延伸阅读

- [产品管理框架大全 + 模板](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [Kano模型：如何让客户满意而不成为功能工厂](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [持续产品发现大师课（CPDM）](https://www.productcompass.pm/p/cpdm)（视频课程）
