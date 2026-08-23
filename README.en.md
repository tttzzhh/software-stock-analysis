# Software Stock Analysis

**Language: [中文](README.zh-CN.md) | English**

A Codex skill for evidence-based software-equity research. A complete report contains three coordinated modules:

1. **Fund flows and market positioning** — determine whether capital is entering the sector, whether participation is broad, and whether short covering or crowding is driving price action.
2. **Industry analysis** — examine demand, business models, competitive structure, subsector KPIs, and structural risks.
3. **Company deep dive** — analyze the revenue engine, growth quality, profitability, cash conversion, moat, valuation, and failure modes.

The governing principle is simple: **define the scope, comparison set, benchmark, horizon, and metric definitions before examining the outcome**. This reduces hindsight-driven peer selection and interval cherry-picking.

> This project provides a research framework. It is not personalized investment advice and does not replace verification against original disclosures.

## Use cases

- Complete software-sector or subsector reports;
- ETF flows, relative strength, breadth, short positioning, options, and crowding monitors;
- Cybersecurity, data-platform, enterprise-workflow, advertising, and transaction-platform research;
- Earnings releases, filings, investor presentations, and earnings-call reviews;
- Peer comparisons, KPI normalization, business-model analysis, valuation, and monitoring frameworks.

It is not intended for software engineering, product architecture, or code review.

## Report modes

| Mode | Trigger | Default output |
|---|---|---|
| Complete report | A sector, investment, or full report is requested | Run all three modules in order |
| Single module | The user explicitly requests one module | Run only that module |
| Document-led review | Only one company's earnings or investor document is supplied | Default to the company deep dive and disclose that Parts 1 and 2 were not run |
| Mixed scope | Two modules are requested | Preserve their original report order and identify the omitted module |

An executive summary, methodology note, source list, and monitoring checklist may sit outside the three analytical parts without becoming additional modules.

## Fix the research design first

Before collecting returns, flows, or company results, state:

- the as-of date and analysis horizon;
- the company, subsector, and geographic scope;
- the benchmark, ETF, and peer-selection rule;
- whether returns are price or total returns;
- whether the task is monitoring, earnings review, peer comparison, or a full thesis.

Select peers by economic buyer, product mission, revenue model, scale, growth stage, and geography. Preserve a user-supplied universe unless a security is demonstrably out of scope, and disclose every change.

## Part 1: Fund flows and market positioning

This module keeps **market positioning** separate from **fundamental business quality**.

### 1. Universe, benchmark, and windows

- Define the software basket, subsector proxies, and constituent rules;
- Compare cap-weighted and equal-weighted performance;
- Use a broad-market and a growth benchmark, such as SPY and QQQ;
- Examine short-, medium-, and long-term windows instead of one favorable interval;
- Before treating an ETF as sector evidence, review its index methodology, concentration, rebalancing, and constituent history.

### 2. Returns and risk

- Interval return: `ending value / starting value - 1`;
- Relative return: `sector return - benchmark return`;
- For longer periods, also inspect the `sector index / benchmark index` ratio;
- Drawdown: `current value / running peak - 1`;
- Maximum drawdown: the minimum of the drawdown series;
- Annualized daily volatility: sample standard deviation of daily returns × `sqrt(252)`.

Do not call simple benchmark outperformance “alpha.” When beta-adjusted residual performance is needed, state the estimation method and window.

### 3. Breadth and concentration

Measure the share of constituents:

- above their 20-, 50-, and 200-day moving averages;
- making 20-day or 52-week highs and lows;
- producing positive returns over the selected window;
- contributing to aggregate basket performance.

Strong cap-weighted performance alongside weak equal-weighted returns and breadth indicates **concentrated leadership**, not broad sector strength.

### 4. ETF flows

Prefer primary fund, exchange, or shares-outstanding data. Separate:

- net creations and redemptions;
- AUM changes caused by price appreciation or depreciation;
- secondary-market trading volume;
- fund-level flow from capital flows into the underlying companies.

Report absolute flow, flow as a percentage of beginning AUM, persistence, and concentration across funds. **Trading volume is not a net inflow.**

### 5. Shorts, options, and crowding

- Short interest as a percentage of float, days to cover, and changes by reporting period;
- borrow fees and utilization when reliable data is available;
- do not substitute daily short-sale volume for outstanding short interest;
- put/call activity, implied versus realized volatility, skew, term structure, and strike concentration;
- crowding evidence from flows, narrow leadership, valuation percentiles, ownership concentration, and recent short covering.

Conclude with one of four labels: **broad participation, concentrated leadership, de-risking, or insufficient evidence**. State the next observations that would change the conclusion.

See [`references/market-positioning.md`](references/market-positioning.md).

## Part 2: Industry analysis

### 1. Subsector map

Classify companies by economic buyer, product function, data flow, and revenue model—not by marketing language.

| Subsector | Key indicators | Principal risks |
|---|---|---|
| Cybersecurity | ARR, NRR, module adoption, large customers, RPO, incident history | Platform bundling, breaches, open source, tool fatigue, data-processing cost |
| Data platforms | Consumption, commitments, workloads, data volume, net expansion | Hyperscalers, open source, optimization, unit-price declines, architecture shifts |
| Enterprise workflow | Seats, modules, renewal, RPO/cRPO, implementation duration | Suite consolidation, long deployment, shelfware, AI-driven seat pressure |
| Advertising and transaction platforms | Ad spend or gross volume, take rate, active customers, loss rates | Cyclicality, privacy, rate compression, fraud, regulation |

Analyze material segments separately for diversified companies and disclose where business mix weakens direct comparability. See [`references/subsectors.md`](references/subsectors.md).

### 2. Business models

Identify the revenue engine before interpreting growth or valuation.

| Model | Revenue framework | Natural expansion | Main risk |
|---|---|---|---|
| Seat subscription | paid seats × realized price × recognized contract fraction | customers, seats, modules, pricing | hiring cycles, shelfware, bundling |
| Usage or consumption | customers × activity × realized unit price | workloads, data, API calls, compute | optimization, price declines, migration |
| Transaction or volume | gross volume × take rate + fixed fees | payments, ad spend, transaction volume | macro cycles, mix, regulation, rate compression |
| Outcome based | verified outcomes × realized fee | revenue generated, cost saved, successful resolutions | attribution disputes, recognition delays, volatility |

For hybrids, decompose growth into customer additions, expansion or contraction, price and packaging, usage or volume, mix, acquisitions, and foreign exchange. See [`references/business-models.md`](references/business-models.md).

### 3. Peer selection and industry dashboard

Prefer peers with similar buyers, missions, pricing units, contract duration, gross-margin and infrastructure intensity, scale, growth stage, and geography.

Do not place high-margin seat software, infrastructure-heavy consumption platforms, and transaction businesses in one unexplained valuation ranking. Cross-subsector comparisons should normalize for growth, gross margin, free cash flow, dilution, cyclicality, and revenue visibility.

The industry conclusion should explain whether demand is accelerating, decelerating, or merely changing mix; whether competitive power is shifting toward platforms, specialists, open source, or self-build; and which leading indicators would validate that view.

## Part 3: Company deep dive

### 1. Positioning and revenue engine

Map the product, economic buyer, pricing unit, contract duration, renewal mechanism, expansion driver, and revenue-recognition lag. Analyze each material revenue stream separately for hybrid models.

### 2. KPIs and growth quality

| Metric | Main use | Common trap |
|---|---|---|
| ARR / MRR | Period-end recurring-revenue scale | Non-GAAP; ARR is not automatically quarterly revenue × 4 |
| NRR / NDR / DBNER | Expansion, contraction, and churn within the starting cohort | Cohort, period, FX, and acquisition definitions differ |
| GRR / logo retention | Retention floor and customer durability | Strong NRR can coexist with high small-customer churn |
| Bookings / ACV / TCV | Contracted commercial activity | Term length, renewals, and cancellation rights distort comparison |
| Billings | Billing and cash timing | Multiyear prepayments and seasonality can dominate quarterly changes |
| RPO / cRPO | Contracted revenue and near-term visibility | Not the same as backlog; may exclude cancellable or usage spend |
| Rule of 40 | Growth rate + profitability margin for the same period | State whether the margin is GAAP operating, adjusted operating, or FCF |

Mark every field as **reported, company-defined, derived, consensus, analyst estimate, or not disclosed**. Never replace a missing value with zero.

Where possible, bridge growth through new customers, expansion or contraction, price and packaging, usage or transaction volume, acquisitions, and foreign exchange. Pair growth with gross margins, GAAP and non-GAAP operating margins, free cash flow, deferred revenue, capitalized commissions, stock-based compensation, and diluted-share growth.

See [`references/metrics.md`](references/metrics.md).

### 3. Moat and failure modes

A moat requires observable evidence. Market share, feature count, and AI branding are not sufficient by themselves. Test:

- whether the product is a system of record or system of action;
- whether permissions, audit, governance, or compliance depend on it;
- the depth of upstream and downstream integrations and embedded business rules;
- cross-functional collaboration, history, and habitual use;
- switching costs from migration, retraining, downtime, and regulatory validation.

Also assess self-build and open-source substitution, platform bundling, commoditization and AI, cloud costs, implementation duration, customer concentration, security and compliance, acquisitions, and changing KPI definitions.

The risk register should contain mechanism, probability, impact, leading indicator, counterevidence, and time horizon. Grade moat claims as **well evidenced, partially evidenced, unproven, or deteriorating** rather than assigning an unexplained score.

See [`references/moat-and-risks.md`](references/moat-and-risks.md).

### 4. Valuation, scenarios, and monitoring

- Match valuation multiples to the revenue model and maturity;
- reconcile the market-price date, net cash or debt, and enterprise value;
- build explicit bear, base, and bull assumptions for revenue, margins, cash flow, and valuation;
- identify the next disclosure that would confirm or falsify each case;
- separate short-term catalysts from durable fundamental change.

## Evidence and calculation rules

- Prefer regulatory filings, investor-relations materials, earnings calls, and official fund or exchange data;
- retain the source, reporting period, publication date, currency, and GAAP/non-GAAP status for every figure;
- never conflate ARR, revenue, bookings, billings, RPO, backlog, and deferred revenue;
- do not invent undisclosed KPIs; show formulas, assumptions, and ranges for estimates;
- reconcile fiscal and calendar periods, quarterly and TTM figures, acquisitions, divestitures, FX, and constant-currency claims;
- treat stock-based compensation and dilution as economic costs;
- disclose missing data, reporting lags, and definition changes.

## Default complete-report structure

```text
Scope and comparison design
Executive summary

Part 1 - Fund flows
  Market regime → ETF flows → relative strength → breadth and concentration
  → shorts/options/crowding → positioning conclusion

Part 2 - Industry analysis
  Subsector definition → demand → business models → normalized peer KPIs
  → competitive structure → outlook and leading indicators

Part 3 - Company deep dive
  Positioning → revenue engine → KPIs and growth quality → profitability and cash
  → moat and risks → valuation and scenarios → catalysts and falsification tests

Sources and limitations
Consolidated monitoring checklist
```

## Repository structure

```text
software-stock-analysis/
├── SKILL.md
├── README.zh-CN.md
├── README.en.md
├── agents/
│   └── openai.yaml
└── references/
    ├── business-models.md
    ├── market-positioning.md
    ├── metrics.md
    ├── moat-and-risks.md
    └── subsectors.md
```

`SKILL.md` contains mode selection, the core workflow, evidence rules, and output structure. Supporting references are loaded only when their module is relevant.

## Installation

```powershell
git clone https://github.com/tttzzhh/software-stock-analysis.git "$env:USERPROFILE\.codex\skills\software-stock-analysis"
```

If a skill with the same name already exists, back it up or update it instead of overwriting unsaved changes.

## Usage examples

Complete report:

```text
Use $software-stock-analysis to produce a complete cybersecurity-software report.
Cover fund flows, industry analysis, and company deep dives on CRWD, PANW, and ZS.
Fix the period, benchmarks, and peer-selection rule before examining results.
```

Earnings review:

```text
Use $software-stock-analysis to analyze this earnings release.
Focus on ARR, NRR, RPO, Rule of 40, stock-based compensation, dilution,
and guidance changes. Separate reported, derived, and estimated values.
```

Fund-flow module only:

```text
Use $software-stock-analysis only for software-sector fund flows and positioning.
Compare cap-weighted and equal-weighted performance and examine ETF creations,
breadth, short positioning, options, and crowding.
```

## Output quality checklist

- Was the universe, benchmark, and horizon fixed before viewing results?
- Were ETF price appreciation and trading volume kept separate from net flows?
- Are reported, company-defined, derived, consensus, and estimated values labeled?
- Are periods, FX, acquisitions, and GAAP/non-GAAP definitions aligned?
- Are stock-based compensation and dilution treated as economic costs?
- Does every moat claim include evidence and counterevidence?
- Are bear, base, and bull assumptions falsifiable?
- Are missing data and the next conclusion-changing indicators disclosed?

## Disclaimer

This skill organizes public information, normalizes definitions, and improves research traceability. Outputs may be affected by data quality, reporting lags, changing company definitions, and model judgment. Nothing in this repository constitutes a securities recommendation, return guarantee, or personalized investment advice.
