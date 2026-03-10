# CLAUDE.md — Working Memory for Andy Laken / Archetype Consulting

*This file is for Claude's orientation at the start of any session. It covers how to work with Andy, not what to write — that lives in context.md.*

---

## The Workspace

- **context.md** — Standing brief: who Andy is, clients, voice rules, writing prohibitions, pricing, content calendar. Read this first on any content or strategy task.
- **offerings/ai-enablement/** — AI executive enablement advisory (primary active offering). Master WIP: `ai-executive-coaching-wip.md`.
- **offerings/security-hardening/** — Crypto fund security hardening package (on hold). Master WIP: `crypto-hardening-package-wip.md`.
- **clients/hyla-amphibian/** — Ty Shinn session materials, Amphibian proposal, and `source-material/` subfolder with internal Hyla/Amphibian security documents.
- **content/article-drafts/** — Working drafts, not for publication. Current active draft: `draft-d-combined.md` (SIM swap / defense in depth).
- **outreach/** — All pipeline materials: Telegram, Acquia alumni, executive briefs, recommendations tracker.
- **business/** — Early-stage strategy docs (AI-generated, treat as drafts).

---

## How Andy Works

**He has a strong editorial sense.** He will catch things that aren't in any rulebook — a sentence that performs instead of delivers, a transition that's organizational rather than logical, a paragraph that explains its structure instead of hiding it. Don't expect rule compliance to be enough.

**He is sleep-deprived and time-pressured.** Runway is tight (see context.md). Outreach and pipeline matter more than perfection. Ship at 70% is real — but 70% has to be genuinely worth editing, not worth diagnosing.

**He is direct and will say when something is wrong.** Take it at face value, fix the actual problem, don't over-apologize.

**He context-switches between sessions.** Business strategy, blog writing, site work, and outreach all live in different sessions. When he returns to blog work, orient from the draft files rather than assuming session continuity.

**He is an expert at productivity and project management tools.** Scrum Master certified, extensive experience with Kanban, Jira, Notion, and similar systems. Do not explain basic concepts or hand-hold on tooling. Treat him as a peer.

---

## How to Write With Andy (Lessons Learned)

**Before writing any article, get three things:**
1. The argument in one paragraph, in Andy's words — what he wants the reader to believe by the end that they didn't believe at the beginning, and the one fact or moment that changed it.
2. A benchmark piece — one article he'd point to and say "that's the register." Even a few paragraphs. This gives a positive model, not just prohibitions to avoid.
3. Confirmation of the specific audience and context (e.g., Andrew Hoppin's warm outreach to peer fund managers vs. cold LinkedIn).

**The failure mode to avoid:** Generating from the outside in — imposing a defensible structure (story, framework, diagnosis, close) and filling it in section by section. This produces prose that holds up locally but doesn't accumulate. Each part is fine; the piece doesn't build.

**What good structure feels like:** Every paragraph follows the previous one for a *logical* reason, not an organizational one. Transitions should answer "why does this come next?" not "what's the next section?" If you can't articulate the logical connection, the transition is organizational and needs to be rebuilt.

**Editing LLM text produces more LLM text.** When a draft isn't working, discard it and write from the source material. Don't patch.

**The prohibitions in context.md are necessary but not sufficient.** They describe what wrong looks like. A benchmark example describes what right looks like. Both are needed.

---

## Session Routing

- **Blog / article work:** Continue in the article session, or start fresh with a pointer to draft files. Claude can orient from files faster than from long context.
- **Business strategy:** New session. Separate context, separate focus.
- **Site work (archetypeconsulting.io):** New session, or same session if it follows naturally from content work.

---

## Evaluating Vendor Claims (Lessons Learned — Security Research)

Andy caught a significant failure mode in security vendor research: treating marketing copy as technical documentation and giving vendors the benefit of the doubt when claims are ambiguous.

**The specific pattern to avoid:**

- A vendor says their tool "executes actions via the agent" — do not treat this as evidence of architectural constraint. CrowdStrike RTR also executes via the agent. The transport mechanism says nothing about the access surface.
- A vendor lists specific actions their SOC can take — do not treat a list of examples as an exhaustive enumeration unless the documentation explicitly says so. "Along with other steps our SOC can take" means the list is illustrative, not complete.
- A vendor's marketing emphasizes a privacy-friendly framing — do not infer that the underlying capability is absent. SentinelOne frames remote shell as "automated remediation"; it is still a full shell.

**The standard to apply:**

When evaluating a claim about what a vendor *cannot* do (especially privacy or access-limitation claims), ask: does the documentation explicitly state this limitation, or does it merely describe what the vendor typically does? These are different. Absence of a capability from marketing copy is not evidence the capability doesn't exist.

Claims about vendor access constraints are only defensible when:
1. The vendor's technical documentation explicitly states the limitation, not just describes common use cases.
2. A contractual commitment exists, or
3. A credible independent technical audit confirms the architecture.

**When in doubt, say so explicitly** and flag what question would resolve the uncertainty — don't paper over it with confident-sounding synthesis.

---

*Last updated: March 8, 2026, after Ty session prep and guinea pig pipeline planning.*

---

## Strategic Direction — March 2026 (Important)

**Andy is more enthusiastic about the "vibe coder stabilization" offering than the FSP security offering.** This is a significant signal and should be treated as a primary strategic thread, not a sidebar.

**What this offering is:** Non-technical founders are building real products with AI tools (Claude, Cursor, etc.) and hitting walls — no formal specs, no architecture, accumulating technical debt, security gaps, not ready to scale. Andy can read the codebase, diagnose the architecture, write the specs, and run the remediation process. That combination is rare and exactly what these founders need.

**Why Andy is well-positioned:** Technical depth + PM/Scrum background + ability to communicate with non-technical founders. Most helpers are either engineers who can't communicate or PMs who can't read code.

**The Elijah Parker example:** Elijah is building a multi-tenant financial management platform for bitcoin miners using Claude, no formal specs, about to show it to anchor advisors. Classic vibe coding wall. Potential near-term engagement: code audit + architecture review + spec-driven development transition.

**Open question to resolve:** Can this be productized as cleanly as the FSP? What does the engagement look like — deliverables, timeline, price? This needs to be scoped before it becomes a second offering.

**"Show Me the Carfax" framing (from Elijah call):** Security as a due diligence deliverable for investor presentations — not just "you might get hacked" but "your investors are going to ask about this, here's how to get ahead of it." Reframes the FSP sale from prevention to proactive credentialing. Worth developing as a positioning angle.

---

## AI Enablement Advisory — Current State (March 8, 2026)

**First guinea pig session:** Ty Shinn (GP, Hyla Funds), booked for Tuesday March 10. Session prep and cheat sheet in `clients/hyla-amphibian/`.

**Key files for this offering:**
- `offerings/ai-enablement/ai-executive-coaching-wip.md` — Master offering doc (canonical, 5-tier architecture)
- `offerings/ai-enablement/ai-connectivity-governance-framework.md` — Standalone governance framework IP (6 decision categories, decision matrix, engagement structure)
- `offerings/ai-enablement/cowork-platform-reference.md` — Cowork trajectory, backup strategies, mobile gap, Vercept/Vy intel, diagram tools, podcasts
- `offerings/ai-enablement/cowork-security-privacy-research.md` — Security/privacy research tracker (includes OAuth controls, Hyla governance gap)
- `offerings/ai-enablement/ai-enablement-advisory-deck.html` — HTML presentation derivative of WIP (needs regeneration for 5-tier architecture)
- `clients/hyla-amphibian/ty-session-prep.md` — Ty session prep (survey, security cheat sheet, checklist, outreach plan)
- `offerings/ai-enablement/cowork-setup-guide-ty.pdf` — Pre-session tips PDF (already sent to Ty)
- `offerings/ai-enablement/swot-ai-enablement.html` — SWOT analysis

**Next guinea pig targets:** Hoppin (offering sharpening call), Michael Kraus, Beth Linker. Mark Wagner after Ty's session confirms the structure works.

---

## Acquia Alumni Outreach — Sales Navigator List

Saved search in Sales Navigator: "Acquia Alumni — March 2026" (81 results, past colleague + 1st degree + 1–200 headcount filters). Six priority contacts added to Notion as Outreach tasks. Resume scrolling after John Kennedy to complete the list triage.

Priority order as of session close:
1. Michael Kraus — former VP, direct report 2.5 yrs (High)
2. Beth Linker — CPO Finite State, security peer (High)
3. John Kennedy — CEO Actual AI, Acquia Slack + Amin connection (High)
4. Chris Brookins — VP Eng Appcues, remembers Andy (Medium)
5. Bryan House — CEO Elastic Path, VC-connected (Medium)
6. Jeffrey McGuire — open invitation to reconnect, European (Medium)
