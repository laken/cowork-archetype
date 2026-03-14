# Ty Shinn Session Prep — Tuesday, March 10, 9:00 AM PT

 *  --

## Ty's Survey Responses (Submitted March 9)

**Plan:** Max
**Cowork:** Yes, has used it
**Daily tools:** Gmail, Google Drive, Calendar, Slack, Asana, Granola, DocuSign, DocSend, Telegram
**AI tools:** ChatGPT Pro daily — research, idea generation, financial analytics, document creation. Previously used ChatGPT + Cursor/VS Code for Python. Less coding recently.

**Morning workflow:** Monitors global markets (U.S. macro, traditional financial, digital assets). Oversees portfolio management across the Amphibian Alpha Funds (BTC Alpha, ETH Alpha, USD Alpha), Hyla Liquid Venture Fund, selected SPVs, and legacy vehicles. Leads direct trading, manager research, investment diligence, portfolio construction, high-conviction idea generation. Constantly on TradingView, CoinMarketCap, Delphi Digital. Simultaneously building the investment platform: data quality, research workflows, portfolio monitoring, risk controls, allocation processes. Current priority: auditable risk and allocation engine spanning HRP, mean-variance/Markowitz, market-regime playbooks, and Black-Litterman. Operating cadence: weekly/monthly risk limit reviews, portfolio drift monitoring, monthly IC Analytics Packs and Allocation Memos, manager selection/monitoring/exit, decision/exception logs.

**Concerns:** File contamination or destruction, security leaks. Fragmented/incomplete data across local and cloud drives. **Say more on this?**

**Success:** "Low friction setup that enables me to move quickly and productively without too many speedbumps while still being protected with backups or a safe operating infrastructure. I would like to 'leapfrog' classic missteps and implement quick productivity boosters and plugins that supercharge my workflow."

 *  --

## Remaining Prep (Tonight / Tomorrow AM)

 *   [ ] Skim security doc sections 1, 2, 7 — email data flow, consumer vs. commercial terms, ring-fencing framework
 *   [ ] Run `ty-morning-briefing` manually ~30 min before session so output is fresh
 *   [ ] Pull up `library/ty-session-cheatsheet.md` before the call

 *  --

## Session Flow (90 min)

### Phase 1: Security, Workspace Setup & CLAUDE.md (20 min)

**Workspace orientation (2-3 min, do this first):**

 *   Cowork asks you to choose a workspace folder every time you start a session — there's no default
 *   Make a parent folder for all workspaces e.g. **iCloud Drive/cowork**
 *   Recommend 2-3 workspaces from the start: one for Hyla/Amphibian fund work, one for personal, possibly a third for platform development
 *   Point each at a folder in iCloud Drive — automatic sync, backup, and mobile access to outputs (markdown, PDFs viewable on iPhone/iPad via Files app)
 *   **iCloud Drive setup — two things to get right:**
  1. **Disable Optimized Storage.** System Settings → Apple ID → iCloud Drive → uncheck "Optimize Mac Storage." Without this, macOS can evict files to cloud-only stubs when disk gets tight — Cowork can't read stubs. Screenshot at `offerings/ai-enablement/assets/macos-icloud-optimize-diable.png` if he wants to see the setting.
  2. **Pin the workspace folder.** Right-click the Cowork folder in Finder → "Keep Downloaded." This prevents eviction even if Optimized Storage gets re-enabled later.
 *   Frame iCloud as a read-from-anywhere layer, not a collaborative editing surface. Viewing outputs on mobile is great; editing the same file from iPhone while Cowork is running risks iCloud sync conflicts (`filename 2.md` duplicates).
 *   **Backup beyond iCloud:** Briefly mention [Backblaze](https://www.backblaze.com/) ($99/yr unlimited) as a set-and-forget full-disk backup that covers everything iCloud doesn't — local files, non-synced folders, the stuff that isn't in any cloud drive. iCloud syncs specific folders; **Backblaze** backs up the whole machine continuously. Belt and suspenders. If he's worried about file destruction, having both layers is the real answer.
 *   Directly addresses his file contamination concern: separate workspaces = separate data surfaces
 *   Each workspace can carry its own CLAUDE.md with different context, connector preferences, and behavioral instructions — so fund work Claude and personal Claude behave differently

**Build a CLAUDE.md live (5-7 min):**

  * This is the single highest-leverage setup step. **Cowork has zero memory between sessions**. Without a CLAUDE.md, every session starts from scratch — Ty has to re-explain who he is, what Amphibian does, and what he cares about every time.
  * Build it together from his survey responses right there in the session. Seed it with: who he is (CFA, GP at Hyla/Amphibian), fund vehicles (BTC Alpha, ETH Alpha, USD Alpha, Hyla Liquid Venture, SPVs), current priorities (allocation engine, risk framework), tools he uses, preferences for how Claude should work with him.
 *   He's read Ruben's article — he already knows this concept exists. Doing it live, from his own context, makes it concrete.
 *   This is also a trust moment: he sees exactly what Claude knows about him, because he wrote it.

**The sandbox — what's actually running (60 sec):**

 *   Cowork runs a real Linux VM (Ubuntu 22.04) on Ty's Mac using Apple's Virtualization.framework — the same native hypervisor UTM uses. It's hardware-level isolation with its own kernel, not a browser tab or a Docker container. Near-native CPU performance on Apple Silicon.
 *   The VM is isolated from his filesystem by default. It can only see folders he explicitly grants access to via VirtioFS mount (the "Select a folder" prompt). That mount is per-session, not permanent. The VM's network is locked to a strict allowlist — it can reach Anthropic's API, PyPI, npm, and essentially nothing else. No access to his LAN, no arbitrary web requests.
 *   Within the mounted folder, file deletes require a separate permission prompt (the mount starts as read-write but not read-write-delete).
 *   The VM resets between sessions. Anything Claude creates inside the VM that isn't saved to the mounted folder disappears. This is why the folder grant matters — it's the only persistent bridge.
 *   **Cowork only runs when the Mac is awake and the Claude desktop app is open.** There's no cloud server keeping things alive. Scheduled tasks (like a morning briefing) only fire if the app is running at the scheduled time. If his laptop is closed or the app is quit, the task waits until next launch. **This is the tradeoff for everything running locally — privacy and control, but he has to leave the app open for automation to work. **Practical tip: [KeepingYouAwake](https://keepingyouawake.app/) is a free Mac menu bar app that prevents sleep — one click to keep the Mac awake overnight so the morning briefing fires on schedule.
 *   This is the architectural answer to his "contamination or destruction of important files" concern. Four layers of isolation: VM boundary, bubblewrap namespace isolation, syscall filtering, and network allowlisting. Claude can't reach beyond the folder he grants.
 *   **One sentence framing: "It's like giving someone a desk in a clean room with one filing cabinet you chose. When they leave, the room gets wiped."**

**Connectors, skills, and plugins — the building blocks (2-3 min):**

 *   Three concepts, each builds on the last:
  - **Connectors** are live links to external services — Gmail, Slack, Asana, Google Drive, Google Calendar. Each connector has individual tool permissions (read, write, delete) that Ty controls. When Claude searches his email or pulls a Drive doc, that's a connector doing the work.
  - **Skills** are specialized instruction sets that teach Claude how to do specific tasks well. The xlsx skill knows how to build proper Excel files with formatting and formulas. The pdf skill knows how to extract tables. Skills don't connect to anything external — they make Claude better at specific output types.
  - **Plugins** bundle connectors, skills, and tools into installable packages for a domain. The financial analysis plugin we installed includes skills for spreadsheet auditing, data cleanup, comparable company analysis, DCF modeling, and presentation QC — all in one package.
 *   Why this matters for Ty: he doesn't need to understand the architecture, but he should know that when Claude does something impressive with a spreadsheet, that's a skill at work. When it pulls his Asana tasks, that's a connector. And when he wants a whole new capability domain, he installs a plugin.
 *      
 **What's already installed that's relevant to him:**

  - **Spreadsheet audit** (`audit-xls`) — can review his HLV Portfolio Management spreadsheet for formula errors, logic issues, and model integrity. Directly relevant to the allocation engine he's building.
  - **Data cleanup** (`clean-data-xls`) — addresses his fragmented data concern. Normalizes messy spreadsheets: inconsistent formatting, mixed types, duplicates.
  - **Comparable company analysis** (`comps-analysis`) — useful for manager research and investment diligence.
  - **Interactive dashboard builder** — could generate the IC Analytics Packs he currently builds manually each month.
  - **Statistical analysis** — risk analysis, correlation, trend detection across portfolio data.
 *   **Show him the Ideas tab** (left sidebar). It surfaces use cases by role — filter to Finance and he'll see prompts and workflows tailored to his world. Good self-serve discovery path for after the session. He can browse at his own pace instead of waiting for us to suggest things.
 *   One sentence framing: "Think of connectors as the pipes, skills as the expertise, and plugins as hiring a specialist who brings their own tools."

**Security & privacy (5 min):**

 *   He's on Max — confirm privacy settings, training opt-out toggle
 *   Consumer vs. Commercial terms: Max is under Consumer Terms (same as Pro). The opt-out toggle is the critical action item. This is a credibility moment — most people don't know this.
 *   **Tool permissions (show this):** Each connector has per-tool Allow / Ask / Block settings. He can allow Asana reads while blocking writes, permit email search while blocking send. This is the concrete version of "ring-fencing" — not hardware isolation, but granular control over what Claude can and can't do with each connected service. Navigate to Customize > Connectors > Tool permissions to show him.
 *   **How connectors route (if he asks):** MCP connector calls go from Claude inside the VM → virtual socket to the desktop app on his Mac → MCP server → external API. Connector traffic never runs inside the VM and never touches his local network directly.
 *   Ring-fencing: his Mac Mini "oasis" idea conflates Cowork with OpenClaw. Cowork is already sandboxed (VM + per-connector permissions). The ring-fencing is about which connectors you enable and what the tool permission levels are, not which hardware you're on.
 *   MCP connectors fetch on demand, not cached by the connector. Content that enters the conversation IS retained (30 days if training is off). Email content passes through Anthropic's servers for LLM processing.
 *   Gaps to acknowledge: calendar data specifics still underdocumented, Granola transcript flow is an open question, prompt injection is real but defenses are evolving

### Phase 2: Live Briefing Demo (15 min)
 *   Show the `ty-morning-briefing` output
 *   Walk through: regime classification, technical context, futures basis signal
 *   Highlight that this uses Crypto.com public data + Andy's accounts as proxy
 *   Let him react — what's useful, what's missing, what would he change?

### Phase 3: The Gap — Demo to Transformation (20 min)
 *   Use the cheat sheet gap table
 *   Key framing: "This tells you what happened in markets. The real system tells you what it means for your specific portfolio decisions today."
 *   Introduce multi-agent concept: the morning briefing is one layer of a system that maps to his actual operating cadence:

**His operating cadence → scheduled Cowork tasks:**

 *   **Daily briefing** (already demoed) — market regime classification, macro context. But the regime classification isn't just informational: it's the input that selects which allocation playbook is active. Risk-off regime → different posture than trending bull. The briefing becomes the trigger, not just the report.
 *   **Weekly risk limit review** — scheduled task pulls current positions from HLV spreadsheet (via Google Drive connector), computes position sizing vs. limits, flags breaches. Output: formatted risk dashboard or email summary. Currently manual.
 *   **Weekly portfolio drift monitoring** — scheduled task compares actual allocations vs. target weights across BTC Alpha, ETH Alpha, USD Alpha, Hyla Liquid Venture. Calculates drift magnitude, flags rebalancing candidates. Layers the daily regime classification on top to contextualize *why* drift is happening — is this market-driven or allocation-driven?
 *   **Monthly IC Analytics Pack** — the big one. Aggregates monthly performance, attribution by vehicle, risk metrics, manager performance vs. benchmarks. Currently built manually. Cowork can assemble 80% of this: pull data from spreadsheets (Drive connector), run the analytics (statistical analysis + Python), generate interactive HTML dashboards (dashboard builder skill) or formatted Excel (xlsx skill). Ty fills in the narrative and judgment; the data assembly is automated.
 *   **Monthly Allocation Memo** — structured document pulling regime context, model outputs, drift data, and Ty's recorded views into a template. Docx skill handles formatting. Ty adds the investment rationale.
 *   **Manager monitoring** — scheduled monthly review: performance vs. benchmarks, overlap analysis across managers, exception flagging. If manager data lives in the HLV spreadsheet, this is connectable now.

**His allocation engine priority → what Claude can actually compute:**

 *   He's building across four models: Markowitz (mean-variance optimization), HRP (hierarchical risk parity — clustering-based, handles noisy crypto correlations better), Black-Litterman (blends market equilibrium with his own views), and market-regime playbooks (different allocation postures for different conditions).
 *   Claude can run all of these in Python — scipy for HRP clustering, numpy/pandas for Markowitz optimization, Black-Litterman implementation with Ty's conviction inputs. Not as a production system, but as an interactive workbench: "Here are my current positions and my views on BTC vs. ETH for next quarter — show me what each model recommends and where they disagree."
 *   The comparison across models is where the value is. Each model has different assumptions. Seeing them side by side — with visualizations of the efficient frontier, cluster dendrograms, weight differences — turns the allocation decision from "which model do I trust" into "where do the models agree, and where do I need to apply judgment?"
 *   **This is aspirational for session 1.** Don't demo it. But name it: **"Your allocation engine is exactly the kind of thing Cowork can serve as a development workbench for — running models interactively, comparing outputs, iterating on parameters, before anything gets productionized."**

**One framing sentence for Phase 3:** "The morning briefing is the daily pulse. The real system is a set of scheduled tasks that match your weekly and monthly operating cadence — risk reviews, drift monitoring, IC packs, allocation memos — each one pulling live data and producing the outputs you're currently building by hand."

### Phase 3b: Live Demo — Risk & Drift Reports (5 min, optional insert)

**Two scheduled tasks are built and ready to run on demand:**

 *   `weekly-risk-limit-review` — pulls live Crypto.com prices for direct crypto positions, uses reported NAV for manager allocations, computes position weights against defined limits, flags breaches. Already tested: flags ETH Alpha's ETH concentration breach and USD Alpha's ETH overweight.
 *   `weekly-drift-monitor` — same data, computes drift from target allocations, classifies severity, calculates the exact dollar trade needed to rebalance each position. Fund-level health scores (BTC Alpha: Monitor, ETH Alpha: Action Needed, USD Alpha: Action Needed, Hyla Liquid Venture: Aligned).

**Data source:** `clients/hyla-amphibian/demo-portfolio.csv` — stub with **four fund vehicles** and 28 positions:

 *   **BTC Alpha, ETH Alpha, USD Alpha** — direct crypto holdings (BTC, ETH, SOL, AVAX, LINK, DOGE) with live Crypto.com pricing
 *   **Hyla Liquid Venture** — 14 manager allocations using actual fund names from Ty's universe (Pythagoras Absolute Return, CMCC Global Liquid Fund 4, CoinFund Seed Fund II, Autonomous VC, VanEck Ventures, Contango Blockchain X AI, Skycatcher Onchain, ZeroKnowledge ZKV Liquid, etc.) with stub NAV values
 *   Not Ty's real data or real allocation amounts — tell him that upfront. But the manager names are real, and the structure mirrors his actual fund-of-funds layer.

**Sample reports already generated:** `clients/hyla-amphibian/risk-reports/risk-limit-review-2026-03-09.md` and `drift-monitor-2026-03-09.md`. Total demo AUM: ~$7.6M across all vehicles. Can show these directly, or re-run live in the session (takes ~30 seconds, crypto positions use real-time prices).

**How to demo:** Open a new Cowork session pointed at the Archetype folder. Say: *"I built two weekly scheduled tasks using a stub portfolio that mirrors your fund structure — including Hyla Liquid Venture's manager allocations. Let me run the risk limit review." Then trigger it manually from the Scheduled section in the sidebar. Walk through the output: "The Alpha funds use live Crypto.com prices — those numbers are real as of right now. The HLV section shows your manager universe with stub NAV values. The system flagged two concentration breaches in the Alpha funds and shows manager-level drift across all 14 HLV allocations. In production, this reads from your HLV spreadsheet instead of the demo CSV, and it runs every Monday morning automatically."*

**The pivot to his real data:** "If we swapped this CSV for your actual HLV spreadsheet via the Google Drive connector, and plugged in your real risk limits, target weights, and latest manager NAVs, this runs every Monday before you start your week. The Alpha fund positions get live pricing automatically. The manager allocations update when you update the spreadsheet."

### Phase 3c: Email Triage Demo (2-3 min, if time allows)

**Why this lands:** Email triage is the most universally relatable AI use case. After the portfolio-specific demo, this shows breadth — Cowork isn't just a finance tool, it handles the operational overhead too.

**How to demo:** Use the Hyla Gmail inbox live — it has confirmed write access (FastMail token is read-only). Say: "Let me show you something completely different. This is the actual Hyla inbox." Ask Cowork to pull recent emails, triage them by urgency, and draft a reply to one. The whole thing takes 30 seconds. If the draft is good, that sells itself.

**The hook — and it's already built:** "This isn't hypothetical. I've already set up two scheduled tasks — `email-triage-morning` runs at 7 AM weekdays and `email-triage-evening` runs at 5 PM. They scan unread messages, categorize by urgency, and auto-draft replies in Gmail for anything actionable. When you sit down with coffee, the drafts are already waiting. You just review, tweak if needed, and hit send."

**Where the reports go:** `Archetype/email-triage/triage-YYYY-MM-DD-morning.md` (and evening). Scannable summary tables with draft status and thread links.

**Connectors:** Gmail connector has full read + write (draft creation confirmed). FastMail is read-only due to token scope — fine for personal inbox triage but can't auto-draft there.

### Phase 4: Staged Reveal — HLV Spreadsheet (10 min)
 *   Don't open it preemptively. After the gap discussion:
  > "The real unlock happens when we connect your actual portfolio data. I know you have the HLV Portfolio Management spreadsheet in Drive. If we connected that, the briefing could show drift from target allocation, manager overlap, and risk limit utilization every morning. Want to pull it up and see what that would look like?"
 *   If yes: search Google Drive live, walk through what each tab feeds into
 *   If he hesitates: walk through the concept using a hypothetical instead

### Phase 5: Discovery & Next Steps (10 min)
 *   Discovery questions are in the cheat sheet — prioritize:
  - "What does your first 15 minutes with TradingView actually look like?"
  - "How much time do you spend building IC Analytics Packs each month?"
  - "What are the 3-4 data sources that should be connected but aren't?"
  - "How much of your day is email? Would automated triage and draft replies be useful — flagging what needs attention, drafting responses you just review and send?"
  - "Is the goal to make the existing process faster, or to enable analysis you're not doing at all right now?"
 *   If he's bought in, concrete next steps:
  1. Connect his own Gmail, Calendar, Slack under his Cowork instance
  2. Connect Asana for platform development tracking
  3. Evaluate the HLV spreadsheet for sensitivity/readiness — what tabs contain position data, target allocations, risk limits? This is the foundation for the weekly scheduled tasks.
  4. Define risk limits and target allocations explicitly so the system knows what "drift" and "breach" mean — these become parameters in the CLAUDE.md or a reference file
  5. Pick the first scheduled task to build together: the weekly risk limit review is probably the tightest scope and highest immediate value
  6. Pick 1-2 additional financial data sources (Morningstar, FactSet, LunarCrush, Aiera) — especially for manager benchmarking
  7. Expand the CLAUDE.md we built together — add fund-specific terminology, vehicle names, reporting cadences, preferred formats, allocation model preferences as they emerge through use



## Framing: This Is Pro Bono, Not a Sale

Ty is a colleague. Andy is offering pro bono help while getting real executive feedback on the enablement offering. Don't pitch, don't close, listen. If the system proves genuinely useful across all Hyla/Amphibian principals (especially with the merger), that could become a paid engagement — let it emerge naturally.


*Updated: March 10, 2026*
