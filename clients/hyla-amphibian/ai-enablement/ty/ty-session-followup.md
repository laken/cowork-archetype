# Session 1 Follow-Up — AI Enablement Assessment
### Andy Laken → Ty Shinn | March 10, 2026

---

## What We Covered

**Security & Workspace Architecture**
We spent real time here,  it's the foundation for everything else. The key points we walked through:

- **VM sandbox model** — Cowork runs a full Linux VM on your Mac with hardware-level isolation. It can only see folders you explicitly grant access to, per session. When the session ends, the VM resets. The one-sentence version: "a clean room with one filing cabinet you chose."
- **Connector permissions** — each connected service (Gmail, Google Drive, Asana, etc.) has individual tool-level controls: Allow, Ask, or Block for each action. We showed this live with your Gmail connector. You control what Claude can read, write, and draft — per service, per action.
- **Privacy settings** — confirmed your Max plan, walked through the training opt-out toggle and 30-day retention window. Consumer terms apply (Max is consumer, not enterprise). You confirmed opt-out is enabled — your conversations won't be used for training, and data retention is limited to 30 days.
- **Google Drive** — confirmed read-only access live. No write or delete capability through the connector. Pending: connect Amphibian, multiple Drive accts.
- **External site access** — the VM's network is locked to an allowlist (Anthropic API, package managers). Set it to ask you for permission for each external site.
- **Prompt injection** — acknowledged the real risk and evolving defenses. This is an area to stay aware of, not a solved problem.
- **Cloud storage** — discussed iCloud, OneDrive, Google Drive, and Dropbox as backup/sync options. Multiple Google accounts and drive fragmentation came up as a real issue for your setup.
- **Machine must be awake** — scheduled tasks only fire when the Mac is awake and the Claude desktop app is open. KeepingYouAwake (free Mac menu bar app) prevents sleep: [keepingyouawake.app](https://keepingyouawake.app/)

**Context Files (CLAUDE.md)**
We discussed how Cowork has zero memory between sessions and how CLAUDE.md and about-me files solve this. You mentioned you already have an "about me" file you built with ChatGPT — that's directly transferable. We looked at examples of context files, writing voice files, and workspace structure, but didn't build one live together. That's a high-priority item for next session.

**Morning Briefing Demo**
Showed the `ty-morning-briefing` scheduled task output — market regime classification, technical context, and portfolio-relevant signals. Your feedback was valuable: this feels like "more noise" rather than a productivity boost. You want to build trust incrementally, not delegate wholesale to a daily AI report you haven't learned to trust yet. Reshapes how we sequence everything going forward.

**Risk Limit Review Output**
Showed the weekly risk limit review report using a demo portfolio that mirrors your fund structure — including Hyla Liquid Venture's manager universe (Pythagoras, CMCC, CoinFund, Autonomous, VanEck, Contango, Skycatcher, ZeroKnowledge, etc.) with stub NAV values. The Alpha fund positions used live Crypto.com prices. You noticed the allocations and asked where they came from — confirmed these were demo amounts with real manager names, not your actual data.

**HLV Spreadsheet Discussion**
We discussed connecting your actual HLV Portfolio Management spreadsheet from Google Drive and weighed the pros and cons. The key finding: currently the Google Drive connector is read-only — Claude can read spreadsheet data but cannot modify, or delete anything in your Drive. This directly addresses your file contamination concern.

Suggestes a workflow for creating/altering documents in Drive - have cowork create as .docx files and upload to drive manually.

We didn't get as far as actually connecting it live and walking through the individual tabs, but the security question that would have blocked that step is resolved.

---

## What We Didn't Get To

**Building your CLAUDE.md together**
This is the single highest-leverage setup step and should be first on the agenda for session 2. You've already done significant groundwork here — your ChatGPT memory export and the contextual profile you built from it cover your identity, career context, projects, and working preferences in detail. Potential goal for session 2 is to restructure that material into Claude's CLAUDE.md format, strip anything ChatGPT-specific, and add the Cowork-specific context (connected tools, file access patterns, privacy settings, your fund vehicles and current priorities) so every session starts with that context loaded instead of from scratch. If you're willing, send me your current about-me.md before session 2 — I can do the initial restructuring ahead of time so we spend session time refining rather than reformatting.

**Portfolio Drift Monitoring**
Companion to the risk limit review you already saw. Computes drift from target allocations across all four fund vehicles, classifies severity, and calculates exact dollar trades needed to rebalance. The risk review tells you "are limits breached?" — the drift monitor tells you "how far off-target am I and what trades fix it?"

**HLV Spreadsheet — Live Connection**
We discussed the spreadsheet and confirmed the Drive connector is read-only (no corruption risk), but didn't get to actually pulling it into a session and walking through the tabs. That's the next step: connect it live, identify which tabs contain position data, target allocations, and risk limits, and wire those into the risk and drift tasks so they run against your real numbers instead of demo data. The scheduled tasks would then output a formatted risk dashboard before your week starts — using live positions and your actual limits.

**Connectors, Skills & Plugins — The Taxonomy**
We touched on this briefly but didn't walk through the structure. Quick version for reference:

- **Connectors** = live links to external services (Gmail, Slack, Drive, Asana, Calendar). Each has its own permission controls.
- **Skills** = specialized instruction sets that make Claude better at specific outputs. The xlsx skill builds proper Excel files. The pdf skill extracts tables. Skills don't connect to anything — they improve output quality.
- **Plugins** = bundles of connectors + skills for a domain. The financial analysis plugin you have installed includes spreadsheet auditing, data cleanup, comparable company analysis, DCF modeling, and deck QC.

The **Ideas tab** in the left sidebar surfaces use cases by role. Filter to Finance and you'll see prompts and workflows tailored to your world. Good self-serve discovery path to browse at your own pace.
![<# alt text #>](../../../../../../Library/Application%20Support/CleanShot/media/media_QmXZZ1El9U/CleanShot%202026-03-13%20at%2007.55.22.png "Screenshot")

**Worth Trying Before Session 2 — Financial Analysis Plugin**
The financial analysis plugin is already installed on your account. Two things worth kicking the tires on between now and session 2, no setup required:

1. **Audit a spreadsheet.** Open a session, drop in one of your working Excel files (an IC Analytics Pack, allocation model, whatever you have handy), and ask Claude to audit it for formula errors, broken references, or logic issues. Type something like "audit this spreadsheet" and the plugin takes over. Low stakes, immediately useful, and it'll give you a feel for how the financial skills work.
2. **Run a comp.** Ask Claude to build a comparable company analysis for one of your portfolio holdings or a name you're evaluating. It'll pull public data, build trading multiples, and output a formatted Excel file. Try something like "build a comps analysis for [ticker]" — good test of whether the output meets your bar for institutional quality.

**What to Think About Before Session 2**
We talked about this toward the end of session 1 — separating the mechanical work from the judgment work. The goal isn't to automate your analysis. It's to figure out which parts of your weekly routine are drudge work that could be pre-assembled so you spend more time on the parts only you can do. Worth spending ten minutes thinking through:

1. When you open your five tabs in the morning — what are you actually scanning for, and what do you skip past? The stuff you skip is a signal: either it doesn't matter (cut it) or it matters but the format isn't right (rebuild it).
2. Your IC Analytics Packs — what's the assembly process? Walk through it step by step. Which parts are you just gathering and formatting data, and which parts are you applying judgment? The gathering part is exactly what Cowork can do on a schedule.
3. Are there workflows you run weekly or monthly that you've never written down? Things where someone watching over your shoulder would say "why did you just do that?" and your answer is experience. Those are the ones worth documenting — not to replace, but to separate the setup from the insight.
4. If you sat down Thursday morning and the data was already collated, formatted, and waiting — what would you actually do with the time you got back? That answer tells us what to build toward.

---

## What to Build Next – Allocation Engine Workbench?

This wasn't on the session 1 agenda, but it's worth calling out separately because it maps directly to work you're already doing.

You described building across four models: Markowitz (mean-variance), HRP (hierarchical risk parity), Black-Litterman, and market-regime playbooks. You're already building quantitative tools with Cursor. Cowork can serve as a complementary development surface for this kind of work — Python with financial analysis packages, your Google Drive data already connected, and the ability to save scripts to your workspace so they persist between sessions. The difference from Cursor: Cowork has your connectors wired in and can run things on a schedule. The difference from ChatGPT: Cowork executes code on your machine against your actual files, not in a sandboxed notebook disconnected from your data.

The practical path: start with a proof-of-concept in a Cowork session — pull your actual positions from the HLV spreadsheet, run one or two allocation models against them, compare the output to your current weights. If the prototype works, we can decide together whether to keep iterating in Cowork or move it to a standalone codebase (where Claude Code or Cursor would take over). Either way, I can help with the architecture, the specs, and the iteration cycle — that's squarely in my wheelhouse regardless of which tool runs the code.

---

## Follow-Up Items

**For you to do:**

- [x] **Privacy settings** — done. Training opt-out confirmed during session 1.
- [ ] **Network egress** — your current setting is restricted (package managers and Anthropic API only). My recommendation: keep it restricted for now. The main thing restricted mode blocks is Python code making direct API calls (e.g., pulling live crypto prices from Crypto.com). If we hit that wall when wiring up the portfolio tasks, we can open it deliberately for specific workflows rather than blanket "all domains." 
- [ ] **Multiple Google accounts** — Cowork's first-party Google connector currently supports one account at a time. Custom MCP servers exist that handle multiple accounts, and that's something we can explore if the fragmentation issue is blocking real workflows. For now, connect whichever account has your primary Hyla data.
- [ ] **Send me your about-me.md** — the contextual profile you built with ChatGPT. If you're comfortable sharing it ahead of session 2, I can do the initial restructuring into Claude's format so we spend session time refining rather than reformatting. If you'd rather wait and do it together live, that works too — just bring the file.
- [ ] **Think about the questions above** — especially the drudge work vs. judgment separation. Ten minutes of honest reflection here will save us hours of building the wrong thing.

**For me to do:**

- [ ] Research multi-agent debate architecture — your description of James's 7 specialized advisor agents and Andrew's 8 debating agents is compelling. The synthetic team concept (Goldman diverse-team model as analogy) is outside my current offering but worth investigating seriously. I'll come back with an honest assessment of what's feasible now vs. what requires custom development.
- [x] Send you links: [WhisperFlow](https://wisprflow.ai/r?ANDY1511) (voice input), [KeepingYouAwake](https://keepingyouawake.app/) (prevent sleep for scheduled tasks)
- [ ] Prepare session 2 with adjusted approach — more hands-on, less demo. Your feedback was clear: "This meeting could be more technical." Next session should be working on your actual tasks live, building things together, with quick productivity wins from minute one.

**A note on session 2 approach:** I heard that you want hands-on work on your actual tasks, not demos of what's possible. I'm restructuring accordingly. Next session will be you driving with me coaching alongside, not me presenting. We'll pick one or two of the items above, work on them live together, and you'll leave with something running. Does that sound aligned?

---

## What Emerged That Wasn't Planned

The multi-agent conversation was the most energizing part of the session and worth flagging separately. The idea of building a stable of specialized agents — each with a defined perspective, calibrated over time, producing structured analysis that you weigh and synthesize.  "I have a team of analysts who each see the world differently, and I'm the portfolio manager synthesizing their views."

James's approach (7 agents analyzing meeting transcripts) and Andrew's approach (8 agents debating a question) are two different architectures for the same idea. The Goldman analogy you drew — a diverse team where disagreement is productive — is a good frame.

I don't have a packaged solution for this today. I'll research what's currently possible with Claude's agent architecture, what the limitations are, and what a realistic implementation path looks like. This could be a significant piece of what makes the system genuinely yours rather than generic.

---

*Next session: TBD. Send me your about-me.md ahead of time if you're willing (or bring it). You drive — pick a task you actually need done, and we'll build it together with me coaching alongside. CLAUDE.md refinement, HLV spreadsheet connection, or the Allocation Engine Workbench are all good starting points, but it's your call what's most useful.*
