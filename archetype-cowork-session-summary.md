# Session Summary: Cowork Coaching & Agentic AI Offering Development
**Source:** Claude.ai conversation, March 11 2026 (mobile, late night)  
**Purpose:** Cowork workspace ingestion — reconcile against existing context.md before editing  
**Status:** Decisions made, hypotheses validated, open items flagged

---

## 1. CONTEXT & FRAMING

This session developed a new service line for Archetype Consulting: executive and founder coaching on Claude Cowork and agentic AI systems, with a distinct differentiator rooted in Andy's startup ops and infosec background. This sits inside the broader Archetype practice — it is not a separate business.

Andy's background relevant to this offering:
- Startup ops: understands how growth-stage organizations actually function
- Infosec: understands data classification, ring-fencing, access control, compliance mapping
- Developmental coaching (second career): preserved at ~50% of total time
- Current Cowork experience: several hours/day for ~2 weeks, past basics, targeting deep competence

---

## 2. CORE DIFFERENTIATOR (VALIDATED)

**The hypothesis:** Combining deep Cowork/agentic expertise with infosec and startup ops background creates a unique market position at the founder/growth-stage level.

**Validation finding:** The position does not currently exist in the market. The coaching space is dominated by productivity/content creators with no governance lens. Enterprise-level governance tooling (Runlayer, MintMCP) exists but requires engineering teams and procurement cycles — nobody is translating this to the founder level in plain language.

**The specific capability no one else has:**
- Can map the full data topology of a Cowork deployment: what stays on-device, what flows through Anthropic's servers, what the VM boundary is, what each MCP connector exposes
- Can map that architecture to specific compliance regimes (SEC, SOC 2, HIPAA, FINRA) that a growth-stage startup may be under
- Understands MCP governance gaps (no built-in auth, no audit trails, tool poisoning vectors) before most founders know to ask
- Can architect n8n + Cowork + LLM hybrid workflows where deterministic logic handles routing and agents handle judgment — a more governable pattern than "give the agent everything"

**The pitch framing that works:**
"You just connected your CRM, your Google Drive, and your Gmail to an AI agent. Do you know exactly what's in scope when that agent runs? Do you know where it logs? Do you know what your Series A term sheet says about data handling?"

**The positioning line:**
Get the edge without the exposure.

---

## 3. OFFERING LADDER

### Tier 1 — Initial Session
- **Format:** 90 minutes, 1:1 with founder or exec
- **Price:** $750 (starting point; room to move to $1,000–$1,500 once deliverable is defined)
- **What they leave with:** Clear mental model of current data exposure; prioritized list of what needs to happen before deploying agents at team scale; possible artifact — a data topology map showing local/Anthropic/MCP/VM layers
- **Role:** Loss leader for the relationship; pipeline generator for Tiers 2 and 3
- **Revenue math:** 3 sessions/week × 48 weeks = $108,000 annual gross as a floor

### Tier 2 — Individual Workflow Development (Follow-on)
- **Format:** Scoped sessions or small project engagements
- **What it covers:** Building skills, plugins, CLAUDE.md context files; designing governed personal Cowork setup; workflow design and implementation
- **Role:** Where productivity gains happen; demonstrates hands-on competence; natural bridge to team engagement

### Tier 3 — Team Enablement (The Real Business)
- **Format:** Fractional/embedded project engagement — closer to a retainer than coaching
- **Price range:** $30,000–$45,000 per engagement (2–3 per year gets to $200K target)
- **What it covers:**
  - Data classification: what exists, where it lives, what classification it deserves
  - MCP governance architecture: access model, audit trail, what's in scope per connector
  - Organizational knowledge layer: aggregate and structure team data for safe consumption by individual Cowork instances
  - Shared workflow infrastructure: governed n8n or similar deterministic scaffolding that feeds agent nodes only where judgment is needed
  - Compliance mapping: architecture documented against applicable regulatory regime
  - Policy: what agents can and cannot touch
- **Key framing:** This is NOT AI training or change management. It's organizational AI readiness — the data infrastructure layer that makes agentic systems safe to deploy at team scale.

---

## 4. FINANCIAL MODEL

| Scenario | Sessions | Team Engagements | Annual Gross |
|----------|----------|-----------------|--------------|
| Floor | 3/week × 48 wks @ $750 | 0 | ~$108K |
| Target | 3/week × 48 wks @ $750 | 2–3 @ $30–45K | ~$200K |

- **Hours target:** 20 hours/week at steady state
- **Time split:** ~50% Archetype/AI work, ~50% developmental coaching practice
- **Timeline:** 3–6 months to fully flesh out the ladder and team offering
- **6-month milestone that confirms on-track:** $100–120K run rate
- **Key caveat:** First 3–6 months will run 25–30 hours/week during build phase

---

## 5. TOOL STACK & TECHNICAL POSITIONS

**Primary tools for the offering:**
- Claude Cowork (core platform being coached)
- n8n for deterministic workflow scaffolding + LLM node insertion at judgment points
- MCP connectors (governance of these is a core service differentiator)

**Why n8n alongside Cowork:**
Deterministic workflow scaffolding is more auditable and governable than pure agent autonomy. Founders in regulated industries can point to exactly where AI touches data. Hybrid architecture is the right answer for compliance-sensitive deployments.

**Cowork scope note:**
Do NOT pin the entire offering identity to Cowork specifically. The frame that ages well: "I help you build a governed AI workflow layer for your organization." Cowork is the current best entry point; the judgment about architecture and governance transfers to n8n, Copilot Cowork, and whatever comes next.

**On cloud Cowork:**
A cloud version is near-certain. Microsoft's Copilot Cowork (launched March 9, 2026) runs in M365 tenant — same Claude engine, cloud architecture. Anthropic will follow or cede the enterprise market. When cloud Cowork arrives, governance questions get more complex, which is good for this business.

**Extended thinking setting:**
Use selectively, not always-on. Toggle on for strategic/analytical depth; leave off for routine Cowork tasks. All surfaces (claude.ai, Claude Code, Cowork) draw from the same usage pool.

---

## 6. LEARNING PATH (COWORK EXPERTISE)

Two-week intensive framework:

**Week 1:**
- Days 1–2: Dissect anthropics/knowledge-work-plugins GitHub — read raw file structure, not just install
- Days 3–4: Build first custom skill using skill-creator plugin; run eval cycle
- Days 5–7: Sub-agent orchestration + scheduled tasks; token economics of MCP-to-Skills compilation

**Week 2:**
- Days 8–9: Build a plugin from scratch useful to a founder (investor update, security posture audit, OKR breakdown)
- Days 10–11: Enterprise admin layer — per-user provisioning, private marketplace flows, Customize menu
- Days 12–13: Prompt craft framework for agentic delegation vs. chat; CLAUDE.md as highest-ROI setup
- Day 14: Document own Cowork stack as worked example / coaching artifact

**Key resources:**
- https://github.com/anthropics/knowledge-work-plugins
- https://github.com/anthropics/skills
- https://resources.anthropic.com/hubfs/The-Complete-Guide-to-Building-Skill-for-Claude.pdf
- https://claude.com/plugins (skill-creator)
- https://code.claude.com/docs/en/plugins
- https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview
- Karo Zieminski (she) — @karozieminski on Substack (paid for subscripton)

**Reading worth paying for:**
- Karo Zieminski (she) — @karozieminski on Substack — AI Product Manager turned AI educator; 11K subscribers; practitioner-level Cowork content; the 50+ tip power user guide is the benchmark for quality. **andy paid for annual sub**
- Sid Saladi — sidsaladi.substack.com — product management background; advanced Cowork guide published March 11 is strong. Andy: His writing is nauseating because it was delayed by AI text. I couldn't read it.
- Both: evaluate 5–6 back posts for consistency before subscribing paid

---

## 7. WORKSPACE ORGANIZATION RECOMMENDATION

**Decision:** Keep Cowork coaching inside the single Archetype workspace. Do not create a separate workspace.

**Rationale:** Cowork/agentic enablement is a service line, not a separate business identity. The ICP, positioning, and client relationships overlap with security and fractional CTO work. Splitting creates friction and splits client context.

**File organization inside the workspace:**
- One workspace per business identity (Archetype)
- Structured files per service line
- Create dedicated section/folder for Cowork offering with its own context, pricing, and positioning files
- Cowork can be directed at just that slice without pulling in unrelated client work

---

## 8. OPEN QUESTIONS / NEXT ACTIONS

| Item | Status | Notes |
|------|--------|-------|
| Define the session deliverable artifact | Open | Leading candidate: data topology map (visual of local/Anthropic/MCP/VM layers). Publishing a version as thought leadership would differentiate immediately |
| Price testing | Open | Start at $750; test path to $1,000–$1,500 once deliverable is crisp |
| First 10 sessions | Action | Start selling the initial session within 30 days. Let team offering emerge from what people ask at the end of those conversations. Don't wait for the full ladder to be designed |
| n8n depth | Open | Needs hands-on exploration; evaluate fit for client workflow architecture work |
| Developmental coaching integration | Strategic | The coaching background is a positioning advantage, not a split. Founders making agentic AI decisions are making organizational and leadership decisions. One person who holds both is rare |
| Karo Zieminski paid sub | Pending | Read 5–6 more posts first; assess consistency before committing |

---

## 9. KEY PHRASES & POSITIONING LANGUAGE TO PRESERVE

- "Get the edge without the exposure."
- "You need to adopt this now to get ahead — while preserving security and data governance."
- "One accountable person who owns the whole picture." (from Archetype core positioning — applies here too)
- The data topology map as a deliverable concept
- "Governed AI workflow layer" as the durable frame (not "Cowork expert")
- The gun range model for data governance: controlled access, time-bound sessions, full audit trails — the environment enforces accountability

---

*Generated: March 11, 2026 | For reconciliation against existing Archetype context.md before workspace edits*
