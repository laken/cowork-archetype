# Cowork Coaching — Offering Reference

*Business model, pricing ladder, competitive differentiator, and learning roadmap for the AI enablement coaching service line. Separate from the session structure (that lives in `ai-executive-coaching-wip.md`) and the governance framework (that lives in `ai-connectivity-governance-framework.md`).*

*Created: March 13, 2026. Source: March 11 mobile session + Ty Shinn session 1 debrief (March 10).*

---

## What This Is

A distinct service line inside Archetype Consulting — not a separate business. ICP, positioning, and client relationships overlap with security and fractional CTO work. Kept inside the single Archetype workspace.

**The durable frame:** "I help you build a governed AI workflow layer for your organization." Cowork is the current best entry point; the architecture and governance judgment transfers when platforms shift. Do not build the brand identity around Claude or Cowork specifically — the offering survives a platform shift; the brand should too.

**The positioning line:** Get the edge without the exposure.

**The pitch that works:**
> "You just connected your CRM, your Google Drive, and your Gmail to an AI agent. Do you know exactly what's in scope when that agent runs? Do you know where it logs? Do you know what your Series A term sheet says about data handling?"

---

## Core Differentiator

The market is dominated by productivity and content creators with no governance lens. Enterprise governance tooling (Runlayer, MintMCP) exists but requires engineering teams and procurement cycles. Nobody is translating this to the founder level in plain language.

**The specific capability no one else has:**

- Can map the full data topology of a Cowork deployment: what stays on-device, what flows through Anthropic's servers, what the VM boundary is, what each MCP connector exposes
- Can map that architecture to specific compliance regimes (SEC, SOC 2, HIPAA, FINRA) that a growth-stage startup may be under
- Understands MCP governance gaps (no built-in auth, no audit trails, tool poisoning vectors) before most founders know to ask
- Can architect n8n + Cowork + LLM hybrid workflows where deterministic logic handles routing and agents handle judgment — a more governable and auditable pattern than "give the agent everything"
- Developmental coaching background: founders making agentic AI deployment decisions are making organizational and leadership decisions. One person holding both lenses is rare.

**The data topology map:** The leading candidate for the Tier 1 session deliverable artifact — a visual showing the local/Anthropic/MCP/VM layers of a client's specific deployment. Publishing a version as thought leadership would differentiate immediately.

---

## Offering Ladder

### Tier 1 — Initial Session (front door)

- **Format:** 90 minutes, 1:1 with founder or exec
- **Price:** $750 starting point; path to $1,000–$1,500 once the deliverable is crisp and tested
- **What they leave with:** Clear mental model of their current data exposure; prioritized list of what needs to happen before deploying agents at team scale; possible artifact — data topology map showing local/Anthropic/MCP/VM layers
- **Role:** Loss leader for the relationship; pipeline generator for Tiers 2 and 3
- **Revenue math:** 3 sessions/week × 48 weeks = ~$108,000 annual gross as a floor
- **Action:** Start selling within 30 days. Don't wait for the full ladder to be designed. Let team offering emerge from what people ask at the end of those first 10 conversations.

### Tier 2 — Individual Workflow Development (follow-on)

- **Format:** Scoped sessions or small project engagements
- **What it covers:** Building skills, plugins, CLAUDE.md context files; designing a governed personal Cowork setup; workflow design and implementation
- **Role:** Where productivity gains happen; demonstrates hands-on competence; natural bridge to team engagement

### Tier 3 — Team Enablement (the real business)

- **Format:** Fractional/embedded project engagement — closer to a retainer than coaching
- **Price:** $30,000–$45,000 per engagement
- **Target:** 2–3 per year
- **What it covers:**
  - Data classification: what exists, where it lives, what classification it deserves
  - MCP governance architecture: access model, audit trail, what's in scope per connector
  - Organizational knowledge layer: aggregate and structure team data for safe consumption by individual Cowork instances
  - Shared workflow infrastructure: governed n8n or similar deterministic scaffolding that feeds agent nodes only where judgment is needed
  - Compliance mapping: architecture documented against applicable regulatory regime (SEC, SOC 2, HIPAA, FINRA)
  - Policy: what agents can and cannot touch
- **Key framing:** This is NOT AI training or change management. It's organizational AI readiness — the data infrastructure layer that makes agentic systems safe to deploy at team scale.

---

## Financial Model

| Scenario | Sessions | Team Engagements | Annual Gross |
|---|---|---|---|
| Floor | 3/week × 48 wks @ $750 | 0 | ~$108K |
| Target | 3/week × 48 wks @ $750 | 2–3 @ $30–45K | ~$200K |

- **Hours target:** 20 hours/week at steady state
- **Time split:** ~50% Archetype/AI work, ~50% developmental coaching practice
- **Timeline:** 3–6 months to fully flesh out the ladder and team offering
- **Build phase:** First 3–6 months will run 25–30 hours/week
- **6-month on-track milestone:** $100–120K run rate

---

## Lessons from Ty Session 1 (March 10)

The first real session produced signal that reshapes the offering structure:

**What worked:**
- Security/architecture framing landed well. Walking through the VM sandbox model, connector permissions, and data retention in plain language is exactly the value. Keep this as the foundation of Tier 1.
- "Drudge work vs. judgment work" framing resonated. The right question isn't "what can we automate?" but "which parts of your weekly routine are pre-assembly, and which parts require only you?" That reframe is clarifying for clients.

**What didn't work:**
- Demo-heavy approach got explicit feedback: "This meeting could be more technical." The morning briefing demo read as "more noise" rather than a productivity win because trust hadn't been established yet. Sequence matters: trust first, delegation second. Don't front-load showcasing what's possible — build toward it.
- Starting with "here's what this can do" before understanding what the client actually needs is backwards. Session 2 needs to invert this: client drives, coach alongside.

**What emerged unexpectedly:**
- Multi-agent debate architecture (James's 7 specialized agents analyzing meeting transcripts; Andrew's 8 debating agents; Goldman diverse-team analogy as a frame) was the most energizing part of the session. This wasn't on the agenda. Ty described building a synthetic team of analysts with different perspectives — not replacing his judgment, but structuring the pre-synthesis so he's working from a richer base. Research this architecture seriously before Session 2.
- Allocation Engine Workbench: Ty is already building quantitative tools (Markowitz, HRP, Black-Litterman, market-regime playbooks) with Cursor. Cowork as a complementary surface for this work — connectors wired in, schedulable, executes against actual files — could be the "holy shit" moment that a generic morning briefing demo couldn't produce.

**Session 2 structural changes:**
- Client drives; Andy coaches alongside. Not presenting — working.
- First task: build CLAUDE.md together (or review the ChatGPT about-me file Ty already has and restructure it for Claude's format)
- Connect HLV spreadsheet live; walk through tabs; wire positions into risk/drift tasks against real data
- One concrete thing Ty leaves with that runs

---

## Open Questions

| Item | Status | Notes |
|---|---|---|
| Define the Tier 1 deliverable artifact | **Active** | Leading candidate: data topology map (visual of local/Anthropic/MCP/VM layers). A published version is immediate thought leadership. |
| Price path to $1,000–$1,500 | Pending | Start at $750; raise once deliverable is crisp and tested. |
| Multi-agent debate architecture | **Research needed** | James's 7-agent model; Andrew's 8-agent debate model; Goldman diverse-team analogy. What's feasible now with Claude's architecture vs. what requires custom dev? |
| n8n depth | Pending | Needs hands-on exploration before positioning in team engagements. |
| Karo Zieminski paid sub | Pending | Read 5–6 more posts; assess consistency before committing. |
| Session 2 with Ty | **Next action** | Restructured as hands-on. Ty drives. Priorities: CLAUDE.md, HLV spreadsheet live connection, one running task. |

---

## Tool Stack for the Offering

- **Claude Cowork** — core platform being coached
- **n8n** — deterministic workflow scaffolding with LLM node insertion at judgment points; more auditable and governable than pure agent autonomy; founders in regulated industries can point to exactly where AI touches data
- **MCP connectors** — governance of these is a core service differentiator

**Platform watch list:** Microsoft Copilot Cowork (launched March 9, 2026 on M365; same Claude engine, cloud architecture); Google Workspace Studio (Gemini-powered, GA on Business plans, Google-ecosystem-only); Microsoft Copilot Tasks (enterprise-first, trending toward SMB). When cloud Cowork arrives from Anthropic, governance questions become more complex. Good for this business.

---

## Competitive Landscape

The coaching space is dominated by productivity and content creators with no governance lens. Direct competitors doing personalized Cowork setup sessions with a security/compliance angle: essentially nonexistent as of March 2026.

Adjacent competition:
- Generic AI consultants offering "AI strategy" workshops (broad, not hands-on, no compliance depth)
- YouTube/Substack creators doing Cowork tutorials (free, not personalized, no governance)
- Enterprise governance tools: Runlayer, MintMCP (require engineering teams + procurement — not translating to founders)
- Anthropic's own onboarding improvements (coming, but slow and generic; the governance evaluation and compliance mapping are out of scope for a product team)

The window is open. The question is how long it stays open. Speed matters more than perfection.

---

## Positioning Language to Preserve

- "Get the edge without the exposure."
- "You need to adopt this now to get ahead — while preserving security and data governance."
- "One accountable person who owns the whole picture." (from Archetype core positioning — applies here)
- Data topology map as the canonical deliverable concept
- "Governed AI workflow layer" as the durable frame (not "Cowork expert")
- The gun range model for data governance: controlled access, time-bound sessions, full audit trails — the environment enforces accountability

---

*Update this file after: pricing decisions, completed sessions with new learnings, platform shifts, or changes to the offering structure.*
