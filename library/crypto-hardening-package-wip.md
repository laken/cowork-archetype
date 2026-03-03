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

---

## Target Buyer

**Archetype:** Small-to-mid-size crypto fund or trading firm. Lean team (4–20 people). Real AUM ($50M–$500M range). Almost certainly BYOD. Security posture that hasn't kept pace with the threat environment. Leadership aware the threat is real but hasn't acted systematically.

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

- **Primary candidate:** CrowdStrike Falcon
- **Alternative to evaluate:** SentinelOne (need product research)
- Covers: malware detection, behavioral monitoring, physical access attacks (USB, Bluetooth), device isolation in incident response
- Privacy framing required — see section below

### 3. Network Protection Layer
Route traffic through a managed DNS/network filter to block malicious domains before they load.

- **Primary candidate:** Cloudflare WARP + Zero Trust
- **Alternative to evaluate:** Tailscale (need product research — different architecture, may be better fit for some clients)
- Covers: DNS-based threat blocking, protection on home/hotel/public WiFi, protection against phishing links regardless of source (email, Telegram, web)
- Privacy framing required — see section below

### 4. Password Manager — Standardization and Full Compliance
One tool, org-wide, with enforced MFA. Product is secondary to adoption.

- **Candidates:** 1Password (Teams/Business) or Bitwarden
- Note: Austin Quam recommended separating 1Password and Bitwarden (passwords vs. TOTP) — Andy's view is this is unnecessarily complex for small teams. Single tool is the right call.
- Hardware MFA (YubiKeys) for principals and high-risk roles
- Offline backup codes policy (stored physically, not in cloud)
- Full team adoption verified, not just deployed

### 5. Telegram and Comms Hardening
Every person on these teams uses Telegram daily and knows it's a war zone — account takeovers, impersonation, and scams are constant. This is a high-anxiety area where peace of mind has real value even when the technical lift is low.

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
- This is a natural output of the IDP and access control work, documented as a reusable playbook

---

## Still Being Scoped / Open Questions

- **SaaS visibility (Nudge Security or equivalent):** Belongs in the full program; question is whether it's core to this package or an add-on. Nudge discovers shadow IT and unsanctioned SaaS — highly relevant but adds complexity and cost.
- **Detection platform (RunReveal or equivalent):** Centralized log correlation across tools. Important for mature programs; may be beyond scope for a fixed-fee entry package.
- **ISMS framework:** Lightweight policy documentation (Information Security Policy, risk register, RACI). Relevant for clients approaching RIA status or facing investor scrutiny. May be a natural add-on or tier-2 offering.
- **Scope for clients with existing infrastructure:** This package assumes starting from near zero. Clients with some tools already deployed need a variant — assessment first, then targeted gap closure.

---

## The Privacy Problem

This is a predictable, structural objection at crypto-native firms and must be addressed proactively, not reactively.

**The objection:** "I don't want CrowdStrike having access to my machine" / "I don't want Cloudflare seeing my DNS traffic."

**The reframe (correct and defensible):**

Privacy in security is never a choice between "someone knows" and "no one knows." It's always a choice between *who knows*, under what terms, with what incentives. The crypto privacy mindset often imagines a third option — total opacity — that doesn't exist at the infrastructure layer.

- **On DNS/WARP:** Every network resolves your DNS somewhere — your ISP, hotel Wi-Fi, coffee shop router. Those actors have no relationship with you, no accountability, and in the US, ISPs have legal authority to sell aggregated DNS data to data brokers. Turning off WARP doesn't mean no one sees your DNS. It means unknown actors with bad incentives see it instead of a known, accountable party with defined retention policies.

- **On EDR/CrowdStrike:** The alternative to CrowdStrike's audited, time-bounded RTR access in a confirmed incident is not "no one can access my machine." It's that attackers who deliver malware have unlimited, unaudited access with no constraints whatsoever. You're choosing between a known accountable actor with narrow documented access, and an unknown attacker with total access.

- **The meta-argument:** The distinction is between *surveillance* (watching you to build a profile or sell data) and *security instrumentation* (watching for specific threat signals so a known party can respond). These use similar technical mechanisms but are fundamentally different in purpose, governance, and incentive.

**Delivery implication:** Every engagement should include a one-page Privacy and Data Governance document delivered on day one, before any tool is deployed. It names what each tool can see, who has administrative access, under what conditions access is used, and what the data retention is. This converts the objection into a demonstration of competence and trust.

*[Draft privacy framework document: pending — to be created as a separate deliverable template]*

---

## Pricing — Not Yet Decided

Working constraints:
- Original Hyla/Amphibian: Andy billed at $150/hr, ~$15,300 total across both orgs over ~9 weeks
- That rate reflected an embedded fractional CTO relationship, not an arm's-length new client engagement
- Productized price should not be anchored to hourly rate — it should be anchored to value delivered
- $150/hr was a floor in that context; the right price for a new client engagement is higher
- $2,500–$4,500 (previously discussed) is almost certainly too low given scope and value
- Pia Silva / Stark methodology: price at ~10% of value delivered; value conversation surfaces the number
- Tension: productized = fixed price = some clients will be underpriced, but that's acceptable for now given the need for reps and revenue

*[Price to be determined after scope is finalized]*

---

## Product Alternatives to Research

Before finalizing scope, need a comparison pass on:

- **SentinelOne vs. CrowdStrike Falcon** — privacy footprint, SMB pricing, ease of deployment for small teams
- **Tailscale vs. Cloudflare WARP/Zero Trust** — architecture differences, privacy model, suitability for BYOD crypto teams

*[Research pending — do before locking in vendor recommendations]*

---

## Conversion Path

The productized package is explicitly designed as an entry point, not a terminal engagement.

Natural upgrades:
- Ongoing monitoring and program management (retainer)
- ISMS framework and compliance readiness (for firms approaching RIA or investor scrutiny)
- AI workflow implementation (separate pillar)
- Full fractional CTO retainer

Andrew Hoppin's intro in Telegram positions this well: "fixed-fee security hardening for crypto funds" is a concrete, low-friction offer that leads naturally into "and then he can stay on to manage it."

---

*Last updated: March 2026. Continue design session before finalizing.*
