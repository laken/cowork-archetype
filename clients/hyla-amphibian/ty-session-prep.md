# Ty Shinn Session Prep — Tuesday, March 10, 9:00 AM PT

---

## Ty's Survey Responses (Submitted March 9)

**Plan:** Max
**Cowork:** Yes, has used it
**Daily tools:** Gmail, Google Drive, Calendar, Slack, Asana, Granola, DocuSign, DocSend, Telegram
**AI tools:** ChatGPT Pro daily — research, idea generation, financial analytics, document creation. Previously used ChatGPT + Cursor/VS Code for Python. Less coding recently.

**Morning workflow:** Monitors global markets (U.S. macro, traditional financial, digital assets). Oversees portfolio management across the Amphibian Alpha Funds (BTC Alpha, ETH Alpha, USD Alpha), Hyla Liquid Venture Fund, selected SPVs, and legacy vehicles. Leads direct trading, manager research, investment diligence, portfolio construction, high-conviction idea generation. Constantly on TradingView, CoinMarketCap, Delphi Digital. Simultaneously building the investment platform: data quality, research workflows, portfolio monitoring, risk controls, allocation processes. Current priority: auditable risk and allocation engine spanning HRP, mean-variance/Markowitz, market-regime playbooks, and Black-Litterman. Operating cadence: weekly/monthly risk limit reviews, portfolio drift monitoring, monthly IC Analytics Packs and Allocation Memos, manager selection/monitoring/exit, decision/exception logs.

**Concerns:** File contamination or destruction, security leaks. Fragmented/incomplete data across local and cloud drives.

**Success:** "Low friction setup that enables me to move quickly and productively without too many speedbumps while still being protected with backups or a safe operating infrastructure. I would like to 'leapfrog' classic missteps and implement quick productivity boosters and plugins that supercharge my workflow."

---

## Remaining Prep (Tonight / Tomorrow AM)

- [ ] Skim security doc sections 1, 2, 7 — email data flow, consumer vs. commercial terms, ring-fencing framework
- [ ] Run `ty-morning-briefing` manually ~30 min before session so output is fresh
- [ ] Pull up `library/ty-session-cheatsheet.md` before the call

---

## Session Flow (90 min)

### Phase 1: Security, Workspace Setup & CLAUDE.md (20 min)

**Workspace orientation (2-3 min, do this first):**
- Cowork asks you to choose a workspace folder every time you start a session — there's no default
- Recommend 2-3 workspaces from the start: one for Hyla/Amphibian fund work, one for personal, possibly a third for platform development
- Point each at a folder in iCloud Drive — automatic sync and backup
- Directly addresses his file contamination concern: separate workspaces = separate data surfaces
- Each workspace can carry its own CLAUDE.md with different context, connector preferences, and behavioral instructions — so fund work Claude and personal Claude behave differently

**Build a CLAUDE.md live (5-7 min):**
- This is the single highest-leverage setup step. Cowork has zero memory between sessions. Without a CLAUDE.md, every session starts from scratch — Ty has to re-explain who he is, what Amphibian does, and what he cares about every time.
- Build it together from his survey responses right there in the session. Seed it with: who he is (CFA, GP at Hyla/Amphibian), fund vehicles (BTC Alpha, ETH Alpha, USD Alpha, Hyla Liquid Venture, SPVs), current priorities (allocation engine, risk framework), tools he uses, preferences for how Claude should work with him.
- He's read Ruben's article — he already knows this concept exists. Doing it live, from his own context, makes it concrete.
- This is also a trust moment: he sees exactly what Claude knows about him, because he wrote it.

**Security & privacy (5 min):**
- He's on Max — confirm privacy settings, training opt-out toggle
- Consumer vs. Commercial terms: Max is under Consumer Terms (same as Pro). The opt-out toggle is the critical action item. This is a credibility moment — most people don't know this.
- **Tool permissions (show this):** Each connector has per-tool Allow / Ask / Block settings. He can allow Asana reads while blocking writes, permit email search while blocking send. This is the concrete version of "ring-fencing" — not hardware isolation, but granular control over what Claude can and can't do with each connected service. Navigate to Customize > Connectors > Tool permissions to show him.
- Ring-fencing: his Mac Mini "oasis" idea conflates Cowork with OpenClaw. Cowork is already sandboxed (VM + per-connector permissions). The ring-fencing is about which connectors you enable and what the tool permission levels are, not which hardware you're on.
- MCP connectors fetch on demand, not cached by the connector. Content that enters the conversation IS retained (30 days if training is off). Email content passes through Anthropic's servers for LLM processing.
- Gaps to acknowledge: calendar data specifics still underdocumented, Granola transcript flow is an open question, prompt injection is real but defenses are evolving

### Phase 2: Live Briefing Demo (15 min)
- Show the `ty-morning-briefing` output
- Walk through: regime classification, technical context, futures basis signal
- Highlight that this uses Crypto.com public data + Andy's accounts as proxy
- Let him react — what's useful, what's missing, what would he change?

### Phase 3: The Gap — Demo to Transformation (20 min)
- Use the cheat sheet gap table
- Key framing: "This tells you what happened in markets. The real system tells you what it means for your specific portfolio decisions today."
- Introduce multi-agent concept: daily briefing is one of 3-4 specialized agents
- Portfolio Operations (weekly), Research Synthesis (on-demand), Platform Dev Tracker (weekly)

### Phase 4: Staged Reveal — HLV Spreadsheet (10 min)
- Don't open it preemptively. After the gap discussion:
  > "The real unlock happens when we connect your actual portfolio data. I know you have the HLV Portfolio Management spreadsheet in Drive. If we connected that, the briefing could show drift from target allocation, manager overlap, and risk limit utilization every morning. Want to pull it up and see what that would look like?"
- If yes: search Google Drive live, walk through what each tab feeds into
- If he hesitates: walk through the concept using a hypothetical instead

### Phase 5: Discovery & Next Steps (10 min)
- Discovery questions are in the cheat sheet — prioritize:
  - "What does your first 15 minutes with TradingView actually look like?"
  - "How much time do you spend building IC Analytics Packs each month?"
  - "What are the 3-4 data sources that should be connected but aren't?"
  - "Is the goal to make the existing process faster, or to enable analysis you're not doing at all right now?"
- If he's bought in, concrete next steps:
  1. Connect his own Gmail, Calendar, Slack under his Cowork instance
  2. Connect Asana for platform development tracking
  3. Evaluate the HLV spreadsheet for sensitivity/readiness
  4. Pick 1-2 additional financial data sources (Morningstar, FactSet, LunarCrush, Aiera)
  5. Define risk limits and target allocations so the system knows what "drift" means
  6. Expand the CLAUDE.md we built together — add fund-specific terminology, reporting cadences, preferred formats as they emerge through use

---

## Framing: This Is Pro Bono, Not a Sale

Ty is a colleague. Andy is offering pro bono help while getting real executive feedback on the enablement offering. Don't pitch, don't close, listen. If the system proves genuinely useful across all Hyla/Amphibian principals (especially with the merger), that could become a paid engagement — let it emerge naturally.

---

*Updated: March 9, 2026*
