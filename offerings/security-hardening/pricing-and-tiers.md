# Archetype Security Hardening — Pricing & Package Tiers

*Internal working document. March 2026.*
*Pricing research sourced from: PRICING_RESEARCH_CRYPTO_FUNDS.md (March 2026)*

---

## The Market Context (What Clients Can Actually Spend)

Before the tiers: what do these firms actually have?

A $100M AUM crypto fund on a 2% management fee generates $2M in annual revenue. After operating expenses — prime brokerage, compliance, fund administration, salaries for 4–20 people — discretionary spend is roughly $200K–$400K. Security is not a line item they budget for proactively. It enters the conversation through one of three pressure points:

**Regulatory pressure:** The SEC's cybersecurity risk management rule (final June 2025, compliance expected early 2026) requires registered investment advisers to have documented security programs. The October 2026 Form PF deadline adds reporting teeth. Neither mandates specific tools, but both create audit exposure for funds with nothing documented.

**Investor pressure:** 68% of institutional allocators cite cybersecurity as their primary concern in crypto risk management. Operational due diligence questionnaires now ask directly: do you have EDR on all endpoints? Is MFA enforced? Who implemented your controls? A weak answer costs deals.

**Incident pressure:** The Hyla infection happened. The Stardust Chollima / Lazarus Group threat is documented and active. Some clients have already been hit or know someone who has.

**Decision authority:** At the target firm size, the $10K–$35K range is approvable by a COO or operating partner without board friction. Above $50K typically requires investment committee sign-off. This matters for tier design.

**Comparable market pricing:**
- vCISO / fractional CISO retainer: $6K–$12K/month ($72K–$144K/year)
- MSSP managed security for a 10-person firm: $72K–$120K/year
- Boutique hardening implementation (assessment + build): $30K–$75K one-time
- Archetype is a one-time fixed fee, positioned below annual MSSP cost, at the lower end of boutique implementation

---

## The Three Tiers

---

### Tier 1 — The Hyundai
**"Security Foundation"**
**Price: $12,000 fixed**
**Timeline: 1 week (3–4 sessions)**
**Ideal client: Sub-$50M fund, or a fund that needs to show something to an investor/auditor fast**

This is triage, not transformation. One week, four focused deliverables. No EDR deployment, no ongoing managed layer — just the highest-leverage controls that can be implemented quickly and documented cleanly.

**What's included:**

*IDP hardening (Google Workspace or M365):*
- SSO enforcement across company-connected SaaS
- MFA enforced org-wide
- Admin access audit and tighten
- Sharing permissions review (Drive / SharePoint)

*Password manager deployment:*
- 1Password or Bitwarden org setup
- Team onboarding + vault structure
- Migration of shared credentials out of Slack/email

*Telegram and Zoom hardening:*
- SOPs for both platforms (crypto-specific threat patterns)
- Settings audit and configuration

*Documentation package:*
- Written summary of controls implemented
- Suitable for investor DDQ or SEC examination response

**What's NOT included:**
- EDR (no endpoint agent deployed)
- Network protection layer
- Incident response capability of any kind
- Crypto asset access inventory
- Ongoing monitoring or support

**Who this is for:** A fund that has essentially nothing and needs to demonstrate basic hygiene fast — regulatory deadline, investor request, or pre-fundraise cleanup. This is not a security program; it's a defensible foundation. Honest framing to the client: "You will be meaningfully more secure than you were. You will not be protected against a sophisticated, targeted attack."

**Andy's margin:** Estimated 20–25 hours delivery. At $12K, that's ~$480/hour effective rate. Clean, fast, repeatable. Risk: scope creep if the IDP situation is worse than expected.

---

### Tier 2 — The Jetta
**"Security Essentials"**
**Price: $22,000 fixed**
**Timeline: 2 weeks (6–8 sessions)**
**Ideal client: $50M–$150M fund, BYOD, no current security program, one investor or regulatory conversation already prompting action**

The full IDP and identity layer plus network protection and EDR deployment. No managed SOC — the client owns the console after handoff. This is a real security program, not just compliance theater, but it leaves incident response ownership explicitly with the client or a named third party.

**What's included:**

Everything in Tier 1, plus:

*Endpoint Detection and Response (SentinelOne Singularity Control):*
- Agent deployment across all work devices (BYOD)
- Configuration and policy setup
- Client training on console basics
- Named escalation path documented (SentinelOne included IR hours)

*Network protection (Cloudflare WARP / Zero Trust):*
- DNS filtering deployed across all devices
- Malicious domain blocking active
- Zero Trust policy baseline configured

*Onboarding/offboarding playbook:*
- Written procedure for adding/removing team members
- Covers IDP, password manager, EDR, and network protection

*Privacy disclosure document:*
- Plain-English explanation of what each tool sees and who holds the keys
- Delivered to all team members before deployment
- Honest framing of trust relationships

**What's NOT included:**
- 24/7 managed SOC
- Crypto asset access inventory
- SaaS visibility / shadow IT audit
- ISMS or formal compliance documentation beyond basic written summary
- Ongoing support or monitoring

**Post-handoff operations:** The client's designated admin holds the SentinelOne console. Andy provides one month of email support post-delivery. After that, incident response goes to SentinelOne's included IR team directly — Andy is not in the chain. This must be stated clearly in the contract.

**Who this is for:** A fund that's ready to actually build something, not just check a box. Probably has one institutional investor asking questions or has recently become aware of the Lazarus Group threat profile. $22K is approvable by a COO without committee friction. Leaves room for an upsell conversation about Tier 3 if they want managed coverage.

**Andy's margin:** Estimated 50–60 hours delivery. At $22K, that's ~$370–440/hour effective rate. Lower than Tier 1 per hour but higher deal size.

---

### Tier 3 — The Cadillac
**"Security Program"**
**Price: $35,000 fixed**
**Timeline: 4 weeks (10–14 sessions)**
**Ideal client: $100M–$500M fund, institutional investors in the cap table or actively fundraising, aware of the specific threat landscape, wants a complete program not a checklist**

The full program. Every layer deployed, documented, and handed off with the client fully capable of operating it. Managed SOC included (Huntress, pending channel verification) or SentinelOne with explicit IR escalation path. This is the engagement Andy built for Hyla, productized and solo-deliverable.

**What's included:**

Everything in Tiers 1 and 2, plus:

*EDR upgrade to managed SOC (Huntress — pending verification):*
- 24/7 SOC monitoring; Andy not in post-handoff IR chain
- Plain-English alert delivery to client
- OR: SentinelOne with documented IR escalation path to S1 team if Huntress channel question unresolved

*Crypto asset access inventory:*
- Audit of who has access to what (exchange accounts, wallets, custodians, API keys)
- Access control recommendations
- Offboarding implications documented

*SaaS visibility audit:*
- Shadow IT discovery
- OAuth grant review (what apps have access to Google/M365)
- Recommendations for consolidation and revocation

*Full onboarding/offboarding playbook:*
- Covers all tools, all access points, crypto asset access
- Executable by a non-technical operator

*Compliance documentation package:*
- Written security program summary suitable for SEC examination
- Controls mapped to SEC cybersecurity rule requirements
- Investor DDQ answers pre-written for common questions

*Staff security training session:*
- 60–90 minute session covering threat landscape, Telegram/Zoom hygiene, phishing, social engineering specific to crypto
- Recorded for future onboarding use

**What's NOT included:**
- Formal ISMS (ISO 27001 / SOC 2) — separate engagement
- Penetration testing — separate engagement
- Ongoing retainer (offered separately at $2,500–$3,500/month)
- Email security (Sublime or equivalent) — offered as add-on

**Post-handoff operations:** Handled by the SOC (Huntress preferred) or SentinelOne IR team. Andy's role ends at handoff. One month of email support included. No on-call obligation.

**Who this is for:** The target client. A fund that has AUM, has institutional investors asking hard questions, knows the threat is real because they've heard the Stardust Chollima story or lived something adjacent to it, and wants the job done by someone referred by someone they trust. The warm Amphibian Unite referral from Andrew Hoppin lands here.

**Andy's margin:** Estimated 100–125 hours delivery. At $35K, that's $280–350/hour effective rate. Below Tiers 1 and 2 on an hourly basis but the right price for the market and the referral channel. Validate actual hours on first 2–3 engagements and adjust.

---

## Add-Ons (All Tiers)

These are offered post-delivery or alongside any tier, not bundled into the fixed price.

| Add-On | Price | Notes |
|---|---|---|
| Monthly retainer (fractional security advisor) | $2,500–$3,500/month | Quarterly check-ins, policy updates, incident escalation point. Positions Andy as ongoing advisor, not on-call IR. |
| Email security (Sublime Security) | $2,500 setup + licensing | Inbound threat filtering; separate deployment engagement |
| Penetration test referral | Pass-through | Andy refers to a vetted pen tester; does not deliver |
| Formal ISMS / compliance framework | Scope TBD | Separate engagement; SOC 2 or ISO 27001 readiness |
| Additional device / team expansion | $500–$1,000/device | For firms that grow after initial deployment |

---

## Pricing Rationale Summary

The $35K Cadillac is not arbitrary. It sits at the intersection of four constraints:

**Cost floor:** 125 hours × blended rate = ~$25K labor. $35K provides a 40% margin — adequate for a solo practice but not fat.

**Decision authority ceiling:** Above $50K typically requires investment committee approval at the target firm size. $35K is approvable by a COO or operating partner unilaterally, especially when framed as regulatory compliance spend.

**Market positioning:** Annual MSSP or vCISO coverage for a 10-person firm runs $72K–$120K/year. $35K one-time is the first year for less than half the cost of ongoing managed services — and the client owns the infrastructure afterward.

**Value anchoring:** Conservative expected breach cost for a $100M crypto fund (direct costs + investor redemptions) runs $22M–$36M. $35K is 0.1% of the conservative loss scenario. The ROI math is not the sales pitch, but it's the backstop when a client pushes back on price.

**The Hyundai and Jetta exist** because not every warm referral will be a Tier 3 client. Some are smaller, some are earlier, some just need to show something to an investor quickly. Having lower tiers prevents losing those conversations entirely and creates a natural upgrade path. A Tier 1 client who gets a real investor inquiry six months later is a Tier 3 renewal conversation.

---

## Open Questions Before Going to Market

1. **Huntress channel verification** — Tier 3 as written depends on Huntress as the managed SOC option. Until the partner call resolves the channel/handoff question, Tier 3 uses SentinelOne as the EDR with explicit IR escalation documentation as the fallback.
2. **Actual hour validation** — The 100–125 hour estimate for Tier 3 is based on the Hyla/Amphibian experience. Needs validation on first 2–3 solo deliveries before holding the price firm.
3. **Tier 2 EDR selection** — Tier 2 currently specifies SentinelOne. If Huntress channel question resolves favorably, consider offering Huntress as the Tier 2 EDR option at a slight premium (adds managed SOC value without the full Tier 3 scope).
4. **Pricing sensitivity** — No live market validation yet. The $12K/$22K/$35K structure is informed by research; it needs 5–10 warm conversations to test where friction actually appears.

---

*Sources: See PRICING_RESEARCH_CRYPTO_FUNDS.md for full citations on market data, regulatory deadlines, vCISO/MSSP pricing, and breach cost benchmarks.*
