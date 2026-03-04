# EDR Tool Evaluation: Crypto/Trading Firms
**Date:** March 2026
**Use Case:** Small crypto funds and trading firms (4–20 people, BYOD, high-threat environment)
**Threat Baseline:** Stardust Chollima / Lazarus Group (nation-state-grade; confirmed infection at Hyla via fake Zoom malware)

---

## Shortlist

Two tools remain in contention. All others are eliminated — reasons documented in the individual product sections below.

### Huntress Managed EDR — ✅ PREFERRED (pending channel verification)

**What it is:** A fully managed detection and response service. A 24/7 SOC watches all endpoints, pre-triages every alert, and delivers plain-English verdicts to the client. The client sees actionable findings, not raw telemetry.

**Why it's preferred:**
- The managed SOC model directly solves Andy's post-engagement operations problem. After handoff, the client has 24/7 eyes on their environment without Andy in the loop.
- Console experience is purpose-built for non-security operators — pre-triaged alerts, plain English, not raw detections.
- Threat intelligence covers Lazarus Group / Stardust Chollima / DPRK actors.
- Pricing includes the SOC — no add-on cost for managed response.

**The privacy question — open, not resolved:**
Earlier sessions noted that Huntress SOC doesn't use an interactive shell and is constrained to scoped agent actions. This needs qualification. Huntress's own documentation states their SOC can perform a "wide range of surgical actions... along with other steps our SOC can take" — that phrase explicitly leaves the action space open-ended. The listed actions (isolate host, kill process, delete file, block connection) are examples, not an exhaustive enumeration. Nothing in the documentation states that SOC analysts are technically incapable of broader access.

The privacy distinction from SentinelOne and CrowdStrike may be real — Huntress's product architecture and business model are built around pre-defined response actions rather than analyst-driven command execution, and the Manual Remediation model (SOC writes instructions, customer executes) implies a different access model than RTR. But this has not been verified as a technical constraint. **This must be resolved on the Huntress partner call before making the privacy claim to clients.** The specific question: can SOC analysts execute arbitrary commands on customer endpoints, and can Huntress put the actual access constraints in writing?

**Open blocking item:** Channel/handoff model. Huntress is channel-first with a 50-endpoint minimum across partner accounts. Clean post-engagement client handoff is not a documented standard process. Requires direct conversation with Huntress partner team.

**Pricing:** ~$8–15/device/month (quote required). For a 10-person team: ~$960–$1,800/year.

---

### SentinelOne Singularity — ✅ FALLBACK

**What it is:** A self-managed EDR with strong autonomous response. The AI agent handles most threats without human intervention. When incidents escalate, the client engages SentinelOne's included IR team directly — Andy is not in that chain.

**Why it's the fallback:**
- Cleaner procurement path for a non-MSSP consultant — can be sold directly to clients.
- Autonomous response reduces operational burden post-handoff.
- IR hours included in Singularity Complete — client has an escalation path without Andy.
- Confirmed detection against nation-state-grade threats.

**The privacy story (honest):**
SentinelOne has full remote shell capabilities — RemoteOps and Full Remote Shell. SentinelOne's own documentation states: *"Anything you can do with PowerShell and Bash, you can also do with SentinelOne Full Remote Shell."* This is architecturally equivalent to CrowdStrike RTR. The privacy framing is about how those capabilities are used (scheduled, automated, admin-controlled rather than SOC-initiated) — not about whether they exist. Don't oversell this as categorically different from CrowdStrike.

**Post-handoff gap:** Someone needs to be watching the console, or at minimum know to engage SentinelOne IR when something fires. Andy can contract this out of scope and refer clients to SentinelOne directly, but it needs to be addressed explicitly.

**Pricing:** $69.99–$179.99/device/year depending on tier. Singularity Control (~$80/device) is the likely entry point. For a 10-person team: ~$700–$1,440/year.

---

## Comparison Matrix

*Shortlist items at top. All others eliminated — reasons in individual sections below.*

| Tool | Status | Entry Price | 10-Person Cost | Human Shell Access | SOC/IR Model | Console for Non-Specialist | BYOD | Stardust Chollima | Post-Handoff IR |
|---|---|---|---|---|---|---|---|---|---|
| **Huntress** | ✅ PREFERRED | ~$8–15/device/mo | $960–$1,800/yr | Unverified — SOC claims scoped actions; "along with other steps" language leaves open. Needs written confirmation. | Fully managed 24/7 SOC; human-verified plain-English alerts | Excellent — pre-triaged, purpose-built for non-specialists | Good; some macOS BYOD friction documented | Yes — active DPRK/Lazarus intel | Handled by Huntress SOC; Andy not in chain |
| **SentinelOne** | ✅ FALLBACK | $69.99/yr | $700–$1,440/yr | Yes — RemoteOps + Full Remote Shell. Own docs: "Anything you can do with PowerShell and Bash." Equivalent to CrowdStrike RTR. | Self-managed; IR hours included in Complete tier | Good — autonomous response reduces noise; cleaner than Falcon | Excellent | Yes — confirmed detection | IR hours included; client engages S1 directly |
| **CrowdStrike Falcon** | ❌ OFF LIST — UI | $99.99/yr | $1,000/yr | Yes — RTR full interactive shell, browser-based terminal, arbitrary command execution | Self-managed; MDR is separate paid tier | Poor — built for security analysts | Good | Yes (market leader) | Requires separate Falcon Complete MDR |
| **Microsoft Defender** | ⚠️ CONDITIONAL — M365 only | $3/user/mo | $360/yr | Limited (Live Response, constrained vs. RTR) | Self-managed | Moderate | Good (M365 integrated) | Weaker than dedicated EDR | Self-managed |
| **Sophos Intercept X** | ❌ OFF LIST — threat profile | ~$28/yr | $280/yr | Limited | Self-managed or add-on MDR | Moderate | Fair | Insufficient for nation-state | Add-on cost |
| **Malwarebytes** | ❌ OFF LIST — threat profile + BYOD gap | ~$50/yr | $500/yr | Minimal | None | Simple | Poor (no bundled mobile) | Insufficient | None |
| **Bitdefender GravityZone** | ❌ OFF LIST — pricing opacity + threat profile | $200/yr base | $2,000+/yr | Unclear (Enterprise only) | Self-managed | Moderate | Fair | Insufficient | Self-managed |
| **Elastic Security** | ❌ OFF LIST — operational overhead | Free/self-hosted | $100–$300/yr | Yes (custom config) | Self-managed (requires security engineer) | Poor — requires expertise | Fair | Dependent on config | Self-managed |
| **Cybereason** | ❌ OFF LIST — enterprise minimum | ~$50/device | $500+/yr | Yes | MDR included | Moderate | Fair | Yes | MDR included |

---

## Why These Two and Not the Others

**CrowdStrike** is off the list not because of the privacy/RTR concern — that's manageable with the right framing, and many teams use CrowdStrike without ever touching RTR. It comes off because the console is genuinely impenetrable for a non-security operator. The most technical person at a 10-person crypto fund is a quant or developer, not a security analyst. Falcon is not built for them. This is a practical delivery problem, not a sales one.

**Sophos, Malwarebytes, Bitdefender** come off because of the threat profile. Stardust Chollima (Lazarus Group subcluster, responsible for the fake Zoom malware infection at Hyla) is nation-state-grade, actively maintained custom malware. These tools are adequate for commodity threats. They are not adequate for that actor.

**Elastic** requires a security engineer to operate. That is not Andy's client.

**Microsoft Defender** stays conditional. If a client is deeply M365-integrated, the economics ($3–5/user/month) are compelling and the integration is seamless. Threat intelligence depth is weaker, and it's not purpose-built for a crypto fund's threat profile. Include only when M365 is already the IDP and budget is a genuine constraint.

**Cybereason** is priced for enterprises with 300+ endpoints minimum. Not viable for 4–20 person teams.

---

## Individual Product Sections

### CrowdStrike Falcon (Baseline — Off List)

**Pricing**
- Falcon Go: $59.99/device/year
- Falcon Pro: $99.99/device/year
- Falcon Enterprise: $184.99/device/year
- Falcon Complete MDR: Custom

**Strengths**
- Market leader; deepest threat intelligence
- Cloud-native architecture; excellent detection
- Strong iOS/Android BYOD support
- Comprehensive XDR platform

**Weaknesses**
- RTR provides full interactive shell access to managed endpoints — browser-based command terminal with arbitrary command execution. This is the capability that caused friction with Hyla staff. The mere existence of it is the concern, not how often it's used.
- Console built for security analysts, not fund operators. This is the actual disqualifier.
- Highest-tier pricing for enterprise features

**Sources:** [CrowdStrike Pricing](https://underdefense.com/blog/crowdstrike-pricing/) · [Falcon Product Page](https://www.crowdstrike.com/en-us/pricing/)

---

### SentinelOne (Shortlist — Fallback)

**Pricing**
- Singularity Core: $69.99/device/year
- Singularity Control: $79.99/device/year
- Singularity Complete: $179.99/device/year (~$135–153 with 15–25% discount)

**Remote Access Capabilities**
- RemoteOps: Execute custom PowerShell/bash scripts across endpoints
- Full Remote Shell: Direct shell access — equivalent to CrowdStrike RTR
- All actions role-based and audited
- SentinelOne frames this as "forensics orchestration" and "automated remediation" — the framing differs, the capability does not

**Strengths**
- Lower entry pricing than CrowdStrike
- AI-driven local agent; less cloud-dependent
- IR hours included in Complete tier
- Excellent ransomware prevention
- Strong BYOD/mobile support

**Weaknesses**
- Full remote shell exists; privacy story is framing, not architecture
- Less threat intelligence depth than CrowdStrike (improving)
- Post-handoff gap: someone needs to be watching or know how to engage S1 IR

**Sources:** [SentinelOne Pricing](https://underdefense.com/blog/sentinelone-pricing-2026-packages-comparison/) · [RemoteOps](https://www.sentinelone.com/blog/feature-spotlight-introducing-remoteops-custom-script-actions/) · [Full Remote Shell](https://www.sentinelone.com/blog/full-remote-shell/)

---

### Huntress Managed EDR (Shortlist — Preferred)

**Pricing**
- Channel-first; no public pricing
- Estimated $8–15/device/month based on industry comparables
- 10-person team: ~$960–$1,800/year

**Strengths**
- 24/7 managed SOC included — not an add-on
- Pre-triaged alerts in plain English; purpose-built for non-security operators
- Lightweight cloud-native agent
- Ransomware and supply-chain threat focus
- DPRK/Lazarus Group threat intelligence

**Open Questions**
- SOC access boundaries: see privacy note in shortlist section above. Must be resolved on partner call before making privacy claims to clients.
- Channel/handoff model: 50-endpoint minimum across partner accounts; clean client exit not a documented standard process.
- macOS BYOD: some deployment friction noted in practitioner reviews; needs investigation for Mac-primary environments.

**Sources:** [Huntress Pricing](https://www.huntress.com/pricing) · [Managed EDR](https://www.huntress.com/small-business-cybersecurity-guide/why-small-businesses-need-edr) · [Automated Remediation Docs](https://support.huntress.io/hc/en-us/articles/21245857024275-Huntress-Managed-Response-Automated-Remediation-of-Incident-Reports)

---

### Microsoft Defender for Endpoint (Conditional)

**Pricing**
- Plan 1: $3.00/user/month
- Plan 2: $5.20/user/month
- Defender for Business (SMB): bundled in M365 security plans

**Strengths**
- Lowest TCO for M365-native environments
- Per-user license covers up to 5 devices (BYOD-friendly)
- Automated investigation and remediation included
- Live Response is constrained compared to RTR — a genuine privacy advantage

**Weaknesses**
- Weaker threat intelligence for crypto-specific threats (SIM swap, nation-state APT)
- Not suitable for non-M365 environments
- macOS and Linux coverage weaker than dedicated EDR

**Use when:** Client is already on M365 as IDP and budget is a binding constraint. Pair with explicit disclosure that threat intelligence depth is lower than Huntress or SentinelOne.

**Sources:** [Defender Pricing](https://www.trustradius.com/products/microsoft-defender-for-endpoint/pricing) · [Defender for Business FAQ](https://learn.microsoft.com/en-us/defender-business/mdb-faq)

---

### Sophos Intercept X (Off List — Threat Profile)

Eliminated because the Stardust Chollima / Lazarus Group threat profile requires nation-state-grade detection capability. Sophos is adequate for commodity threats; it is not adequate for that actor. Cost-effective for lower-risk environments but wrong for this client base.

**Pricing:** ~$28–30/device/year; with MTR ~$70–80+/year.

**Sources:** [Sophos Pricing](https://underdefense.com/blog/sophos-pricing-intercept-x-endpoint-protection-cost/)

---

### Malwarebytes EDR (Off List — Threat Profile + BYOD Gap)

Eliminated on two grounds: insufficient detection depth for nation-state-grade threats, and no bundled mobile protection (BYOD mobile requires a separate product). Not suitable for crypto firms with staff on personal iPhones.

**Pricing:** ~$50–72/device/year; $1,500 annual minimum.

**Sources:** [Malwarebytes Pricing](https://www.trustradius.com/products/malwarebytes/pricing)

---

### Bitdefender GravityZone (Off List — Pricing Opacity + Threat Profile)

EDR capabilities gated behind Enterprise tier with opaque custom pricing. Threat intelligence insufficient for nation-state-grade threats. Geared toward traditional IT environments, not crypto-forward firms.

**Pricing:** $200+/year base; EDR requires Enterprise quote.

**Sources:** [Bitdefender Pricing](https://www.trustradius.com/products/bitdefender-gravityzone/pricing)

---

### Elastic Security (Off List — Operational Overhead)

The maximum-privacy option: open-source core, self-hostable, no proprietary telemetry. Eliminated because it requires a security engineer to configure, tune, and maintain. Andy's clients do not have that person. Revisit only if a client has an in-house technical co-founder willing to own it.

**Pricing:** Free self-hosted; Elastic Cloud ~$100–300/year for small deployments.

**Sources:** [Elastic Pricing](https://www.elastic.co/pricing)

---

### Cybereason (Off List — Enterprise Minimum)

Priced and designed for 300+ endpoint enterprises. Not viable for 4–20 person teams.

**Pricing:** ~$50/device; minimum effective purchase 50–100 devices.

**Sources:** [Cybereason Pricing](https://www.trustradius.com/products/cybereason-defense-platform/pricing)

---

## Open Items

1. **Huntress partner call** — resolve channel/handoff model and get written confirmation of SOC access boundaries before committing as default and before making privacy claims to clients.
2. **Huntress macOS BYOD** — investigate deployment friction for Mac-primary environments.
3. **Price validation** — $35K package price not yet validated by Andy.
4. **SentinelOne fallback procurement** — if Huntress channel model doesn't work, confirm direct-to-client procurement path.
