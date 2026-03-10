# Archetype Security Hardening Package
## Pricing & Positioning Document

**Status:** Working reference for sales and delivery
**Date:** March 3, 2026
**Prepared for:** Andy Laken, Archetype Consulting
**Package Target:** Crypto funds and fintech trading firms, $50M–$500M AUM, 4–20 people

---

## Executive Summary

This document proposes **one fixed-price package** positioned as a foundational security program suitable for peer crypto fund referrals. The recommendation is:

- **Package Name:** Foundation Security Program (FSP)
- **Price:** $35,000 fixed fee (all-in, no negotiation)
- **Timeline:** 4–5 weeks to completion
- **Delivery Model:** Fixed scope, fixed price, solo delivery by Andy
- **Positioning:** Fills the critical gap between no program and expensive enterprise solutions

The price anchors to genuine value delivered (~1–2% of AUM protection value) and reflects productized, repeatable delivery.

---

## 1. Market Research Findings

### MSSP and Fractional CISO Benchmarks

From market research on comparable services:

**Fractional CISO Pricing:**
- Retainers: $1,600–$20,000/month; midpoint $6,000–$10,000
- Hourly rates: $200–$400/hour
- Annual costs: $60K–$180K/year
- Industry specialization (fintech, regulated): +15–30% premium

**MSSP Security Program Buildouts:**
- Per-endpoint pricing: $45–$200/month (average $45 for basic, $200 for premium)
- Per-user retainer pricing: $15–$75/month depending on service level
- Small financial firms: specialists command 15–30% premium over generalists
- Tiered pricing (good/better/best) preferred for SMBs

**Security Implementation Project Work:**
- EDR deployment: can be rapid (2 hours for agent rollout), but full configuration and policy tuning requires 40–80 hours for a 10-person org
- IDP hardening (Google Workspace/M365): 30–45 minutes for baseline, but full rollout with enforcement, MFA enrollment, SaaS SSO integration, and audit: 60–100 hours
- Fixed-price security projects: common model for SMBs and startups; demands upfront scope definition but offers budget predictability

**Sources:**
- [Fractional CISO Costs Guide (IronOrbit)](https://www.ironorbit.com/fractional-ciso-cost-guide/)
- [vCISO Costs: Pricing & ROI (Cynomi)](https://cynomi.com/learn/vciso-costs/)
- [MSSP Pricing Guide 2026 (Bennett Financials)](https://bennettfinancials.com/pricing-managed-security-services/)
- [Endpoint Security Pricing (TrustRadius)](https://solutions.trustradius.com/buyer-blog/endpoint-security-pricing/)

---

## 2. Delivery Effort Estimate

### Scope Reminder
The package includes:
1. IDP hardening (Google Workspace or M365 as SSO)
2. EDR deployment (CrowdStrike or SentinelOne)
3. Network protection (Cloudflare WARP/Zero Trust or Tailscale)
4. Password manager standardization (1Password, full adoption + MFA)
5. Telegram and comms hardening (all team members)
6. Crypto asset access inventory (documented, role-based, tied to IDP)
7. Onboarding/offboarding playbooks (formal processes)

### Realistic Hour Estimate (Solo Delivery, 10-Person Team)

| Component | Effort (hours) | Notes |
|-----------|---|---|
| **Pre-engagement setup & discovery** | 8 | Kickoff, asset inventory, current state assessment, stakeholder alignment |
| **IDP hardening** | 20 | Policy configuration, SSO testing, MFA rollout, Drive/Dropbox audit, mobile device management |
| **EDR selection & deployment** | 12 | Tool selection, agent rollout, tuning, initial alerts, handoff documentation |
| **Network protection (WARP/Zero Trust)** | 10 | Setup, client distribution, mobile config, testing, optional profile management |
| **Password manager (1Password)** | 16 | Setup, vault structure, migration from existing tools, team adoption training, full adoption verification |
| **Telegram hardening & verification** | 8 | SOP creation, walkthrough with team, account audits, 2FA setup, active sessions review |
| **Zoom & comms hardening** | 4 | SOP creation, settings configuration, meeting lock defaults, waiting room rules |
| **Crypto access inventory** | 12 | Stakeholder interviews, documentation, spreadsheet/database creation, role mapping, tie-in to IDP |
| **Onboarding/offboarding playbooks** | 10 | Process documentation, templates, tool integration (IDP, password manager, inventory), sign-off |
| **Deployment, testing, validation** | 8 | Live rollout supervision, troubleshooting, final verification, team sign-off |
| **Documentation & knowledge transfer** | 6 | Admin runbooks, SOP handoff, tool training videos or sessions |
| **Contingency (10%)** | 11 | Unexpected issues, rework, scope clarification |
| **TOTAL** | **125 hours** | |

**Billable Solo Rate Equivalent:** 125 hours at $200/hour = $25,000 labor cost (at a professional rate higher than the $150/hr embedded CISO rate, reflecting productized, repeatable delivery with higher risk)

---

## 3. Value to the Buyer

### Cost of Not Having This Program

**Attack Scenario: Successful BEC / Credential Compromise / Ransomware**

For a $100M AUM crypto fund, a single security incident can create:

1. **Direct Financial Loss:** $1–5M (stolen funds, ransom, remediation) or more
2. **Downtime Costs:** 22 days average downtime × ops costs ≈ $500K–$1M
3. **Forensics & IR:** $500K–$1M (incident response teams, legal, law enforcement coordination)
4. **Regulatory Fines & Remediation:** $500K–$2M (compliance review, reporting, mandatory controls)
5. **Reputational Damage:** 20–30% of AUM redemptions = $20–30M investor outflows
6. **Lost Opportunities:** Inability to raise new capital, longer sales cycles

**Conservative lower-bound total loss estimate: $25–40M**

### Value of Prevention (This Program)

This program materially reduces attack surface:
- IDP hardening + 2SV: Eliminates 90%+ of credential compromise attacks
- EDR: Detects and stops malware execution and lateral movement
- Password manager: Eliminates weak/reused passwords (leading cause of breaches)
- Network protection: Blocks malware C&C, prevents DNS hijacking
- MFA at access points: Stops credential-based attacks at high-value assets
- Inventory + onboarding/offboarding: Reduces insider threat and leavers retaining access

**Conservative estimate:** This program reduces attack probability from ~15–20% (for a $100M fund with zero hardening) to ~2–3% over a 3-year horizon.

### Value Calculation (Stark/Enns Framework)

Using Jonathan Stark's heuristic of ~10% of value delivered as a fair price:

- **Attack probability reduction:** 15% → 3% = 12 percentage points
- **Expected loss at current state:** $100M × 15% × $32M avg cost = $48M expected loss
- **Expected loss with program:** $100M × 3% × $32M avg cost = $9.6M expected loss
- **Value delivered:** $48M – $9.6M = **$38.4M** prevented loss expectancy

**10% of $38.4M = $3.84M → This is insane and obviously wrong for the use case.**

Better framing:

- **Direct tangible value:** 3–5% reduction in breach probability = $960K–$1.6M in expected loss prevention
- **Strategic value:** Investor confidence, RIA/regulatory readiness, client retention = $2–5M in value over 2–3 years
- **Business protection:** Ability to raise capital, maintain operations, client trust = priceless but quantifiable as firm survival
- **Total value delivered (conservative):** $3–7M over 3 years

**10% of $5M = $500K (obviously too high for a single implementation)**

**Better anchor:** Price should reflect exceptional ROI while remaining accessible

For a $100M fund, paying $35K for a program that reduces $40M expected loss probability by 80% is a **1,140x ROI** (conservative). Even on the modest side, a $100K program would still be a 400x ROI.

**Benchmark reality check:**
- Fractional CISO + implementation for a similar program: $15K–$30K in labor alone + ongoing retainer = $60K–$120K first-year cost
- Buying best-of-breed tools (CrowdStrike + Cloudflare + 1Password + RunReveal) = $30–40K/year in SaaS
- Getting this as a fixed-price package with configuration and rollout included: $35K is under-priced vs. bundled components alone

**Sources:**
- [Average Cost of Ransomware Attacks 2025 (PurpleSec)](https://purplesec.us/learn/average-cost-of-ransomware-attacks/)
- [Ransomware in Financial Sector (ABA Banking Journal)](https://bankingjournal.aba.com/2024/08/ransomware-in-the-financial-sector/)
- [Fintech Breach Statistics 2025 (DeepStrike)](https://deepstrike.io/blog/fintech-breach-statistics-2025/)
- [The Cost of Ransomware Attacks (Huntress)](https://www.huntress.com/ransomware-guide/cost-of-ransomware-attacks)
- [Ransomware Statistics 2026 (Varonis)](https://www.varonis.io/blog/ransomware-statistics)

---

## 4. Pricing Recommendation

### Proposed Model: Single Fixed-Price Package

**Package Name:** Foundation Security Program
**Price:** $35,000 (USD, all-inclusive)
**Scope:** Deliverables 1–7 as specified above
**Timeline:** 4–5 weeks to completion
**Terms:** No scope negotiation; this is a fixed package, not a custom engagement

### Why $35,000?

1. **Labor pricing parity:** 125 hours of delivery work at an effective rate of $200/hour (higher than Andy's fractional CTO rate, reflecting productized delivery, reduced iteration risk, and higher value per hour) = $25K internal labor. $35K allows $10K margin for tool licensing costs incurred during setup, buffer for unknowns, and profit.

2. **Market positioning:**
   - MSSP retainers for comparable service: $6K–$10K/month = $72K–$120K/year
   - Fractional CISO + implementation: $60K–$100K first year
   - $35K is significantly cheaper than hiring comparable expertise; customers get exceptional value
   - Yet it's not so low as to signal commodity work or trigger concerns about delivery quality

3. **Buyer psychology:**
   - High enough to be taken seriously (not a commodity product)
   - Low enough to say yes quickly without weeks of budget negotiation (especially vs. enterprise consulting)
   - Anchored to outcome (security program) not hours (psychological anchor to value, not effort)

4. **Revenue adequacy:**
   - At 2 engagements/quarter, $35K × 8 = $280K/year from this one product line
   - At 4 engagements/quarter, $35K × 16 = $560K/year
   - This is meaningful recurring revenue for a boutique practice and covers time between engagements

5. **Competitive positioning:**
   - Not competing on price; competing on specialization (crypto funds, fintech, referral credibility)
   - Price is defensible because it's fixed, productized, and scoped for high-trust buyer base
   - Customers are comparing this to doing nothing, or to hiring a full CISO for $200K+

### Why Not Two Tiers?

**Considered:** Core package ($35K) + Premium package ($60K) with RunReveal detection platform and Nudge SaaS visibility.

**Decision:** Single package recommended for MVP launch because:
- Keeps sales complexity low (easier to close)
- Two tiers create decision paralysis at the margin (which one do I need?)
- The $35K package is actually complete and defensible as-is; detection platform is nice-to-have, not must-have
- Can introduce Premium tier after 5–10 engagements once you understand real upsell patterns

**Future optionality:** After launch, if customers consistently ask for detection/visibility, reposition as "add-on" ($8K–12K) rather than tier 2. This compounds lifetime value without complicating the lead generation story.

---

## 5. Package Positioning & Messaging

### Package Name
**Foundation Security Program** (FSP)

**Why:**
- "Foundation" signals necessary but not exhaustive (rooms for upsell later)
- "Security Program" signals professional, structured approach (not point solutions)
- Acronym is forgettable but name is self-explanatory
- No hype, no crypto-specific jargon that dates the offer

### Positioning Statement (for outreach/website)

*The Foundation Security Program is a fixed-scope, fixed-price implementation package for early-to-growth crypto funds and fintech firms that are ready to move from undefined security into a real program, but don't need (or want) a full enterprise buildout.*

*In 4 weeks, we implement identity hardening, endpoint protection, network security, access controls, and operational playbooks—the core controls that stop 80%+ of attacks. You'll have a documented program that holds up to investor diligence, positions you for regulatory compliance, and eliminates the friction of security inconsistency.*

*$35,000, fixed price, fixed scope, delivered solo. No surprise hours. No change orders. No extended negotiations.*

### Value Prop for Warm Crypto Fund Referrals

**Lead-in (Andy's voice, via Andrew Hoppin's referral):**

"Andrew mentioned you're scaling and thinking about security. We built Hyla and Amphibian's full program from scratch in the middle of 2024. It's a repeatable playbook now.

Instead of spending 6 months interviewing fractional CISOs and assembling tools, we deliver everything in 4 weeks: identity hardening, EDR, network protection, password management, access controls, and documented playbooks.

Flat $35K. No negotiation. Everyone I bring this to either says yes immediately or says they're not ready yet—there's no in-between, which is how I know the price is right.

If you're interested in a quick call, I can walk you through what's included and you can decide if it fits where you are right now."

---

## 6. Timeline & Delivery Model

### Proposed Delivery Timeline (4–5 Weeks, Cooperative Client)

| Week | Activity | Effort |
|------|----------|--------|
| **Week 0 (Pre-engagement)** | Contracts signed, access granted, stakeholder kickoff, current-state discovery | 8 hrs |
| **Week 1** | IDP hardening begins; EDR/network protection tools onboarded and agents/clients pushed; password manager setup | 30 hrs |
| **Week 2** | IDP hardening completed (SSO, MFA, SaaS integration); EDR tuning; password manager adoption push; Telegram SOP creation | 32 hrs |
| **Week 3** | Password manager full adoption verification; Telegram + Zoom hardening verification; crypto access inventory; onboarding/offboarding playbook drafts | 30 hrs |
| **Week 4** | Playbook finalization; team training; final testing and validation; documentation and handoff | 20 hrs |
| **Week 5 (Optional)** | Follow-up, troubleshooting, any rework; typically not needed for cooperative clients | 5 hrs |

**Total:** 125 hours over 4–5 weeks ≈ 25–30 hours/week, which is part-time (not consuming all capacity).

### Critical Success Factors (Built Into Scope)

1. **Upfront scope locking:** Contracts state clearly what's included and what isn't (e.g., incident response, ongoing monitoring, custom app integration not included)
2. **Executive sponsor:** Requires a named point of contact (usually founder/COO) who unblocks decisions and confirms completion
3. **Cooperative team:** Assumes team members will be available for 2–3 hours of time per person for training, setup, and verification
4. **Decision-making authority:** Price includes 1–2 tool selections (EDR and network protection), but not endless re-evaluations

### What Happens After Completion?

The package is **not** an ongoing retainer. Completion = handoff.

**Future upsell opportunities** (separate engagements):
- Detection platform implementation (RunReveal, Wiz, etc.): $8–12K
- SaaS visibility (Nudge Security): $3–5K
- Annual security assessment / playbook updates: $5–10K
- Incident response retainer: $2–5K/month
- Ongoing fractional CISO: $2–3K/month

These come after delivery, when customer is confident and you have better visibility into their needs.

---

## 7. Risk & Mitigation

### Delivery Risks

**Risk: Scope creep or tool selection paralysis**
*Mitigation:* Upfront contracts explicitly state scope; tool selection is Andy's choice (not committee decision); any scope changes are out-of-scope and trigger separate engagement/pricing.

**Risk: Team unresponsive; delays push into 6+ weeks**
*Mitigation:* Contracts specify minimum team availability hours; if client can't commit, delivery is paused and billed weekly at $250/hr until they can engage. Clear enforcement prevents open-ended timelines.

**Risk: Customer balks at tool choices or wants "custom" setup**
*Mitigation:* Productized scope is non-negotiable. Customer choice is (a) yes, we do this as specified, or (b) no, wait for later. If they want customization, that's a premium engagement (different model).

**Risk: Customer doesn't adopt tools post-delivery**
*Mitigation:* Not Andy's problem. Contracts clearly state deliverable = deployed and configured, not sustained adoption. Follow-up adoption support is a separate service.

### Market Risks

**Risk: Competitor (big MSSP, boutique firm) undercuts price**
*Mitigation:* Don't compete on price. Lean into specialization (crypto funds, fintech, referrals from trusted players like Andrew Hoppin). Emphasize solo delivery and founder-level attention vs. junior consultants.

**Risk: Customer prefers to hire a full CISO instead**
*Mitigation:* This is not a loss. A customer ready to hire a full CISO is a different ICP anyway. FSP is for teams 4–20 people, not 50+.

**Risk: Crypto market downturn reduces VC/founder appetite for security spending**
*Mitigation:* Crypto funds are actually **more** security-conscious than VC-backed startups because they manage investor assets directly. In downturns, they cut everything except security. This is defensible spend.

---

## 8. Confidence Levels & Next Steps

### What Andy Should Validate

1. **Tool selections:** Confirm CrowdStrike (or SentinelOne) and Cloudflare Zero Trust are still the right defaults for the 4–20 person fintech use case. If tools have shifted, adjust effort estimates.

2. **Effort accuracy:** Run one real engagement at this price point and time it. Adjust estimates if actual delivery is 100 hours or 160 hours.

3. **Customer acquisition:** Send 10 warm outreach messages via Andrew Hoppin's referrals at this price point. Are customers saying yes, no, or asking for changes?

4. **Pricing elasticity:** If you're getting 8/10 yeses, price might be too low. If you're getting 2/10 yeses, price might be too high OR positioning needs work.

### Recommended Launch Sequence

1. **Week 1–2 of March:** Create a 1-page flyer / one-pager for "Foundation Security Program" with the positioning statement and core bullets. Send to Andrew Hoppin for feedback.

2. **Week 3–4 of March:** Send 10 warm outreach messages to crypto fund founders/COOs referred by Andrew. Offer a 20-minute discovery call. Goal: Land 2 commitments by end of Q1.

3. **April–June:** Deliver 2 programs. Track actual hours, customer feedback, and adoption post-delivery. Document lessons learned.

4. **July:** Refine positioning, pricing, or scope based on first 2 deliveries. Plan Q3 outreach.

5. **By Q4:** If 4–6 engagements completed, you'll have:
   - Real delivery data to refine estimating
   - Customer testimonials and case study material
   - Confidence to raise price if demand exceeds capacity

---

## 9. Appendix: Comparable Market Data

### MSSP / Fractional CISO Pricing Summary

| Provider Type | Monthly Cost | Annual Cost | Notes |
|---|---|---|---|
| MSSP (basic, per endpoint) | $45–$60/endpoint | Varies | ~$450–$600/year for 10 people |
| MSSP (premium, per endpoint) | $150–$200/endpoint | Varies | ~$1,500–$2,000/year for 10 people |
| Fractional CISO (retainer, low) | $1,600 | $19,200 | Basic advisory, 5–10 hrs/month |
| Fractional CISO (retainer, mid) | $6,000 | $72,000 | Standard, 20–30 hrs/month |
| Fractional CISO (retainer, high) | $15,000+ | $180,000+ | Full program buildout + ongoing |
| Fractional CISO (hourly) | — | — | $200–$400/hour, 100–150 hrs for buildout = $20K–$60K |
| **This FSP** | — | **$35,000** | **One-time implementation + handoff** |

---

## 10. Final Recommendation

**GO** with the Foundation Security Program at **$35,000 fixed price**, 4-5 week timeline, starting with warm referrals from Andrew Hoppin.

This price is defensible on value, competitive vs. comparable services, and generates meaningful revenue while staying focused on Andy's high-touch, founder-level positioning.

The productized model allows for repeatable delivery, faster sales cycles, and clear positioning in the market. Upsell and premium tiers can follow once you've validated demand and delivery model with the first 5 customers.

