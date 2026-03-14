# Ty Session Cheat Sheet — Demo vs. Transformational Briefing

*Quick reference for Andy during the March 10 session. Pull this up when walking Ty through the vision.*

---

## What We're Showing Him (Demo Tier)

The `ty-morning-briefing` scheduled task runs at 6:30 AM and delivers:

- **Crypto spot prices** — BTC, ETH, SOL, CRO, DOGE, AVAX, LINK via Crypto.com
- **BTC technical snapshot** — 7-day candles, order book depth, bid/ask imbalance
- **Perpetual futures basis** — BTC and ETH perps vs. spot (funding rate signal)
- **Calendar/email/Slack** — pulled from Andy's accounts as proxy
- **"What connecting more sources would unlock"** — teaser section

This is table-stakes aggregation. It replaces five browser tabs, not five hours of judgment.

---

## What He Actually Does Every Morning (From His Survey)

Ty monitors global markets with emphasis on **U.S. macro, traditional financial markets, and digital assets**. He oversees portfolio management across:

- Amphibian Alpha Funds (BTC Alpha, ETH Alpha, USD Alpha)
- Hyla Liquid Venture Fund
- Selected SPVs
- Remaining legacy vehicles

He leads or oversees **direct trading, manager research, investment diligence, portfolio construction, and high-conviction idea generation**. He's constantly on TradingView, CoinMarketCap, and Delphi Digital.

Simultaneously, he's **building the investment platform itself**: data quality, research workflows, portfolio monitoring, risk controls, allocation processes. Current priority: an auditable risk and allocation engine spanning **HRP, mean-variance/Markowitz, market-regime playbooks, and Black-Litterman**.

Operating cadence: weekly/monthly risk limit reviews, portfolio drift monitoring, monthly IC Analytics Packs and Allocation Memos, ongoing manager selection/monitoring/exit decisions, written decision/exception logs.

---

## The Gap

| Dimension | Demo Tier | Transformational Tier |
|---|---|---|
| **Market data** | Spot prices, candles, order book | Regime classification (risk-on/off/transition), cross-asset correlation shifts, macro calendar triggers |
| **Portfolio view** | None — no portfolio data connected | Cross-vehicle exposure synthesis: net BTC beta, manager overlap, drift from target allocation |
| **Risk monitoring** | None | Automated limit checks, breach alerts, exception log drafts |
| **IC cadence** | None | Pre-drafted Analytics Pack inputs, allocation memo scaffolds from position data + market context |
| **Manager research** | None | Research synthesis across Delphi, on-chain data, manager track records; DD pipeline status |
| **Decision support** | "BTC is at $X" | "Given current regime + your drift + your IC schedule, here's what needs attention today" |
| **Platform development** | None | Project tracker pulling from Asana: what's blocking the HRP engine, what shipped last week |
| **Session continuity** | None — every session starts cold | CLAUDE.md provides standing context: who Ty is, fund vehicles, priorities, terminology, preferences. Every session starts with full orientation. |
| **Access control** | Binary: connected or not | Per-tool Allow/Ask/Block permissions on each connector. Granular ring-fencing, not hardware isolation. |

**The one-sentence version:** The demo tells Ty what happened in markets. The transformation tells him what it means for his specific portfolio decisions today.

---

## Multi-Agent Architecture (The Bigger Vision)

One briefing can't do everything. The real system is 3-4 specialized agents, each with different data, cadence, and purpose:

### Agent 1: Pre-Market Briefing (daily, 6:30 AM)
- Market moves overnight + regime signal
- Portfolio drift flags (if connected)
- Calendar prep for today's meetings
- Unanswered messages requiring action
- *Data sources: Crypto.com, Morningstar, FactSet, calendar, email, Slack*

### Agent 2: Portfolio Operations (weekly, Monday AM)
- Cross-vehicle exposure report
- Manager performance vs. benchmarks
- Risk limit utilization
- Rebalancing candidates
- *Data sources: HLV spreadsheet, manager reports, risk models*

### Agent 3: Research Synthesis (on-demand or 2x/week)
- Delphi Digital digest
- On-chain analytics flagged positions
- Earnings/macro events hitting portfolio names
- High-conviction idea pipeline
- *Data sources: Delphi, Aiera, LunarCrush, S&P Capital IQ*

### Agent 4: Platform Development Tracker (weekly)
- Asana project status across the allocation engine build
- Blockers and dependencies
- What shipped, what slipped
- *Data sources: Asana, GitHub (if applicable)*

**Key point for the conversation:** Agent 1 is what we're demoing. Agents 2-4 are what make this transformational. Getting there requires connecting Ty's own data — the HLV spreadsheet, Asana, internal dashboards.

---

## Wednesday Market Overview — Deeper Than It Looks

Ty gives a weekly market overview on the Wednesday team call. Two transcripts (Jan 21, Mar 4) confirm a stable seven-layer structure: regime headline → ETF flows → positioning/liquidation → probabilistic outlook → catalyst of the week → thematic thesis → portfolio spotlight. This is analytical depth that goes well beyond a team update.

**Key questions to ask:**
- "Are you already using ChatGPT to help build the Wednesday overview?" (He uses ChatGPT Pro daily for financial analytics — good odds he is. If so, the pitch shifts from automating a manual process to showing what persistent context + connected data + scheduled cadence does that re-prompting from scratch each week can't.)
- "Is the Wednesday call where this analysis originates, or does it feed into other deliverables too?" (Almost certainly gets repurposed — IC Analytics Packs, allocation memos, LP comms, decision logs. The team call is one outlet. Understanding the full lifecycle of this analysis tells us how many workflows a single prep agent could feed.)
- "If the weekly analysis could be pre-drafted and then sliced into multiple formats — team talking points, IC memo section, LP update paragraph — would that change how you allocate your time?"

**What we could offer:** A Tuesday-night scheduled task that pre-drafts the data-driven sections (regime, flows, positioning, catalyst, portfolio news) in his format, leaving space for his probabilistic outlook and thematic thesis. If the analysis feeds multiple deliverables, the same prep agent could output multiple formats from one data pull.

---

## Discovery Questions for the Session

Ask these after showing the demo to understand what matters most:

**On market intelligence:**
- "What's your first 15 minutes with TradingView actually look like? What signals do you check first?"
- "When you say 'market regime' — what indicators define risk-on vs. risk-off for your portfolio?"
- "Is Delphi your primary crypto research source, or are there others?"

**On portfolio operations:**
- "How often are you pulling up the HLV Portfolio spreadsheet? What are you looking for when you do?"
- "When you review portfolio drift — is that a manual process against target allocations right now?"
- "The IC Analytics Packs — how much time do you spend building those each month?"

**On the allocation engine:**
- "Where are you in the HRP / mean-variance build? Working code, or still in design?"
- "Are the inputs for Black-Litterman views currently manual or sourced from somewhere?"
- "What's the biggest bottleneck in getting the allocation engine to production?"

**On data fragmentation (his stated concern):**
- "You mentioned fragmented data across local and cloud drives. What are the 3-4 sources that should be connected but aren't?"
- "Is there a single 'source of truth' for positions, or are you reconciling across systems?"

**On what "success" looks like:**
- "If this system saved you an hour a day, where would that hour go?"
- "Is the goal to make the existing process faster, or to enable analysis you're not doing at all right now?"

---

## Staged Reveal: The HLV Spreadsheet

**Setup:** Don't open it preemptively. After the demo briefing, say something like:

> "Everything we just saw is using public market data and my accounts as proxy. The real unlock happens when we connect your actual portfolio data. For example — I know you have the HLV Portfolio Management spreadsheet in Drive. If we connected that, the briefing could show you drift from target allocation, manager overlap, and risk limit utilization every morning. Want to pull it up and see what that would look like?"

**If he says yes:** Search Google Drive live, open it, walk through what each tab could feed into which agent.

**If he hesitates:** Totally fine. Walk through the concept using a hypothetical instead. The point is he sees the distance between aggregated market data and synthesized portfolio intelligence.

---

## What We'd Need From Ty to Build the Real System

After the session, if he's bought in, the next steps would be:

1. **CLAUDE.md in each workspace** — we'll build the first one live in the session. This is the single highest-leverage thing: without it, every Cowork session starts from zero. With it, Claude already knows who Ty is, what Amphibian does, his fund vehicles, his priorities, and how he wants to work. Expand it over time as preferences and terminology emerge.
2. **Tool permissions configured** — Allow/Ask/Block per connector per tool. Lets him ring-fence precisely: allow Asana reads, block writes; allow email search, block send. This replaces the hardware-isolation instinct with something granular and real.
3. **Connect his own accounts** — Gmail, Calendar, Slack under his Cowork instance
4. **Connect Asana** — for platform development tracking
5. **Evaluate the HLV spreadsheet** — determine sensitivity, decide what's safe to connect
6. **Identify the 2-3 additional data sources** that would have the highest impact (likely Morningstar + one of Aiera/FactSet/LunarCrush)
7. **Define his risk limits and target allocations** — so the system knows what "drift" means
8. **Pick a cadence** — which agents, which days, what time

---

*Created: March 9, 2026*
