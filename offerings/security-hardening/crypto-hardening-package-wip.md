# Crypto Fund Security Hardening — Productized Package (WIP)

*Working document. Updated March 2026 from design session with Claude.*
*Do not publish. This is the internal design brief, not the client-facing offer.*

---

## Strategic Context

This package is designed as Archetype's fixed-scope, fixed-price entry point for crypto fund clients. It converts the Hyla/Amphibian security program (9 phases, ~$70K combined product + services, ~9 weeks, co-delivered with Austin Quam/Zero Sum Defense) into a solo-deliverable engagement that:

- Is concrete enough for warm inbound referrals to say yes to without a lengthy discovery process
- Is repeatable and efficient enough to achieve a high effective hourly rate
- Creates a natural conversion path into ongoing retainer work
- Can be delivered 4–5 times to build tooling, playbooks, and institutional knowledge

Andrew Hoppin is the primary referral channel — warm Telegram intros to peer fund managers in the Amphibian Unite community (~194 members, Tier 1 prospects identified in `outreach-resources/amphibian-unite-members.md`).

**Critical delivery constraint:** This is a get-in-and-get-out engagement. Andy is not an incident responder and does not want post-engagement operational obligations. Scope, contracts, and tool selection must all reflect this. Incident response is explicitly out of scope and stated clearly in contracts from day one.

---

## Target Buyer

**Archetype ICP:** Small-to-mid-size crypto fund or trading firm. Lean team (4–20 people). Real AUM ($50M–$500M range). Almost certainly BYOD. Security posture that hasn't kept pace with the threat environment. Leadership aware the threat is real but hasn't acted systematically.

**Not the target (for this package):** Large institutional market makers (Wintermute, GSR, Flow Traders) who likely have existing security infrastructure and would require a different sales motion entirely.

**Assumed starting state (based on Hyla/Amphibian experience):**
- Fully BYOD — no endpoint management or visibility
- No EDR (endpoint detection and response)
- No network protection layer (some individuals run consumer VPNs, which is not equivalent)
- Password manager partially adopted or not at all — inconsistent across team
- Google Workspace or M365 in use but not functioning as a real IDP; SaaS sprawl with rag-tag auth
- No SaaS visibility or shadow IT awareness
- Telegram and Zoom used constantly, naively — no hardening or SOPs
- No crypto asset access inventory
- No onboarding/offboarding playbook
- Ahead of ~90–95% of peers in the space even at this maturity level (per Hyla/Amphibian experience)

---

## What's Settled in the Core Scope

### 1. IDP Hardening — Foundation Layer
Make Google Workspace or M365 actually function as the identity provider. This is the structural prerequisite for everything else.

- Enforce SSO across all company-connected SaaS — eliminate standalone username/password for any system where SSO is available
- Tighten admin access and super-admin controls
- Enable and configure available security features (many clients are paying for these and not using them)
- 2-step verification enforced org-wide
- Audit and tighten sharing settings (Google Drive / Dropbox / equivalent) — permissions are almost always overbroad
- Mobile device management profiles where applicable

**Why it's foundational:** If the IDP isn't clean, EDR and network protection are patching over a leaky foundation. Every other layer depends on identity being trustworthy.

### 2. Endpoint Protection (EDR)
Deploy endpoint detection and response across all work devices.

**Current leading candidate: SentinelOne Singularity Control** (~$79.99/device/year)

- Marginally cheaper entry point than CrowdStrike Pro ($99.99/device/year)
- AI-driven autonomous response — designed to prevent and remediate threats without requiring admin intervention, which reduces (though does not eliminate) the frequency of remote shell use
- Important caveat: SentinelOne has the same remote access capabilities as CrowdStrike (RemoteOps, Full Remote Shell) — the privacy story isn't actually cleaner, just framed differently. Don't oversell this distinction.
- Strong BYOD and mobile support via Singularity Mobile module
- No separate MDR cost — unlimited IR hours included

**On CrowdStrike:** Remains viable. The RTR objection is manageable with the right framing (surveillance vs. security instrumentation). Many teams never touch RTR in normal operations.

**On Huntress:** Interesting because their SOC handles incident response, which solves Andy's post-engagement operational problem. However:
- The privacy story isn't cleaner for this audience. Trading "your consultant could access your machine" for "a company you've never heard of has 24/7 SOC access" undermines Andy's core credibility advantage (known, accountable, referred by Andrew Hoppin).
- Channel-first model — 50-endpoint minimum across partner accounts, and clean post-engagement client handoff is not a documented standard process. Requires direct conversation with Huntress partner team.
- **Open question:** Does Huntress's "Huntress Supported" tier allow clean handoff of the client relationship post-engagement? Research suggests it may, but it's not a designed pathway. Needs verification before relying on this model.

**Primary open question blocking EDR decision:** Who handles incident response after Andy exits? This needs to be answered first — tool selection follows from that answer.

### 3. Network Protection Layer
Route traffic through a managed DNS/network filter to block malicious domains before they load.

**Current recommendation: Cloudflare WARP + Zero Trust** (simplest unified option)

**Key architectural finding:** Tailscale is NOT a replacement for Cloudflare WARP. They solve different problems:
- **Tailscale** = mesh VPN (WireGuard-based, peer-to-peer). Solves internal network access — securely connecting team devices to each other and shared infrastructure. Does not filter internet-bound traffic or block malicious domains.
- **Cloudflare WARP** = DNS filtering + encrypted DNS + threat blocking for internet-bound traffic. Different architectural problem.

**Privacy-preserving alternative to Cloudflare:** Tailscale + NextDNS (~$12–13/user/month combined). NextDNS offers regional data storage, no upstream logging, ~$6.50/month flat. Viable swap if a client's objections specifically center on Cloudflare.

For most engagements, Cloudflare WARP remains the default. The privacy reframe handles most objections without needing to swap tools.

### 4. Password Manager — Standardization and Full Compliance
One tool, org-wide, with enforced MFA. Product is secondary to adoption.

- **Candidates:** 1Password (Teams/Business) or Bitwarden
- Single tool only — splitting 1Password (passwords) and Bitwarden (TOTP) is unnecessarily complex for small teams
- Hardware MFA (YubiKeys) for principals and high-risk roles
- Offline backup codes policy (stored physically, not in cloud)
- Full team adoption verified, not just deployed

### 5. Telegram and Comms Hardening
Every person on these teams uses Telegram daily and knows it's a war zone — account takeovers, impersonation, and scams are constant. High-anxiety area where peace of mind has real value even when the technical lift is low.

- Telegram account hardening: username privacy, active sessions audit, 2FA, linked device review, recovery email/phone secured
- Zoom hardening: waiting rooms, host verification, screen sharing restrictions
- Signal configuration where relevant
- SOPs for identity verification on communication platforms — out-of-band verification practices
- Written guide delivered as a team resource, plus verification that everyone has actually completed it

### 6. Crypto Asset Access Inventory
Document who has access to what, under what authentication mechanism, with what authorization level.

- Exchanges (Coinbase, Anchorage, Binance, etc.)
- Custodians
- Bank accounts
- Internal dashboards and trading tools
- Deliverable: auditable access registry, role-based, tied to the IDP and password manager
- Covers offboarding risk — departing staff or partners whose access persists

### 7. Onboarding/Offboarding Playbooks
Formal, documented process for provisioning and deprovisioning access.

- Tied directly to IDP and access inventory work above
- Ensures new staff/contractors get appropriate access from day one
- Ensures departing staff lose all access on exit, not weeks later
- Natural output of the IDP and access control work, documented as a reusable playbook

---

## Still Being Scoped / Open Questions

- **SaaS visibility (Nudge Security or equivalent):** Belongs in the full program; question is whether it's core to this package or an add-on.
- **Detection platform (RunReveal or equivalent):** Centralized log correlation. Important for mature programs; likely beyond scope for the fixed-fee entry package.
- **ISMS framework:** Lightweight policy documentation. Relevant for clients approaching RIA status. Candidate for add-on or tier-2.
- **Scope for clients with existing infrastructure:** This package assumes starting from near zero. Clients with some tools deployed need a variant.
- **EDR default and incident response ownership:** Primary open question. See EDR section above.

---

## The Privacy Problem

Predictable, structural objection at crypto-native firms. Must be addressed proactively, not reactively.

**The objection:** "I don't want CrowdStrike having access to my machine" / "I don't want Cloudflare seeing my DNS traffic."

**The reframe (correct and defensible):**

Privacy in security is never a choice between "someone knows" and "no one knows." It's always a choice between *who knows*, under what terms, with what incentives.

- **On DNS/WARP:** Every network resolves your DNS somewhere — your ISP, hotel Wi-Fi, coffee shop router. Those actors have no relationship with you, no accountability, and in the US, ISPs have legal authority to sell aggregated DNS data to data brokers. Turning off WARP doesn't mean no one sees your DNS — it means unknown actors with bad incentives see it instead of a known, accountable party with defined retention policies.

- **On EDR/CrowdStrike:** The alternative to CrowdStrike's audited, time-bounded RTR access in a confirmed incident is not "no one can access my machine." It's that attackers have unlimited, unaudited access with no constraints. You're choosing between a known accountable actor with narrow documented access, and an unknown attacker with total access.

- **The meta-argument:** The distinction is between *surveillance* (watching you to build a profile or sell data) and *security instrumentation* (watching for specific threat signals so a known party can respond). Same technical mechanisms, fundamentally different purpose, governance, and incentive.

**Delivery implication:** Every engagement should include a one-page Privacy and Data Governance document delivered on day one, before any tool is deployed. Names what each tool can see, who has admin access, under what conditions, and data retention. Converts the objection into a demonstration of competence and trust.

*[See: `library/privacy-framework-one-pager.md` — draft client-facing deliverable]*

---

## Pricing — Directional, Not Final

Sub-agent research (see `library/fsp-pricing-analysis.md`) recommended **$35,000 fixed fee**, 4–5 week timeline.

Rationale used by sub-agent:
- 125 hours estimated delivery at $200/hr effective rate = $25K labor + $10K margin
- Competitive benchmark: fractional CISO + implementation runs $60–120K first year; $35K is well-positioned relative to alternatives

**Andy has not validated this number.** Built bottom-up from hours; value-based methodology (Stark/Enns) would anchor it to the DFS conversation with the specific buyer. $35K may be right, may be conservative.

Working constraints:
- Original Hyla/Amphibian: Andy billed at $150/hr, ~$15,300 total — this is a floor, not an anchor
- Productized price should be anchored to value delivered, not hourly rate
- Tension: fixed price = some clients will be underpriced, acceptable for now given need for reps and revenue

---

## Conversion Path

Natural upgrades after the foundational package:
- Ongoing monitoring and program management (retainer — ~$2,500/month)
- ISMS framework and compliance readiness
- Detection platform implementation (RunReveal, etc.) — $8–12K estimated
- SaaS visibility (Nudge Security) — $3–5K estimated
- Annual security assessment / playbook updates — $5–10K estimated
- AI workflow implementation (separate Archetype pillar)
- Full fractional CTO retainer

---

## Related Files in Library

- `value-based-pricing-synthesis.md` — methodology reference (Stark, Enns, Silva, Baker/Weiss)
- `edr-evaluation-report.md` — full EDR comparison (CrowdStrike, SentinelOne, Huntress, others)
- `fsp-pricing-analysis.md` — sub-agent pricing research and $35K recommendation
- `fsp-sales-script.md` — draft 20-minute discovery call script
- `fsp-one-pager.md` — draft client-facing positioning
- `fsp-financial-model.md` — unit economics and revenue scenarios
- `privacy-framework-one-pager.md` — client-facing day-one privacy/data governance document

---

*Last updated: March 2026. Primary open question: incident response ownership and EDR default. Price not finalized.*
