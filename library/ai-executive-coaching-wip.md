# AI Executive Coaching — Offering WIP

*Work in progress. Update as the offering takes shape through real sessions.*

---

## What This Is

Security-aware AI enablement for executives handling sensitive data. Andy evaluates the client's information risk profile, configures agentic AI tools (starting with Claude Cowork) with appropriate privacy and security controls, and builds working workflows on their actual data — email, calendar, notes, task management. They walk away with a system that's both productive and defensible, plus a written security brief they can hand to their board, investors, or compliance team.

This is not "help you set up an app." It's "make sure you adopt AI without exposing your firm."

**Working name:** TBD — "AI Enablement Advisory" / "Executive AI Enablement" / something that signals advisory, not tutoring. Avoid "coaching" and "setup" — both pull toward lower-status framing.

**Format:** 90-minute initial session (remote or in-person), structured as assessment + configuration + demonstration. Follow-on engagement likely for most clients — either a monthly retainer or a scoped firm-level project.

**Price point:** Needs rethinking (see Positioning & Pricing section below). $500/session as a transaction feels like a service call. A $2,000–2,500/month retainer that *starts* with a hands-on session feels like an advisory relationship. Guinea pig sessions are free regardless — the goal is learning, not revenue.

---

## Why Now, Why Me

Agentic AI tools are crossing into the mainstream — Claude is the #1 app in the US, Cowork just launched on Windows, CNBC is writing about it for a general business audience. Every executive is hearing about this. The ones who handle sensitive data (fund managers, fintech founders, healthcare, legal) face a specific problem: they can see the productivity gains, but they can't evaluate the information risk. Their options are (a) dive in and hope for the best, (b) wait for their IT department to figure it out (which won't happen at a 15-person fund), or (c) find someone who understands both the technology and the risk.

Andy is option (c). The differentiator isn't "I can set up Cowork" — anyone with a YouTube subscription can learn that. The differentiator is the security evaluation that wraps around the setup:

**What Andy brings that a tutorial can't:** 20+ years in enterprise IT and security. Direct experience evaluating EDR vendors, data privacy architectures, and access control models (see: Huntress/SentinelOne evaluation, FSP offering development). Deep knowledge of Anthropic's specific privacy architecture — consumer vs. commercial terms, connector permission models, data retention policies, prompt injection attack surfaces. Daily Cowork power user who has already mapped the real-world risks. PM/Scrum background that translates technical risk into business language executives actually understand.

**The positioning in one sentence:** "I'm not teaching you how to use an AI tool. I'm making sure your adoption of AI doesn't create a liability for your firm — and showing you how powerful it is in the process."

---

## Target Audience

**Primary:** Senior operators, founders, and fund managers who are AI-curious but haven't made the leap to agentic workflows. Already using ChatGPT or similar conversationally. Smart, busy, would pay to skip the learning curve.

**Profile:**
- Founder/CEO/COO/CIO at a 5–50 person company
- Or GP/partner at an investment fund
- Already using LLMs casually (ChatGPT, Gemini)
- Hasn't set up Cowork or agentic tools
- Values time over money — would rather pay $500 than spend 10 hours figuring it out

**Not the target:** Tech-forward people already deep in Claude, developers, AI enthusiasts who watch every YouTube tutorial. They don't need this.

---

## Market Research — ICP Validation (March 2026)

*Pressure-tested the ICP hypothesis with web research. Summary of confirming and disconfirming signal below.*

### Confirming Evidence

**The onboarding gap is real and documented.** Anthropic's own products ship with minimal guided onboarding — Cowork drops you into a sandbox with connectors available but no structured walkthrough. Multiple user reports and reviews confirm that the gap between "I installed this" and "this is running my workflow" is where most people stall. The 93% stat from executive AI adoption surveys (BCG, Microsoft Work Trend Index) consistently identifies human factors — setup friction, unclear use cases, trust concerns — as the primary barrier, not the technology itself.

**Willingness to pay exists.** The market for AI coaching/consulting for non-technical executives is emerging but real. Comparable offerings (Eesel AI onboarding, fractional AI consultants, executive AI coaching) price at $200–500/hour for individual sessions. Andy's $500/session is market-rate, not aspirational.

**The "show, don't tell" gap.** YouTube and Substack are full of Cowork tutorials, but they're generic. Nobody is doing personalized setup on someone's actual email, calendar, and workflow. The difference between watching a demo and watching your own meeting prep brief generate from your own calendar is the "holy shit" moment that tutorials can't replicate.

**Security credibility is a genuine differentiator.** Multiple sources confirm that data privacy is the #1 concern among executives evaluating AI tools. Most AI coaches and consultants hand-wave on this. Andy's ability to walk through the actual data flow (consumer vs. commercial terms, connector permissions, prompt injection risks) — and hand over a one-pager — is rare in this market.

### Disconfirming Evidence & Risk Factors

**Free content competition is increasing rapidly.** Anthropic is investing in documentation, and the YouTube/creator ecosystem around Cowork is growing. The window where "nobody explains this well" is narrowing. This argues for speed — launch now, build testimonials before the market catches up.

**Platform dependency.** The offering is tightly coupled to Claude Cowork, which is a research preview product. Platform instability (bugs, breaking changes, feature removals) could undermine session quality. See the Platform Contingency section under Platform Validation for detailed scenario planning and mitigation strategy.

**macOS only (for now).** Cowork requires macOS. This excludes a meaningful chunk of the executive population, particularly in industries where Windows is standard (finance, healthcare, legal). Worth noting in pipeline conversations — don't waste time on Windows-only prospects.

**VP/Director expansion is problematic.** The hypothesis that the ICP could expand beyond C-suite to VP/Director level is weak. VPs and Directors are less likely to have purchasing authority for personal productivity tools, more likely to need org-wide approval, and more likely to expect their company to provide AI training. The sweet spot remains founders, GPs, and C-suite who control their own spend.

### Refined ICP (Post-Research)

The research confirms the primary ICP but tightens it:

- **Strongest fit:** Founders, GPs, and C-suite at 5–50 person firms on macOS, already using LLMs casually, handling sensitive data (financial, client, deal flow), willing to pay personally
- **Secondary fit:** COOs and Chiefs of Staff who are de facto "figure out the AI thing" owners at their firms
- **Weak fit:** VPs/Directors (purchasing friction), Windows-only shops (platform constraint), anyone already deep in Claude (they don't need this)
- **Expansion path:** Individual sessions → "do this for my team" → org-level AI enablement engagement ($10–20K)

### Competitive Landscape

The market is early. Direct competitors doing personalized Cowork setup sessions for executives are essentially nonexistent as of March 2026. Adjacent competition includes:

- Generic AI consultants offering "AI strategy" workshops (broad, not hands-on)
- YouTube/Substack creators doing Cowork tutorials (free, not personalized)
- Anthropic's own onboarding improvements (coming, but slow and generic)
- IT departments at larger firms (irrelevant for the 5–50 person ICP)

The window is open. The question is how long it stays open.

### Platform Validation — Is Cowork the Right Bet? (March 2026)

**Short answer: Yes, for now.** Cowork is the only agentic AI product that combines local file access, MCP connectors (email, calendar, task management), and a sandboxed security model — all in a consumer-accessible package. The competitive landscape as of March 2026:

- **OpenAI ChatGPT Desktop:** Conversational + screen sharing, but no equivalent file/connector architecture. Operator is web-only (browser tasks, not local workflows).
- **Microsoft Copilot:** Evolving toward autonomous agents (Copilot Tasks launched Feb 2026), but deeply embedded in M365 stack. Enterprise IT deployment, not founder self-service. 12-18 months from reaching the 5-50 person firm ICP.
- **Google Workspace Studio:** Closest architectural competitor — Gemini-powered agents inside Gmail/Drive/Chat, no coding required. GA on all Business/Enterprise Workspace plans as of March 2026. Worth monitoring closely, but Google-ecosystem-only and no local file access.
- **Other platforms (Kore.ai, Sierra, Moveworks):** Enterprise-grade, developer-oriented, or customer-service-focused. Not competing for the same buyer.

**Key developments since initial research:**
- **Windows support launched Feb 10, 2026** — full feature parity with macOS. The platform constraint from the original ICP analysis is eliminated.
- **Mainstream media coverage** (CNBC, VentureBeat) positions Cowork as "for the average office worker," not just developers.
- **SaaS stocks dropped 15-33%** after Cowork enterprise announcements — Wall Street is pricing this as category-defining.
- **Enterprise traction:** Adobe, Dentons cited as early adopters. Anthropic says ~80% of revenue is enterprise.

**The real risk** isn't another product displacing Cowork — it's Anthropic improving Cowork's own onboarding to the point where executives don't need coaching. Current signal: the onboarding gap is still wide (no guided setup, token consumption confusing, key features like Projects/Memory don't work in Cowork yet). This gap is unlikely to close in <6 months.

**Strategic framing:** The offering is "executive AI enablement." Cowork is the current best vehicle, not the permanent identity. If the platform landscape shifts, the advisory skills and client relationships transfer.

### Platform Contingency — How to Stay Agnostic Without Going Broad

Cowork is the primary platform. Full stop. Clients get configured on Cowork, workflows get built in Cowork, the security brief evaluates Cowork's architecture. Splitting attention across platforms during a session would be confusing and dilute the value.

But the offering should survive a platform shift. Practical guardrails:

**Monitor continuously:** Keep active tabs on Google Workspace Studio (closest competitor, GA on Business plans, Google-ecosystem-only), Microsoft Copilot Tasks (enterprise-first but trending toward SMB), and any new entrants. Spend 30 minutes per week testing competitor updates firsthand. If a competitor reaches feature parity with Cowork's local-file + MCP connector model, evaluate whether to add it as a supported platform.

**Name and frame platform-agnostically.** "AI Enablement Advisory" works regardless of which tool is underneath. Avoid building the brand identity around Claude or Cowork specifically. Marketing can reference Cowork as the current recommended tool without making it synonymous with the offering.

**Build transferable session structure.** The session arc (security evaluation → connector configuration → live workflow demo → written brief) works on any agentic platform. The security brief template should include a section on platform selection rationale so clients understand *why* Cowork, which also makes a future platform migration feel like a natural advisory recommendation rather than a pivot.

**Scenario planning:**
- *Cowork has a major privacy incident or extended outage:* Pause sessions, notify active clients with risk assessment, evaluate alternatives. The security-first positioning means being first to flag a problem strengthens credibility rather than undermining it.
- *A competitor reaches parity and gains market share:* Add as a second supported platform. The advisory value (security evaluation, workflow design, information governance) is platform-independent. Configuration specifics change; the engagement structure doesn't.
- *Anthropic improves onboarding dramatically:* The security evaluation and written brief remain valuable even if setup friction disappears. Shift emphasis from "help you get started" to "make sure what you're doing is defensible." The self-serve user who set up Cowork alone still hasn't had anyone evaluate their data exposure.
- *Cowork exits research preview and ships breaking changes:* Stay current, update session materials weekly. Being the person who understands what changed and what it means for existing configurations is itself valuable advisory work.

---

## Initial Guinea Pigs (Free Sessions)

| Person | Context | Status |
|---|---|---|
| Ty Shinn (GP, Hyla Funds) | Explicitly asked for help setting up Cowork on Wednesday's team call. Wants "safe setup guidance" and "ring-fenced approach." | **Booked for Tuesday March 10.** Pre-session Tally survey ready to send. Session prep doc: `ty-session-prep.md` |
| Mark Wagner (GP, Hyla Funds) | Interested in AI agent marketplace, hasn't committed yet. "Everything's been marked down." | Offer after Ty's session |
| Andrew Hoppin (CIO, Hyla) | Already a Cowork convert, 10x productivity claim. Session with him is more about sharpening the offering than onboarding. | Schedule a call to discuss his workflows and get his input on the offering |

**Goal from guinea pig sessions:** Validate the session structure, identify the "oh wow" moments, learn what people actually need vs. what I assume they need, generate testimonials.

---

## Pipeline — Where Clients Come From

**Primary channel: LinkedIn**
- Andy's network from 20+ years in tech (Acquia alumni, former colleagues now VPs/founders)
- Strategy: 3–5 posts per week showing real Cowork workflows (not selling, demonstrating). "Here's what happened when I connected Granola to Claude and asked it to prep me for my next meeting."
- Let people come to you. Posts generate DMs. DMs generate sessions.

**Secondary: Warm referrals**
- Ty and Mark tell other fund managers
- Hoppin mentions it to his network
- Existing Amphibian/Hyla team members spread the word

**Tertiary: Andrew's Telegram intros**
- The crypto fund managers Andrew can intro to may want this as a lighter entry point before (or instead of) a full security engagement

**Not primary channel (yet):** Cold outreach, paid ads, content marketing beyond LinkedIn. Keep it simple at launch.

---

## LinkedIn Strategy

**Content approach:** Show, don't sell. Each post demonstrates a specific workflow or result.

**Post types:**
- "Here's what happened when I..." — workflow demos with real (anonymized) results
- Commentary on AI/Cowork news (ride the wave of Claude being #1 app)
- Before/after: "This used to take me 45 minutes. Now it takes 3."
- Lessons learned: "The three things executives always ask about when setting up AI tools" (privacy, what to connect, how to prompt)

**Frequency:** 3–5x per week during launch push. Can reduce to 2–3x once sessions are flowing.

**CTA:** Not "book a session" — more like "DM me if you want to see this on your own workflow." Let the conversation start naturally.

---

## Website Updates Needed?

**Maybe, but not blocking.** The current site positions Andy as a fractional CTO focused on security + AI + infrastructure. AI executive coaching fits under the AI pillar. Options:

- Add a section or subpage for the coaching offering once it's validated
- Or keep it as a LinkedIn-driven offering for now and add to the site after 5–10 paid sessions

**Don't let website updates slow down outreach.** The offering sells through LinkedIn posts and direct conversations, not through a landing page (yet).

---

## Session Structure (Draft v1)

*See separate document for detailed session outline. Summary:*

**Pre-session (15 min async):** Quick questionnaire — what tools do you use daily? What takes the most time? What have you tried with AI so far?

**Part 1 — Setup & Security (20 min):** Install/configure Cowork. Connect Gmail and Calendar. Walk through what each connector can see, what it can do, what requires confirmation. Address privacy/ring-fencing questions directly.

**Part 2 — The "Holy Shit" Workflow (25 min):** One high-impact workflow on their real data. For most people: pull tomorrow's calendar, grab email context for each meeting, generate a meeting prep brief. They watch it happen live on their actual schedule.

**Part 3 — Two More Use Cases (20 min):** Tailored to what they said in the pre-session questionnaire. Email triage, weekly summary, draft responses, research synthesis — depends on the person.

**Part 4 — Handoff (15 min):** Cheat sheet of prompts for their specific workflows. How to ask Cowork for help when stuck. Set expectations for the learning curve.

---

## Relationship to Other Offerings — The Escalation Model

The individual session is a **front door**, not the whole house — but the front door needs to be built so the hallway is visible.

When you sit with a GP for 90 minutes, configure their tools, and hand them a security brief, you've done something no one else in their world has done: you've demonstrated both technical depth and executive communication in a single interaction. That combination is what makes the escalation natural rather than salesy. They don't need to be upsold — they'll ask.

**Designed escalation paths:**

The security brief itself creates the opening. When you hand someone a document that says "here's what your current setup exposes, here's what we locked down today, and here's what a firm-level assessment would cover," the next conversation writes itself. Specific paths:

- "Can you do this for my team?" → Firm-level AI enablement engagement. Assess the org's tools, configure Cowork/agents for each role, establish information governance policies, train the team. $10–20K scoped project.
- "We have an app being built with AI and no one's reviewed it..." → Vibe coder stabilization. Code audit, architecture review, spec-driven development transition. (Elijah Parker archetype.)
- "Our investors/board are asking about our AI security posture..." → The "Show Me the Carfax" play. Security assessment as a due diligence deliverable. Reframes security from cost center to credentialing.
- "We've been wanting to go AI-first as a company..." → Full AI operations engagement. Strategic roadmap, tool selection, workflow design, change management. (Amphibian archetype, James Hodges proposal.)

**Why the security framing makes escalation work:** A "productivity coaching" session ends when the tools are set up. A "security-aware AI enablement" session surfaces risks that extend beyond the individual — firm data policies, team access controls, vendor evaluation, compliance posture. Those risks don't resolve in 90 minutes. They require follow-on engagement. The security lens naturally generates scope that the productivity lens doesn't.

**Revenue model:** The session itself generates modest revenue ($500–750 or equivalent retainer fraction). Its primary economic function is pipeline generation for $5K–$50K engagements, paid for by the trust and visibility earned during the hands-on session. This is a dramatically cheaper and more effective pipeline strategy than cold outreach or content marketing for larger engagements.

---

## Offering Tiers — Individual to Firm

The offering has two distinct tiers. The individual session stands alone and sells to any executive regardless of firm context. The team/firm tier is the upsell — and it's where the real revenue lives. Both are needed: the individual session generates pipeline and trust; the firm engagement generates revenue and case studies.

### Tier 1: Individual AI Enablement Session

Standalone engagement for any executive. Works whether or not their firm adopts. This is the front door.

**Core use cases (demonstrate in every session):**

*Meeting prep brief* — the anchor demo. Pull tomorrow's calendar, grab email context for each attendee, surface prior meeting notes (Granola or equivalent), synthesize into a one-page brief. This is the "holy shit" moment because it touches data the client already has but isn't using. Every executive has meetings; every executive is underprepared for at least half of them.

*Email triage and draft responses* — not "AI reads all your email" (triggers privacy alarm) but "here's what needs your attention today, here's what can wait, here are draft responses for the three that matter." The security conversation is natural here: configure permissions, explain what the connector sees, walk through the confirmation model.

*Scheduled daily briefing* — a morning digest generated automatically: portfolio company news, LP email summary, calendar prep for the day, or whatever the client's domain requires. This is where scheduled tasks come in. It's sticky — once someone has a daily briefing appearing in their workflow, they don't want to lose it. It also demonstrates that Cowork isn't just reactive; it works for you while you sleep.

*Domain-specific research synthesis* — tailored per client. A fund manager staying current on a sector. A founder prepping for investor conversations. A COO tracking competitor moves. Cowork pulls from email threads, saved docs, meeting notes and produces a synthesis. Higher-touch to configure, but high perceived value.

**Deliverable:** Written security/privacy brief (see template — to be built). Documents what was configured, data exposure profile, ring-fencing level, firm-level recommendations, and open risks. This is the artifact that makes it an advisory engagement, not a tutoring session.

### Tier 2: Team/Firm AI Enablement

Scoped engagement for firms with 3+ people adopting Cowork. This is where individual workflows connect into team information architecture. Priced as a project ($10–30K depending on scope), not per-session.

**The insight:** Individual Cowork sessions are powerful, but the real transformation happens when multiple people's AI workflows connect — when one person's output becomes another person's input, and the firm's collective knowledge becomes queryable. Designing that information flow is systems architecture work, priced accordingly.

**Team-level use cases:**

*AI notetaker standardization* — most teams have a balkanized mess: one person on Otter, one on Granola, one taking notes by hand. Meeting intelligence lives in different formats, different tools, inaccessible to anyone who wasn't in the room. Standardizing on one tool (likely Granola, given Cowork integration) and establishing a shared knowledge base that everyone's Cowork can query is a concrete, high-value deliverable. Scoped as: tool selection, configuration, team training, workflow integration. This is a wedge into the broader engagement.

*Shared document intelligence via Drive connector* — individual Drive connection lets you query your own docs. The team play is shared folders — deal memos, investment committee notes, portfolio company reports — becoming queryable by anyone on the team through their Cowork session. The security conversation here is real and valuable: who should have access to what, how do you ring-fence partner-only materials from junior analysts, what are the information governance policies. This is exactly the kind of problem a YouTube tutorial can't solve. It requires someone who thinks about access control, organizational hierarchy, and data classification — CTO-level thinking.

*Team briefing workflows via scheduled tasks* — each team member produces a weekly briefing on their area of responsibility, generated by Cowork from their email, meeting notes, and Drive docs using scheduled tasks. Those briefings get shared (Slack channel, shared Drive folder, Notion) and become inputs for the firm-wide weekly meeting. Each person's AI does individual work that feeds a team workflow. You're designing an information architecture, not setting up an app.

*Cross-tool orchestration* — connecting the individual workflows: Granola notes → Drive → Slack summaries → task tracking. Within Cowork's current capabilities, designing how information flows between people's individual AI sessions is genuine systems design. Eventually this extends to n8n or similar automation tools, but the architectural thinking starts here.

**Why Hyla is the perfect testbed:** Hoppin is already evangelizing Cowork internally. Ty and Mark are ready for individual sessions. If you get 3-5 people at the firm actively using Cowork, you have a live environment to prototype every team-level workflow above — and a case study to sell firm-level engagements elsewhere. The merger adds urgency: post-merger, the combined firm will need standardized tools, shared knowledge bases, and information governance. You can be the person who builds that.

**Important caveat:** Keep the individual offering clean and standalone. The team-level use cases should inform how you *think* about the escalation, but they shouldn't leak into the pitch for individual sessions. A solo founder at a 6-person fund doesn't need to hear about team briefing workflows — they need their morning meeting prep brief to work. The team tier sells itself naturally when a client says "can you do this for my team?" Don't lead with it.

---

## Positioning & Pricing — The Status Problem

**The concern:** A one-off "setup session" risks positioning Andy as a service provider rather than an advisor. A two-to-four-week security transformation commands authority because it implies "you have a problem you can't solve yourself." A 90-minute coaching session, poorly framed, implies "I'll save you time" — which is a convenience play, not an authority play.

**The fix is framing, not format.** The session structure stays roughly the same. What changes is how it's described, priced, and what it delivers:

1. **Lead with security, not productivity.** The opening conversation isn't "let me show you cool AI tricks." It's "let me evaluate what connecting your email and calendar to an AI agent actually exposes, and configure it so you're protected." The productivity demo happens *after* the security setup — as proof that doing it right doesn't mean doing less.

2. **Deliver a written artifact.** Every session ends with a security/privacy brief: what was configured, what the data exposure profile looks like, what the client's plan should cover at the firm level, and what's still open. This is a professional deliverable, not a receipt. It's also the document that generates the follow-on conversation.

3. **Price as a relationship, not a transaction.** Options to explore:
   - **Monthly retainer:** $2,000–2,500/month, 3-month minimum. Includes initial hands-on session + ongoing advisory (2–3 check-ins/month, async support, security brief updates as the platform evolves). This is the strongest status signal — you're a retained advisor, not a hired hand.
   - **Engagement pricing:** $1,500–2,000 for a "Personal AI Security & Enablement Assessment" — scoped as a mini-engagement (session + brief + one follow-up), not as an hourly rate. Feels like a project, not a service call.
   - **Session pricing (fallback):** $750/session if the market resists engagement pricing. Still professional-services range, but less ideal for positioning.
   - **Guinea pig sessions remain free.** The goal is learning and testimonials, not revenue.

4. **Name it like an advisory service.** Avoid "coaching," "setup," "training," and "tutorial." Candidates: "AI Enablement Advisory," "Executive AI Security Assessment," "AI Workflow & Risk Advisory." The name should make a CEO feel like they're hiring a strategist, not booking a tutor.

**The litmus test:** Would a fund manager mention this engagement to their co-GP or board without feeling like they need to justify it? "I brought in an AI security advisor to evaluate our tools and set up our workflows" passes. "I hired someone to help me set up Claude" doesn't.

---

## Open Questions

- [ ] **Pricing model decision:** Retainer vs. engagement vs. per-session? Test with guinea pigs, but decide the *framing* before outreach starts. The retainer model ($2,000–2,500/month) is the strongest positioning play but may be a harder initial sell. The mini-engagement model ($1,500–2,000 for assessment + session + follow-up) might be the right entry point.
- [ ] **Offering name:** Needs to be decided before LinkedIn content starts. Current candidates: "AI Enablement Advisory," "Executive AI Security Assessment," "AI Workflow & Risk Advisory." Run past Hoppin for reaction.
- [ ] **Security brief template:** Build this before the first guinea pig session. It's the key deliverable that separates this from a tutoring session and creates the follow-on conversation. What goes in it? (Ring-fencing level, connector permissions configured, data exposure profile, firm-level recommendations, open risks.)
- [ ] **Branding:** Does this live under Archetype Consulting or does it need its own identity? Leaning toward keeping it under Archetype — the security credibility of the parent brand is the whole point.
- [ ] **Tools beyond Cowork:** When do I introduce n8n, OpenClaw, other agentic tools? Probably not in v1 — keep it focused on Cowork. But the offering name should be platform-agnostic so it can expand.
- [ ] **Recording/screenshots:** Can I record sessions (with permission) for testimonial clips or LinkedIn content?
- [ ] **Cal.com booking:** Set up a specific booking type for this offering?

---

## Immediate Next Steps

1. ~~Message Ty to schedule first guinea pig session~~ **DONE — booked for Tues March 10**
2. Call Hoppin to learn his top 3 daily Cowork workflows and get input on the offering
3. Complete security/privacy research (see security-privacy-research.md)
4. Do 2–3 free sessions, refine the structure
5. Write first LinkedIn post showing a real Cowork workflow
6. Start charging after guinea pig sessions are done and structure is validated

---

*Last updated: March 8, 2026*
