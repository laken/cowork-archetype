# Ty Shinn Session Prep — Tuesday, March 10, 2026

*Everything Andy needs to build the survey, prep for the session, and expand the guinea pig pipeline.*

---

## 1. Tally Survey — Ready to Build

**Title:** "Quick Background — Before Our AI Session"
**Intro text:** "Takes ~5 minutes. Helps me make Tuesday's session immediately useful rather than generic."

| # | Question | Type |
|---|---|---|
| 1 | What Claude plan are you on? | Single select: Pro / Team / Max / Haven't signed up yet / Not sure |
| 2 | Have you used Claude's Cowork mode? (This is the desktop mode that can connect to your email, calendar, and files.) | Single select: Yes / I have Claude desktop but haven't tried Cowork / I don't have Claude desktop yet |
| 3 | What tools do you use daily for work? | Multi-select + Other: Gmail, Google Calendar, Slack, Notion, Granola, CRM, etc. |
| 4 | Walk me through a typical work morning, from when you open your laptop to your first meeting. | Long text |
| 5 | What types of sensitive information do you work with, and what concerns do you have about connecting that data to AI tools? | Long text |
| 6 | Does your firm have any compliance requirements or data handling policies I should know about? | Short text |
| 7 | If Tuesday's session goes well, what does "success" look like for you? | Long text |

**Send with:** "Looking forward to Tuesday. Quick survey so I can make the session actually useful rather than generic — takes 5 min."

---

## 2. Security Cheat Sheet — What to Know Cold

### The Three Things Ty Will Ask About

**A) "What happens to my email data?"**
- MCP connectors fetch on demand; data isn't cached by the connector
- Content that enters the conversation IS retained (30 days if training is off)
- Email content does pass through Anthropic's servers for LLM processing — don't claim otherwise
- Training opt-out is available and verifiable; incognito chats are never retained
- Key gap to acknowledge: exact handling in transit and at rest is not fully documented

**B) "Ring-fencing" (his exact word from the team call)**
- Your 4-level framework is solid (Minimal → Selective → Full productivity → Enterprise)
- For Ty specifically: probably Level 2 or 3
- Teaching moment: his Mac Mini "oasis" idea conflates Cowork with OpenClaw
  - Cowork: sandboxed VM + per-connector permissions. Risk surface = data flowing through connectors to Anthropic
  - OpenClaw: full system access. Dedicated hardware is a legitimate security practice there
  - The ring-fencing for Cowork is about *which connectors you enable and what your privacy settings are*, not which hardware you're on

**C) Consumer vs. Commercial terms — your best credibility moment**
- Team plan is under Consumer Terms, same as Pro. Does NOT get enterprise-grade privacy protections
- If Hyla is on Team, flag it. If Ty is on Pro, the opt-out toggle is the critical action item
- The opt-out toggle in Privacy Settings: every client should verify it's off if handling sensitive information

### What to Study Before Tuesday

- Reread security doc sections 1 (email data flow), 2 (consumer vs. commercial), and 7 (ring-fencing framework)
- Prompt injection section (Category 3) — probably won't need for Ty, but demonstrates depth if conversation goes there
- Find out what plan Ty is on before the session (survey Q1 handles this)

### Gaps to Acknowledge, Not Paper Over

- Calendar data specifics (what exactly does the connector pull?) — still unresearched
- Granola transcript flow through Claude — open question
- Prompt injection is a real risk you can name and explain, but defenses are evolving

---

## 3. Guinea Pig Expansion — Outreach Plan

### Immediate (warm, already in context)

**Mark Wagner** (GP, Hyla) — Offer after Tuesday's session goes well. Don't jump the gun.

**Andrew Hoppin** (CIO, Hyla) — Different framing. He's already a Cowork convert. Session with him is about sharpening the offering, not onboarding. Schedule a call this week to pick his brain on workflows and get his reaction to the offering name/positioning.

### Acquia Alumni (Sales Navigator list)

Recommended next 2 guinea pigs from the list:

1. **Michael Kraus** (former VP, direct report 2.5 yrs) — Strongest personal relationship. Framing: "I'm building something new and you're one of the first people I want to test it with."
2. **Beth Linker** (CPO, Finite State) — Security peer. Framing: "You'd get value from this AND your feedback on the security framing would be invaluable."

Other contacts for later waves:
- **John Kennedy** (CEO, Actual AI) — Already building an AI company. May be too technical for the offering but strong for referrals.
- **Chris Brookins** (VP Eng, Appcues) — Engineering leader. Better as referral source unless managing non-technical staff.
- **Bryan House** (CEO, Elastic Path) — VC-connected. Good guinea pig if AI-curious. The VC network is the real value.
- **Jeffrey McGuire** — Open invitation to reconnect. European timezone complicates scheduling.

---

## 4. Tuesday Prep Checklist

### This Weekend
- [ ] Build Tally survey (10 min) and send to Ty
- [ ] Reread security doc sections 1, 2, 7
- [ ] Send outreach to Hoppin for a "sharpen the offering" call
- [ ] Send outreach to 1–2 Acquia alumni (Kraus and/or Linker)

### Monday
- [ ] Review Ty's survey responses
- [ ] Prepare his session based on answers (which connectors, which demo workflows, which security conversation)
- [ ] Have the security brief template at least outlined (structure shows professionalism even for a guinea pig)

### Tuesday (Session Day)
- [ ] Session: security eval → connector config → live workflow demo → brief handoff
- [ ] Take notes on what lands, what falls flat, what he asks that you didn't expect
- [ ] After: write up lessons learned, update the WIP

---

*Created: March 8, 2026*
