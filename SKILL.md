---
name: software-stock-analysis
description: "Produce software-equity research in three coordinated modules: fund flows and market positioning, industry analysis, and company deep dives. Use for complete software-sector reports, peer comparisons, earnings reviews, KPI interpretation, investment theses, and monitoring frameworks; do not use for software engineering or product architecture reviews."
---

# Software Stock Analysis

Produce evidence-based software-equity research that separates capital flows, industry structure, and company fundamentals. A complete report has exactly three main parts: **fund flows**, **industry analysis**, and **company deep dive**. Avoid choosing the comparison set after seeing the result.

## Select the report mode

- **Complete report:** When the user asks for a full report, sector report, investment report, or does not narrow the scope, run all three parts in order.
- **Single module:** When the user explicitly asks for fund flows, industry analysis, or a company deep dive, run only that module and do not pad the answer with the other two.
- **Document-led review:** When the user supplies only one company's earnings release, filing, or investor presentation, default to Part 3. State that Parts 1 and 2 were not run unless the user asks to add current market and industry evidence.
- **Mixed scope:** When the user requests two modules, preserve their report order and identify the omitted module.

An executive summary, methodology note, source list, and final monitoring checklist may sit outside the three parts. They do not count as additional report parts.

## Start with the research design

Before collecting performance or company results, state:

- the as-of date and analysis horizon;
- the company, subsector, and geographic scope;
- the benchmark and peer-selection rule;
- whether the task concerns monitoring, earnings review, comparative research, or a full investment thesis.

Choose peers by buyer, product category, revenue model, scale, and growth stage. Do not add or remove peers merely because their subsequent returns support a conclusion. If the user supplies a universe, preserve it unless a security is demonstrably out of scope; disclose any change.

## Route by report part

Read only the references needed for the request:

- **Part 1 - Fund flows:** Read [references/market-positioning.md](references/market-positioning.md). Use it for ETF flows, relative strength, breadth, short positioning, options, and crowding.
- **Part 2 - Industry analysis:** Read [references/subsectors.md](references/subsectors.md) and the relevant sections of [references/business-models.md](references/business-models.md). Read [references/metrics.md](references/metrics.md) when building an industry KPI or peer table.
- **Part 3 - Company deep dive:** Read [references/metrics.md](references/metrics.md), [references/business-models.md](references/business-models.md), and [references/moat-and-risks.md](references/moat-and-risks.md). Also read the company's relevant subsector section in [references/subsectors.md](references/subsectors.md).

## Three-part research workflow

### Part 1 - Fund flows and market positioning

1. Define the software basket, subsector proxies, benchmark, horizon, and return convention before observing performance.
2. Measure ETF creations or redemptions, flow relative to AUM, persistence, and concentration. Do not describe trading volume or AUM appreciation as fund inflow.
3. Compare absolute and relative returns, cap-weighted and equal-weighted performance, breadth, and contribution concentration.
4. Add short interest, borrow, options, and crowding evidence where available, preserving reporting lags.
5. Conclude whether the market shows broad participation, concentrated leadership, de-risking, short covering, or insufficient evidence.

### Part 2 - Industry analysis

1. Define the subsector and peer universe before comparing outcomes. Select peers by buyer, product mission, revenue model, scale, and geography.
2. Map the demand environment: customer budget, adoption cycle, regulation, infrastructure shifts, and major technology transitions.
3. Compare business models, pricing units, contract structures, gross-margin intensity, revenue visibility, and natural expansion mechanisms.
4. Build a normalized industry dashboard using only comparable KPI definitions and periods.
5. Assess competitive structure: platform vendors, specialists, open source, self-build, bundling, channel power, and likely sources of commoditization.
6. Identify which industry indicators are accelerating, decelerating, or merely changing mix; then define the subsector monitoring list.

### Part 3 - Company deep dive

1. Map the company's product, economic buyer, pricing unit, contract duration, renewal mechanism, expansion driver, and revenue-recognition lag.
2. Build an operating dashboard. Distinguish reported, company-defined, derived, consensus, and analyst-estimated values.
3. Test growth quality by separating new customers, expansion, price, usage, acquisitions, and foreign exchange where possible. Pair growth with gross margin, operating leverage, free cash flow, stock-based compensation, and dilution.
4. Evaluate moat and failure modes using observable evidence for workflow depth, switching costs, data, distribution, integration, and ecosystem effects. Treat feature breadth and AI branding as claims, not moats.
5. Value the company in context. Match the multiple to its revenue model and maturity; reconcile enterprise value inputs and the market-price date.
6. Form bear, base, and bull scenarios with explicit operating assumptions and identify the next disclosures that would confirm or falsify each case.

## Evidence and calculation rules

- Prefer regulatory filings, investor-relations materials, earnings-call transcripts, and official fund or exchange data. Use secondary sources for context, not as the sole support for company-reported KPIs.
- Attach source, reporting period, publication date, currency, and whether a figure is GAAP or non-GAAP. Cite links when available.
- Never silently equate ARR with revenue, bookings with billings, RPO with backlog, or NRR with customer retention. Preserve each company's definition.
- Do not manufacture missing KPIs. Mark them `not disclosed`; if estimating, show the formula, assumptions, and range.
- Reconcile fiscal versus calendar periods, quarterly versus trailing-twelve-month figures, acquisitions, divestitures, and constant-currency adjustments.
- Treat stock-based compensation and diluted share growth as economic costs even when presenting non-GAAP margins.
- Present financial analysis as conditional research, not certainty or personalized investment advice.

## Default complete-report output

Start with **scope and comparison design** and a short **executive summary**, then use these three main sections without inserting a fourth main analytical section:

### Part 1 - Fund flows

- Market regime and software-sector risk appetite.
- ETF flows normalized by AUM and checked against shares outstanding.
- Absolute and relative strength versus stated benchmarks.
- Breadth, leadership concentration, short positioning, options, and crowding.
- Positioning conclusion and the indicators that would change it.

### Part 2 - Industry analysis

- Subsector definition, peer-selection rule, and industry map.
- Demand drivers, customer budgets, adoption cycle, and technology or regulatory changes.
- Business-model and pricing-model comparison.
- Normalized peer KPI table.
- Competitive structure, bundling, self-build, open-source, and commoditization risks.
- Industry outlook, leading indicators, and preferred or vulnerable business profiles. Do not turn this into an unexplained stock ranking.

### Part 3 - Company deep dive

- Company positioning and revenue engine.
- Operating KPI dashboard and growth-quality bridge.
- Profitability, cash conversion, stock-based compensation, and dilution.
- Product, workflow depth, moat evidence, counterevidence, and risk register.
- Valuation, bear/base/bull scenarios, catalysts, and falsifiable monitoring indicators.

Finish with **sources, caveats, and a consolidated monitoring checklist**. Primary sources come first; estimates and unavailable data remain clearly labeled.

For a single-module task, use the corresponding section structure without pretending that the complete three-part report was produced.

Use the user's language. Prefer compact tables for comparable metrics and prose for causal interpretation. Avoid composite scores unless their components and weights are transparent.

