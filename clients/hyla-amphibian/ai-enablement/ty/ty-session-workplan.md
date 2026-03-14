# Ty Session — Monday Prep Work Plan
*4 hours, starting 1pm Monday March 9. Session: Tuesday March 10, 9:00 AM, 90 minutes.*

---

## What the Survey Tells Us (Read This First)

Ty is **not a beginner**. He's a daily ChatGPT Pro power user doing research, financial analytics, document creation, and Python/Cursor coding. He's on **Max plan** and has already opened Cowork. This changes the session from "let me introduce you to AI" to **"let me show you what Cowork does that ChatGPT can't, and make sure you're doing it safely."**

**His morning is the demo target.** He monitors global markets across TradingView, Coinmarketcap, Delphi, and various research outlets. He oversees portfolio management across Amphibian Alpha Funds (BTC Alpha, ETH Alpha, USD Alpha), Hyla Liquid Venture Fund, SPVs, and legacy vehicles. He does direct trading, manager research, investment diligence, portfolio construction. All of this lives in fragmented tools — email, Drive, Slack, Granola, Asana, Telegram. The synthesis is manual. That's the pain point.

**His success definition (his exact words):** "Low friction setup that enables me to move quickly and productively without too many speedbumps while still being protected with backups or a safe operating infrastructure. I would like to 'leapfrog' classic missteps and implement quick productivity boosters and plugins that supercharge my workflow."

**His concerns (his exact words):** "Contamination or destruction of important files — security leaks. Fragmented / incomplete data sources across local and various cloud drives."

**Translation:** He wants speed with guardrails. Lead with guardrails briefly, spend most of the time on speed.

---

## Connector Strategy — What Ty Should Pre-Connect

**Send Ty a Slack message tonight (draft below) asking him to connect these before the session.** Every connector he has live before 9 AM means more time spent on results and less on permission prompts.

### Financial Services Plugins (CONFIRMED WORKING on Max plan)

Anthropic has dedicated financial services plugins. **Recommended install path — direct links** (one click each, no GitHub dependency):

- [Financial Analysis](https://claude.com/plugins/financial-analysis) (core — install first)
- [Private Equity](https://claude.com/plugins/private-equity)
- [Equity Research](https://claude.com/plugins/equity-research)

Alternative: GitHub marketplace (Customize → Browse plugins → Personal → Add marketplace from GitHub → `https://github.com/anthropics/financial-services-plugins`). Installs all plugins at once but can fail on the first attempt. The direct links are more reliable for a pre-session setup where you won't be there to troubleshoot.

**Plugins to install for Ty:**

| Plugin | What It Does | Relevance to Ty |
|---|---|---|
| **Financial Analysis** (core, install first) | Comps, DCF, LBO, 3-statement models, spreadsheet auditing, data cleaning. Bundles MCP connectors for major financial data providers. | Foundation — install this first |
| **Private Equity** | Deal sourcing, due diligence checklists, IC memos, KPI monitoring, returns analysis, value creation plans | **Direct hit** — maps to his daily work |
| **Equity Research** | Earnings analysis, coverage reports, morning notes, catalyst tracking, investment idea screening, thesis tracking | Relevant for manager research and market monitoring |

Lower priority (don't ask Ty to pre-install):

| Plugin | Notes |
|---|---|
| **Investment Banking** | CIMs, teasers, merger modeling. Less relevant unless doing deal work. |
| **Wealth Management** | Client meeting prep, portfolio rebalancing. Lower priority for a fund GP. |
| **LSEG** (partner) | FX, bonds, derivatives, interest rate curves. Relevant for macro but secondary. |
| **S&P Global** (partner) | Broad financial data and analytics. Heavy — explore after basics are solid. |

The core Financial Analysis plugin bundles connectors for: Daloopa, Morningstar, S&P Global, FactSet, Moody's, MT Newswires, Aiera, LSEG, PitchBook, Chronograph, and Egnyte. **Important: installing the plugin does NOT auto-enable these connectors.** After plugin install, Ty needs to go to the connectors panel (puzzle piece icon) and manually enable/authorize each bundled connector he wants active. They'll appear in his connector list after the plugin is installed, but they start disabled.

Skills trigger automatically based on the request (e.g., "run a comps analysis on X" fires the comps skill, "draft an IC memo for Y" fires the IC memo skill). They can also be invoked explicitly.

Sources: [Financial Analysis Plugin](https://claude.com/plugins/financial-analysis) · [Private Equity Plugin](https://claude.com/plugins/private-equity) · [Equity Research Plugin](https://claude.com/plugins/equity-research) · [Install financial services plugins](https://support.claude.com/en/articles/13851150-install-financial-services-plugins-for-cowork) · [Financial Services Skills](https://support.claude.com/en/articles/12663107-claude-for-financial-services-skills)

---

### Pre-connect (ask him tonight):

| Connector | Why | Notes |
|---|---|---|
| Gmail | Foundation for every demo — email triage, meeting prep, morning briefing | He's probably already done this |
| Google Calendar | Meeting prep brief needs it, daily briefing needs it | Quick setup |
| Google Drive | Cross-source synthesis, accessing fund docs and research | Enables "what do we know about X across everything" |
| Slack | Team activity digest, overnight messages, internal context | Daily tool for him |
| Granola | Meeting notes synthesis — connects prior conversations to future meetings | Check if Cowork has a Granola connector; if not, note as gap |
| Crypto.com | **Live BTC/ETH prices and market data in his morning briefing** | This is what makes the briefing demo land — real-time portfolio-relevant market data flowing into the same brief as his email and calendar |
| Asana | Task management integration, project tracking | He listed it twice in the survey — clearly core to his workflow |

### Explore during or after session:

| Connector | Why | Notes |
|---|---|---|
| Moody's | Credit opinions, sector outlooks, entity peer analysis | Directly relevant to manager research and investment diligence |
| Morningstar | Investment insights, analyst research, fund holdings, screener | Core for manager selection workflow |
| Aiera | **Earnings intelligence and market analysis** | Earnings monitoring, relevant for manager research — new find from FS docs |
| Daloopa | **SEC filings and operational KPIs for 3,500+ public companies** | Research workflow — new find from FS docs |
| MT Newswires | Real-time financial news feed | Could feed morning briefing |
| LunarCrush | Crypto social sentiment data | Relevant for BTC/ETH alpha work — monitors social signal |
| PitchBook | VC/PE deal data | Relevant for Hyla Liquid Venture Fund |
| S&P Global | Broad financial data (22+ endpoints) | Heavy tool, worth exploring once basics are solid |
| Chronograph | PE/VC portfolio management and analytics | Potentially relevant for Hyla's fund structure |
| Egnyte | Data room management | Could partially fill the Docusign/Docsend gap |

### Not available (be upfront):

- **Docusign** — no connector. Drive docs as proxy for document workflows.
- **Docsend** — no connector. Same.
- **Telegram** — no connector. Flag as a gap.
- **TradingView** — no connector. Crypto.com covers the real-time price data need.

---

## The 4-Hour Prep Block

### Block 1: Get Your Own House in Order (1:00–2:15)

You haven't set up email, calendar, or daily briefs in your own Cowork. Fix that now — you need hands-on experience with the mechanics before you walk Ty through them.

**Do these in order:**

1. **Test the Financial Services plugin marketplace first.** In Cowork: Customize → Browse plugins → Personal → Add marketplace from GitHub → enter `https://github.com/anthropics/financial-services-plugins`. Try installing the core Financial Analysis plugin. If it works on your Max plan, this is a game-changer for the session. If it's gated, you know before you promise Ty anything.

2. **Connect Gmail, Google Calendar, and Slack** in your Cowork instance. Walk through the permission prompts yourself so you know exactly what Ty will see.

3. **Test the meeting prep brief workflow.** Ask Cowork to pull your calendar for tomorrow (Tuesday), grab email context for each meeting, and generate a prep brief. Note what's good, what's thin, what needs a better prompt.

4. **Build a scheduled daily briefing.** This is the centerpiece of the session. Set up a morning briefing task on your own data. You won't have the financial connectors, but you'll learn the scheduled task mechanics — how to write the prompt, set the schedule, trigger a test run, and see the output. That's what matters.

5. **If time permits, connect Crypto.com** (public market data, no account required beyond the connector auth). See what the tools return. `get_tickers` and `get_candlestick` should give you a feel for the data structure.

### Block 2: Build Ty-Specific Demo Assets (2:15–3:15)

Now that you've felt the connectors, build the demo material tailored to his world.

**1. The Daily Briefing Prompt (the centerpiece)**

This is the scheduled task you'll build with Ty during the session. Draft and refine the prompt now so you're not writing it live. The briefing pulls from every connected source to replace his manual morning synthesis.

Draft prompt for Ty's daily briefing:

```
Generate my morning briefing for today.

## Market Pulse
Pull current BTC and ETH prices and overnight price action via Crypto.com.
Flag any moves greater than 3% in either direction. Note current levels
relative to recent ranges.

## Attention Required
Search my Gmail from the last 12 hours. Surface messages that need a
response or flag a risk event, prioritized by urgency. Categories to
watch for: LP communications, fund administrator notices, manager
updates, legal/compliance, and anything mentioning NAV, redemption,
capital call, or risk.

## Today's Meetings
Pull my calendar for today. For each meeting:
- Who am I meeting with?
- What's the most recent email thread with each attendee?
- Any relevant Granola notes from prior meetings with them?
- One line on what this meeting likely needs from me.

## Portfolio & Research Watch
Check my email and Drive for anything touching: Amphibian Alpha Funds
(BTC Alpha, ETH Alpha, USD Alpha), Hyla Liquid Venture Fund, active
SPVs, or managers currently in diligence. Surface updates, not
summaries of old information.

## Team Activity
Pull overnight Slack messages from Hyla channels. What did the team
discuss? Any decisions or questions pending my input?

## Asana
Flag any tasks assigned to me that are due today or overdue.

Keep the entire briefing to one page. Lead with what needs action.
```

This prompt will need tuning after the first few runs — Ty will know which sections are useful and which are noise. The point is that the *infrastructure* is live and pulls from real sources. Version 1 doesn't need to be perfect; it needs to be real.

**2. Meeting Prep Brief (backup/secondary demo)**

Simpler, proven pattern. Prep a clean prompt that pulls tomorrow's calendar, finds email threads with each attendee, surfaces prior Granola notes, and synthesizes into a one-page brief per meeting. Use this if the full briefing demo hits a snag, or as a second workflow to show.

**3. Research Synthesis Proof of Concept**

Ty spends significant time on manager research and investment diligence. A prompt like "What do we know about [manager X] across email, Drive, Slack, and meeting notes?" shows cross-source synthesis on his actual data. Even rough output proves a workflow that currently takes hours of manual cross-referencing.

**4. Financial Connector Demo Prompts**

If Moody's or Morningstar are connected during the session, have ready:
- "Pull the credit opinion summary and sector outlook for [entity Ty cares about]" (Moody's)
- "What does Morningstar say about [fund/manager Ty is evaluating]?" (Morningstar)
- "Show me the analyst research on [sector]" (Morningstar)

These are quick hits that show the connectors working. You don't need to build a full workflow around them — just demonstrate that institutional-grade data is queryable conversationally.

### Block 3: Session Run of Show + Security Brief (3:15–4:15)

**Revised 90-Minute Session Structure**

Given that Ty is NOT a beginner, the session should be rebalanced:

```
0:00–0:10  Context & Security Quick-Check (10 min)
           - He's on Max — confirm training opt-out is off. Show him
             the toggle. This takes 30 seconds and addresses his
             "security leaks" concern directly.
           - Sandbox architecture in one sentence: "Cowork runs in an
             isolated VM. It can't touch your files unless you explicitly
             save something to your workspace folder."
           - Consumer vs. commercial terms: Max is consumer terms.
             Training opt-out is the critical control. Mention it,
             confirm it's set, move on.
           - Verify his pre-connected connectors are live. Check that
             the FS plugin bundled connectors (Moody's, Morningstar, etc.)
             are enabled, not just installed. Troubleshoot anything that
             didn't take. If he didn't pre-connect, do Gmail + Calendar +
             Crypto.com now (fastest path to the demo).

0:10–0:40  The Daily Briefing — Build It Live (30 min)
           This is the centerpiece. You're not showing a demo — you're
           building his actual morning briefing together.

           - Open with: "Let's build the thing that replaces your
             manual morning synthesis."
           - Walk through the briefing prompt section by section.
             Show him what each section pulls from (Gmail, Calendar,
             Crypto.com, Slack, Drive, Granola, Asana). He sees the
             connectors doing real work, not an abstract explanation.
           - Trigger a test run on his live data. He watches his own
             email, his own calendar, live BTC/ETH prices, his own
             Slack messages synthesize into a structured brief.
           - Set up the scheduled task together. Pick a time
             (6:30 AM? 7:00 AM? His call). He'll have this waiting
             for him Wednesday morning.
           - Iterate on the prompt together. "Is this section useful?
             Would you want this organized differently? What's missing?"
             This is collaborative, not a performance.

           The briefing demo does triple duty:
           1. Shows connectors working on real data (wow)
           2. Produces a scheduled task he'll actually use (sticky)
           3. Teaches him how prompts work by building one together
              (transferable skill)

0:40–0:55  Second Workflow — Financial Skills or Research Synthesis (15 min)
           Follow his energy from the briefing block.

           **If FS plugins work:** This is where they shine. Ask Ty to
           pick something from his current work — a company he's
           evaluating, a manager in diligence, an upcoming IC memo.
           Then show the relevant skill firing: "Run a comps analysis
           on [company]" or "Draft an IC memo for [investment]" or
           "Pull the earnings analysis on [company]." Purpose-built
           financial skills running on institutional data connectors.

           **If FS plugins don't work:** Fall back to individual
           connectors. "Pull the credit opinion on [entity]" (Moody's),
           "What does Morningstar say about [fund]?" (Morningstar).
           Or do a research synthesis query across email + Drive + notes
           for a topic he cares about.

0:55–1:10  His Agenda — Workflow Gaps & Tools (15 min)
           Let him drive. He'll have questions. Likely topics:
           - Asana integration (connected? show it)
           - Docusign/Docsend (no connectors — be upfront, show
             Drive-based document workflows as alternative)
           - Telegram (no connector — flag as gap)
           - His Python/Cursor coding workflow and how Claude Code
             relates (mention, don't go deep)
           - Anything from his ChatGPT usage he wants to replicate

1:10–1:25  Handoff & Next Steps (15 min)
           - Give him the prompt cheat sheet (tailored to his use cases)
           - Confirm the scheduled briefing is live for Wednesday AM
           - "Week 1" daily practice: use the briefing, ask follow-up
             questions from it, build one new prompt per day
           - Additional connectors to explore on his own: Moody's,
             Morningstar, MT Newswires, LunarCrush, PitchBook
             (give him the list)
           - Plant the team-level seed naturally: "Once you're
             comfortable, the next conversation is doing this across
             the firm"
           - Ask: what surprised you? What do you want more of?
           - Get verbal OK to use his feedback for refining the offering
```

**Security Brief Template (Skeletal)**

Don't build the full template today. Build the outline so you can fill it in *during* the session as you configure his setup. Sections:

1. Plan & Privacy Configuration (Max, training opt-out status, retention policy)
2. Connectors Enabled (which ones, what each can access)
3. Data Exposure Profile (what types of data are now flowing to Anthropic)
4. Ring-Fencing Level (your 4-level framework — where Ty lands)
5. Recommendations (what's safe to connect next, what to hold off on, firm-level considerations)
6. Open Questions (things to revisit with Hoppin / the broader firm)

### Block 4: Rehearse & Contingency (4:15–5:00)

**Dry run the wow moment.** Open Cowork, connect to your email/calendar, and run the meeting prep brief prompt. Time it. Note any awkward pauses, permission prompts, or slow responses. The demo needs to feel effortless.

**Prepare fallback demos.** If a connector fails, if the output is thin, if something times out — have a backup. Options:
- Pre-generated example output you can show ("here's what this looks like when it's running on a full dataset")
- A second workflow ready to go (email triage instead of meeting prep)
- The file system demo: show Cowork reading and writing local files. This is tangible and always works.

**Confirm logistics:**
- [ ] Is the meeting on your calendar? (Didn't see it on your Hyla calendar)
- [ ] Zoom/Google Meet link?
- [ ] Screen sharing plan — you sharing, or him sharing, or both?
- [ ] Record the session? (Need his permission)

**Prepare your own notes template.** A simple doc to fill in during/after the session:
- What landed (specific moments)
- What fell flat
- Questions he asked that I didn't anticipate
- His exact words about what was valuable (future testimonial material)
- Follow-up items promised

---

## The Investment Domain: What You Can and Can't Do

You're right that you don't need to be a portfolio manager. Here's the line:

**You CAN demo:** Research synthesis across his email/Drive/notes, morning intelligence briefings, meeting prep, email triage, document drafting, workflow automation. These are domain-agnostic patterns that happen to run on his financial data.

**You CAN'T (and shouldn't) demo:** Portfolio optimization, HRP implementation, Black-Litterman modeling, risk analytics. That's his domain expertise, not yours.

**The bridge:** Show him that Cowork can be a research and synthesis assistant for investment work — pulling relevant information together, drafting IC memos from notes, summarizing manager research. Then say: "The quantitative portfolio work you described — the HRP, the allocation engine — that's a deeper engagement. Cowork can help with the analytical workflow, but building that out properly is a separate conversation." This plants the seed for a follow-on without pretending you're a quant.

---

## Quick Reference: What Ty Said → What You Demo

| His Words | Your Demo |
|---|---|
| "monitor global markets… various research outlets" | Daily briefing with live Crypto.com data + email + news |
| "fragmented / incomplete data sources across local and various cloud drives" | Briefing pulling from Gmail + Drive + Slack + Granola + Asana in one output |
| "low friction setup… move quickly" | Pre-connected connectors, straight into building workflows |
| "leapfrog classic missteps" | Security config done right from day 1, scheduled task live by end of session |
| "quick productivity boosters and plugins" | Crypto.com, Moody's, Morningstar connectors + scheduled daily briefing |
| "contamination or destruction of important files" | Sandbox architecture — one sentence, move on |
| "ChatGPT Pro daily — research, analytics, documents" | Everything ChatGPT does + connectors + scheduled tasks + file system |

---

## Slack Message to Ty (Send Tonight)

```
Hey Ty — looking forward to tomorrow. To make the most of our 90 minutes,
would you mind setting up a few things in Cowork before we start?
Four things, roughly 15 min total:

1. CONNECTORS — open Cowork → click the connectors icon (puzzle piece,
bottom left) → connect these and authorize the permissions:
• Gmail
• Google Calendar
• Google Drive
• Slack
• Asana
• Crypto.com (real-time market data — search for it in the directory)

2. FINANCIAL SERVICES PLUGINS — Anthropic has purpose-built finance
plugins with skills for comps, DCF, IC memos, due diligence, earnings
analysis, and more. Click each link and hit install:

• Financial Analysis (core — install first): https://claude.com/plugins/financial-analysis
• Private Equity: https://claude.com/plugins/private-equity
• Equity Research: https://claude.com/plugins/equity-research

3. ENABLE THE BUNDLED CONNECTORS — after you install the Financial
Analysis plugin, go back to the connectors panel (puzzle piece icon).
You'll see new data sources that appeared: Moody's, Morningstar,
FactSet, PitchBook, S&P Global, and others. They start disabled — click
into any that look useful and authorize them. We'll explore these
together tomorrow, but having a few enabled ahead of time saves us
setup time.

4. PRIVACY — go to Settings → Privacy → make sure "Allow training on my
data" is toggled OFF. Single most important security setting on the
platform. We'll walk through why tomorrow.

If anything gives you trouble, no worries — we'll sort it out together.
But every connector you have live before 9 means more time building
actual workflows.

See you at 9.
```

---

*Created: March 9, 2026, 1:00 PM. Updated: March 9, 2026 — added connector strategy, revised session flow around daily briefing, added Slack message draft. Latest: clarified plugin connectors need manual enabling, switched to direct install links, updated Slack message to 4-step setup.*
