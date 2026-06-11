---
name: stock-research-sop
description: >-
  Create structured stock research workflows, prompts, checklists, and monitoring tables for A-share or equity ideas using a four-stage process: monthly chokepoint screening, quarterly financial review, pre-buy red-team falsification, and holding-period milestone monitoring. Use when the user asks to analyze a stock idea, turn influencer screenshots/notes into an investing SOP, generate AI prompts for stock screening, review companies around BOM localization or国产替代, or build a repeatable equity research checklist. This skill supports research organization only and must not present outputs as investment advice.
---

# Stock Research SOP

## Purpose

Use this skill to turn raw stock ideas, screenshots, notes, company names, or sector themes into a repeatable research workflow. Keep outputs decision-oriented: what to screen, what evidence to verify, what could falsify the thesis, and what events would trigger continued holding, caution, or exit.

Always include a brief note that the output is research organization, not investment advice.

## Default Workflow

Use the four-stage workflow unless the user requests only one stage.

1. Monthly screening: find chokepoint opportunities.
2. Quarterly review: verify financial delivery.
3. Pre-buy red team: falsify the thesis before entry.
4. Holding monitoring: track milestones and failure thresholds.

If the input is only screenshots or rough notes, first extract the explicit rules, thresholds, and workflow sequence. Then rewrite them as a clean Markdown SOP with prompts and tables.

## Stage 1: Monthly Chokepoint Screening

Goal: shrink a large sector into a focused candidate pool of companies in scarce, high-leverage supply-chain links.

Prioritize candidates with these traits:

- BOM or supply-chain link with low domestic substitution.
- Domestic localization rate below 20% when the user provides or asks for that threshold.
- Cost share below 5%, but high impact on yield, performance, delivery, certification, or customer expansion.
- Capacity expansion cycle longer than 18 months.
- Specialized or niche leaders such as 专精特新 or 单项冠军 companies.
- Market cap roughly 30-150 billion RMB when following the original rule.

Prompt template:

```text
请基于【行业/产品/赛道】的 BOM 清单，逆向拆解国产化率低、成本占比小但对性能、良率、交付或扩产影响大的关键卡脖子环节。

请优先筛选国产化率低于 20%、成本占比低于 5%、扩产周期超过 18 个月的环节，并寻找具备专精特新或单项冠军属性、当前市值约 30 亿-150 亿的 A 股公司。

请输出：环节名称、技术壁垒、国产化率、成本占比、扩产周期、代表公司、市值、关注理由、主要风险、需要进一步验证的证据。
```

## Stage 2: Quarterly Financial Review

Goal: test whether the thesis is being confirmed by financial statements, not only by narrative.

Review at least the latest four quarters when data is available:

- Gross margin direction and whether improvement is driven by core business.
- Revenue, order, inventory, contract liability, receivables, and cash flow consistency.
- CapEx, construction in progress, fixed assets, and capacity progress.
- Private placement or fundraising use of proceeds, especially whether it funds the relevant chokepoint.
- Research-report crowding: flag names with heavy recent coverage, such as more than 15 reports in the past 3 months if that threshold is used.

Prompt template:

```text
请审计【公司名称/股票代码】最近 4 个季度财报，判断其毛利率改善是否由主营业务驱动，而不是会计口径、产品结构短期变化或非经常性因素造成。

请重点分析收入、毛利率、存货、合同负债、应收账款、经营现金流、CapEx、在建工程、固定资产和定增投向是否支持其卡脖子环节的真实扩产或渗透率提升。

如果该公司近 3 个月研报数量超过 15 篇，请标记为交易拥挤并降低优先级。请输出财务验证结论、证据、反证和下一步跟踪项。
```

## Stage 3: Pre-Buy Red-Team Falsification

Goal: assume the long thesis is wrong and search for the strongest disconfirming evidence before any entry decision.

Check these risks:

- Major customer has internal R&D or substitution plans.
- Major customer is introducing a second supplier.
- The current solution could be replaced or cancelled within 18 months.
- Competitors can start a price war or capacity race.
- Certification, reliability, yield, or customer qualification barriers are weaker than claimed.
- The stock is already priced for perfect execution.

Prompt template:

```text
请扮演极度苛刻的空头研究员，对【公司名称/股票代码】的投资逻辑做路径证伪。

请逐项审查：大客户是否有自研计划，是否引入第二供应商，现有技术在未来 18 个月是否可能被替代或需求被取消，同行是否具备打价格战能力，当前估值是否已透支预期。

请给出证据来源、风险等级、触发条件、需要回避的情形，以及如果仍要跟踪，必须验证的关键证据。
```

## Stage 4: Holding Monitoring

Goal: convert the thesis into observable milestones so the logic can be updated or stopped.

For each target company, build a milestone table:

- List three hard milestones over the next two quarters.
- Prefer concrete events: sample delivery, certification, pilot order, mass production, capacity ramp, customer import, design win, tender result, or order confirmation.
- Set the latest acceptable date for each milestone.
- Define the verification source: exchange announcement, annual/interim report, investor Q&A, customer disclosure, supplier chain evidence, or third-party industry data.
- Define a failure threshold. If the milestone is not confirmed by the deadline, mark the thesis as weakened or invalid.

Prompt template:

```text
请为【公司名称/股票代码】列出未来 2 个季度最关键的 3 个硬核里程碑，例如打样、送样、认证、量产、投产、客户导入、设计定点或订单落地。

请为每个里程碑设置最晚完成时限、可验证信息源、确认方式和熔断阈值。如果公告、财报、互动易、客户侧信息或供应链信息无法在时限内确认，请标记为逻辑弱化或逻辑失效，并给出持有、观察或退出建议。
```

## Output Formats

For a full SOP, use this structure:

```markdown
# 标题

> 仅作研究流程整理，不构成投资建议。

## 一句话总结

## 核心框架

| 阶段 | 目标 | 关键动作 | 输出 |
|---|---|---|---|

## 1. 月度初筛
## 2. 季度复审
## 3. 买前终审
## 4. 持股监控
## 最终输出表格模板
## 执行节奏
## 关键提醒
```

For company-level research, use this table:

| 公司 | 代码 | 卡脖子环节 | 国产化率 | 成本占比 | 扩产周期 | 财务验证 | 空头风险 | 未来里程碑 | 熔断阈值 | 结论 |
|---|---|---|---|---|---|---|---|---|---|---|

For milestone monitoring, use this table:

| 公司 | 里程碑 | 最晚时限 | 验证来源 | 确认方式 | 未兑现含义 | 动作 |
|---|---|---|---|---|---|---|

## Evidence Discipline

When live or current facts matter, verify with current sources before making claims about:

- Market cap, latest financials, analyst coverage count, or recent announcements.
- Customer plans, supplier qualification, order progress, or product milestones.
- Laws, exchange rules, or financial-reporting details.

Separate evidence from inference:

- Use "已验证" for facts directly supported by sources.
- Use "推断" for reasoned conclusions.
- Use "待验证" for claims that require source checking.

Avoid unsupported recommendations. Prefer labels such as "值得跟踪", "需要验证", "风险较高", "逻辑弱化", or "逻辑失效" unless the user explicitly asks for portfolio actions and adequate evidence is available.
