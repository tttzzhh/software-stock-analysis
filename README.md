# Software Stock Analysis

**语言：中文｜[English](README.en.md)**

面向 Codex 的软件股研究 Skill。完整报告固定由三部分组成：

1. **资金流向与市场定位**：资金是否真正进入软件板块、行情是否具有广度、空头和拥挤度如何；
2. **行业分析**：需求、商业模式、竞争结构和子行业指标如何变化；
3. **个股深度分析**：收入引擎、增长质量、盈利与现金、护城河、风险和估值。

核心原则是：**先定义研究范围、比较对象和指标口径，再观察结果**，避免事后选择区间或同业来倒推结论。

> 本项目提供研究框架，不构成个性化投资建议，也不替代对原始披露文件的核验。

## 适用场景

- 软件板块或子行业完整报告；
- ETF 资金流、相对强弱、市场广度、空头与拥挤度监控；
- 网络安全、数据平台、企业工作流、广告与交易平台研究；
- 软件公司财报、年报、投资者演示文稿与电话会拆解；
- 同业比较、KPI 校准、商业模式比较、估值和监控框架。

不用于软件工程、产品架构或代码审查。

## 报告模式

| 模式 | 触发方式 | 默认输出 |
|---|---|---|
| 完整报告 | 要求板块报告、完整报告或投资报告 | 依次运行三个部分 |
| 单模块 | 明确只要资金流、行业或个股分析 | 只运行指定模块 |
| 财报驱动 | 只提供一家公司的财报或公告 | 默认运行个股深度分析，并注明未运行前两部分 |
| 混合范围 | 指定其中两个模块 | 保持原顺序，并说明省略的模块 |

执行摘要、方法说明、来源和监控清单可以放在三部分之外，但不应成为新的主分析模块。

## 研究开始前：固定设计

在收集收益、资金流或公司数据之前，先声明：

- 数据截止日和分析区间；
- 公司、子行业与地域范围；
- 基准、ETF 和同业选择规则；
- 使用价格收益还是总收益；
- 任务属于监控、财报复盘、同业比较还是完整投资研究。

同业依据经济买方、产品任务、收入模式、规模、成长阶段和地域选择。用户已经指定股票池时，原则上保留；确需调整时必须说明原因。

## Part 1：资金流向与市场定位

这一部分把**交易状态**与**基本面质量**分开。

### 1. 股票池、基准与窗口

- 定义软件篮子、子行业代理和成分规则；
- 同时观察市值加权与等权结果；
- 使用宽基和成长基准，例如 SPY 与 QQQ；
- 同时观察短、中、长期窗口，避免用单个有利区间定义市场状态；
- ETF 作为板块代理时，检查指数方法、持仓集中度、再平衡和成分变化。

### 2. 收益与风险

- 区间收益率：`期末值 / 期初值 - 1`；
- 相对收益：`板块收益率 - 基准收益率`；
- 中长期同时观察 `板块指数 / 基准指数`；
- 回撤：`当前值 / 历史峰值 - 1`；
- 最大回撤：回撤序列的最小值；
- 年化日波动率：日收益率样本标准差 × `sqrt(252)`。

简单跑赢基准不能直接称为 Alpha；需要时应说明 Beta 调整方法和估计窗口。

### 3. 广度与集中度

跟踪成分股中：

- 位于 20、50、200 日均线以上的比例；
- 创 20 日或 52 周新高、新低的比例；
- 指定区间取得正收益的比例；
- 对板块总收益的贡献集中度。

市值加权很强、但等权和广度很弱，应解释为**集中式领涨**，而非板块全面走强。

### 4. ETF 资金流

优先使用基金公司、交易所或 shares outstanding 数据，区分：

- 申购赎回形成的真实净流入/净流出；
- AUM 因价格变化产生的被动变化；
- 二级市场成交量；
- ETF 层面资金流与成分公司资本流。

报告绝对资金流、相对期初 AUM 比例、持续性和基金间集中度。**成交量不是资金净流入。**

### 5. 空头、期权和拥挤度

- 空头占流通股比例、days to cover、报告期变化；
- 有可靠数据时加入借券费率和利用率；
- 不把每日卖空成交量等同于未平仓空头；
- 观察 Put/Call、隐含/实际波动率、偏度、期限结构和关键行权价；
- 结合资金流、领导集中度、估值分位、机构持仓与空头变化判断拥挤度。

结论使用：**广泛参与、集中式领涨、去风险、证据不足**，并列出会改变判断的下一组数据。

详见 [`references/market-positioning.md`](references/market-positioning.md)。

## Part 2：行业分析

### 1. 子行业框架

按经济买方、产品功能、数据流和收入模式分类，而不是按营销话术分类。

| 子行业 | 重点指标 | 主要风险 |
|---|---|---|
| 网络安全 | ARR、NRR、模块采用、大客户、RPO、事件记录 | 平台捆绑、安全事故、开源、工具疲劳、数据成本 |
| 数据平台 | 使用量、承诺消费、工作负载、数据量、净扩张 | 云厂商、开源、优化周期、单位价格、架构迁移 |
| 企业工作流 | 席位、模块、续约、RPO/cRPO、实施周期 | 套件整合、部署过长、闲置席位、AI 压缩席位 |
| 广告与交易平台 | 广告支出/交易总额、take rate、活跃客户、损失率 | 周期性、隐私、费率压缩、欺诈和监管 |

多业务公司应拆分重要业务线，并说明业务混合如何削弱直接可比性。详见 [`references/subsectors.md`](references/subsectors.md)。

### 2. 商业模式

| 模式 | 收入框架 | 自然扩张 | 核心风险 |
|---|---|---|---|
| 席位订阅 | 付费席位 × 实现单价 × 确认比例 | 客户、席位、模块、提价 | 招聘放缓、闲置席位、捆绑 |
| 使用量/消费 | 客户 × 活动量 × 单位价格 | 工作负载、数据、API、算力 | 优化、单位价格下降、迁移 |
| 交易量 | 交易总额 × take rate + 固定费 | 支付、广告、交易量 | 宏观、渠道组合、监管、费率压缩 |
| 结果收费 | 可验证结果 × 实现费率 | 收入提升、成本节省、成功处理量 | 归因争议、确认滞后、收入波动 |

混合模式需要拆分：新增客户、扩张/收缩、价格与包装、用量/交易量、业务组合、并购和汇率。详见 [`references/business-models.md`](references/business-models.md)。

### 3. 同业选择与行业仪表盘

优先选择具有相近经济买方、产品任务、定价单位、合同期限、毛利与基础设施强度、规模、成长阶段和地域的公司。

不要把高毛利席位软件、基础设施密集型消费平台和交易型公司放进没有解释的估值排名。跨子行业比较时，至少校准增长、毛利率、自由现金流、稀释、周期性和收入可见度。

行业结论应回答：需求在加速、减速还是仅发生组合变化；竞争优势正向平台、专业厂商、开源还是客户自建迁移；哪些指标能最早验证判断。

## Part 3：个股深度分析

### 1. 公司定位与收入引擎

明确产品、经济买方、定价单位、合同期限、续约机制、扩张来源和收入确认滞后。混合模式要分别分析重要收入流。

### 2. KPI 与增长质量

| 指标 | 用途 | 常见误区 |
|---|---|---|
| ARR / MRR | 观察期末经常性收入 | 非 GAAP；不能默认 ARR = 单季收入 × 4 |
| NRR / NDR / DBNER | 衡量原有客户扩张、收缩和流失 | 队列、期间、汇率和并购口径可能不同 |
| GRR / Logo retention | 收入留存底线与客户留存 | 强 NRR 可能掩盖小客户流失 |
| Bookings / ACV / TCV | 合同活动 | 合同期限、续约和取消条款影响比较 |
| Billings | 开票和现金时点 | 多年预付与季节性会扭曲季度变化 |
| RPO / cRPO | 合同收入与近 12 个月可见度 | 不等于 backlog，可能排除可取消或用量收入 |
| Rule of 40 | 同期增长率 + 利润率 | 必须说明 GAAP、调整后利润率或 FCF margin |

每个字段标注为：**公司披露、公司自定义、推导、一致预期、分析估计、未披露**。缺失值不能填成零。

增长质量尽量拆成新增客户、原有客户扩张/收缩、提价与包装、使用量/交易量、并购和汇率；并结合毛利率、GAAP/non-GAAP 经营利润率、自由现金流、递延收入、资本化佣金、股权激励和稀释后股数判断。

详见 [`references/metrics.md`](references/metrics.md)。

### 3. 护城河与失败路径

护城河必须有可观察证据，不由市场份额、功能数量或 AI 标签自动推导。检查：

- 是否成为 system of record 或 system of action；
- 权限、审计、治理与合规是否依赖产品；
- 上下游集成和定制业务规则的深度；
- 多部门协作、历史数据与使用习惯；
- 数据迁移、培训、停机和监管验证形成的切换成本。

同时评估自建与开源、平台捆绑、商品化与 AI、云成本、实施周期、客户集中、安全合规、并购和 KPI 定义变化。

风险表包含：风险机制、概率、影响、领先指标、反证和时间范围。护城河结论使用**证据充分、部分有证据、尚未证明、正在恶化**，避免无依据的数字评分。

详见 [`references/moat-and-risks.md`](references/moat-and-risks.md)。

### 4. 估值、情景和监控

- 按收入模式与成熟度选择估值倍数；
- 对齐市场价格日期、净现金/净负债和企业价值；
- 建立 Bear / Base / Bull 情景，写明收入、利润率、现金流与估值假设；
- 给出会证实或证伪各情景的下一项披露；
- 将短期催化剂与可持续基本面变化分开。

## 证据与计算规则

- 优先使用监管文件、投资者关系材料、电话会和官方基金/交易所数据；
- 每个数字保留来源、报告期、发布日期、币种和 GAAP/non-GAAP 属性；
- 不混淆 ARR、收入、bookings、billings、RPO、backlog 与 deferred revenue；
- 不编造未披露 KPI；估算必须给出公式、假设和区间；
- 对齐财年/自然年、季度/TTM、并购、剥离、汇率和恒定汇率口径；
- 把股权激励和稀释视为经济成本；
- 明确标注数据缺口、报告滞后和定义变化。

## 默认完整报告结构

```text
研究范围与比较设计
执行摘要

Part 1 - 资金流向
  市场状态 → ETF 资金流 → 相对强弱 → 广度与集中度
  → 空头/期权/拥挤度 → 定位结论

Part 2 - 行业分析
  子行业定义 → 需求驱动 → 商业模式 → 同业 KPI
  → 竞争结构 → 行业展望与领先指标

Part 3 - 个股深度分析
  公司定位 → 收入引擎 → KPI 与增长质量 → 盈利和现金
  → 护城河与风险 → 估值与三情景 → 催化剂和证伪条件

来源与限制
综合监控清单
```

## 目录结构

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

`SKILL.md` 负责模式选择、研究流程和输出规则；`references/` 只在对应模块需要时读取。

## 安装

```powershell
git clone https://github.com/tttzzhh/software-stock-analysis.git "$env:USERPROFILE\.codex\skills\software-stock-analysis"
```

如果已有同名 Skill，请先备份或更新，避免覆盖未保存的修改。

## 使用示例

完整报告：

```text
使用 $software-stock-analysis，对网络安全软件板块做完整报告。
包括资金流向、行业分析，以及 CRWD、PANW、ZS 的个股深度分析。
先固定比较区间、基准和同业选择规则。
```

财报拆解：

```text
使用 $software-stock-analysis 分析这份财报。
重点检查 ARR、NRR、RPO、Rule of 40、股权激励、稀释和指引变化，
区分公司披露、推导数据与分析估计。
```

资金流模块：

```text
使用 $software-stock-analysis，只做软件板块资金流向与市场定位。
比较市值加权和等权表现，检查 ETF 申购赎回、广度、空头与拥挤度。
```

## 输出质量检查

- 是否在查看结果前固定股票池、基准和区间；
- 是否把 ETF 价格上涨误写成资金净流入；
- 是否区分披露、公司定义、推导、一致预期和估计；
- 是否对齐期间、汇率、并购与 GAAP/non-GAAP 口径；
- 是否把股权激励和稀释纳入经济分析；
- 是否为护城河同时提供证据与反证；
- 是否为三种情景写出可证伪假设；
- 是否列出数据缺口和会改变结论的下一项指标。

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


## 免责声明

本 Skill 用于组织公开信息、统一口径和提高研究可复核性。输出可能受到数据质量、披露滞后、公司定义变化和模型判断误差影响，不构成证券推荐、收益承诺或针对个人情况的投资建议。
