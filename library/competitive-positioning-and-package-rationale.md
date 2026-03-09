# Competitive Positioning & Package Design Rationale

*Internal working document. March 2026.*
*Covers two questions: (1) where anti-phishing belongs in the tier structure, and (2) how to make the value argument against boutique/dedicated security firms.*

---

## Part 1: Anti-Phishing — Core or Add-On?

### The Current State

Anti-phishing (Sublime Security) is currently positioned as an add-on at $2,500 setup + licensing, available across all tiers. The question is whether this is the right call given what Cloudflare Zero Trust (CFZT) already does on the network side.

### What CFZT Actually Covers

Cloudflare WARP + Gateway provides phishing protection in two meaningful ways:

**DNS-layer blocking.** Every connection starts with a DNS lookup. Gateway blocks malicious domains — including phishing sites — before the device ever loads the page. Cloudflare's ML models detect phishing domains, command-and-control infrastructure, and DGA (domain generation algorithm) patterns in real time. For a crypto fund where someone clicks a fake Telegram link or a spoofed exchange URL, this stops it cold at the DNS level — before the page loads, before credentials are entered.

**Remote Browser Isolation (RBI) for email links.** This is where it gets interesting for the anti-phishing question. Cloudflare's Gateway + RBI integration automatically routes suspicious email links through an isolated browser session running at Cloudflare's edge. The user sees a rendered page, but no code executes on their device. If it's a credential-harvesting page, there's nothing to harvest — the keyboard input can be disabled entirely for high-risk browsing categories.

Cloudflare received 5.0/5.0 in malicious URL detection in the Forrester Wave for Email, Messaging, and Collaboration Security, Q2 2025. Their email link isolation product is native to the Zero Trust platform and doesn't require a separate tool.

### What Sublime Does Differently

Sublime is an email-first, programmable security platform — it sits in the email pipeline (M365 or Google Workspace) and filters at the inbox level before messages are delivered. Key distinctions:

- **Pre-delivery filtering.** Sublime catches phishing emails before they arrive. Gateway/RBI catches them when someone clicks. These are different points in the attack chain.
- **BEC and impersonation detection.** Business email compromise — fake CFO emails, supplier fraud, internal impersonation — isn't a link-click problem; it's a social engineering problem. RBI doesn't help here. Sublime's ML models specifically target BEC patterns that don't rely on malicious links at all.
- **Customizable rule engine.** Sublime lets you write detection rules tuned to your threat model. For crypto firms, that means rules targeting exchange impersonation, wire transfer requests, and fake KYC flows. Cloudflare's email product doesn't offer this level of customization.
- **Google Workspace compatibility.** Sublime integrates cleanly with Google Workspace, which is the IDP of choice for most small crypto funds. Cloudflare Email Security's deepest integrations are M365-native.

### The Architecture Question

The honest framing is that CFZT and Sublime protect against overlapping but non-identical threat vectors:

| Attack Type | CFZT (DNS + RBI) | Sublime |
|---|---|---|
| Phishing link in email → credential theft | ✅ RBI blocks execution | ✅ Pre-delivery filter |
| Malicious domain visited directly (Telegram link, etc.) | ✅ DNS blocking | ❌ Not in email path |
| BEC / impersonation (no malicious link) | ❌ Nothing to block | ✅ Pattern detection |
| Malware download via email | ⚠️ RBI partial | ✅ Pre-delivery filter |
| Fake exchange/wallet site | ✅ DNS + RBI | ⚠️ Only if via email |

### Recommendation: Keep as Add-On, but Tighten the Rationale

**The case for keeping Sublime as add-on rather than core is solid, with one important nuance:**

CFZT (with RBI enabled) covers the most common crypto-specific attack vector — malicious links delivered via Telegram, Discord, or any channel outside email. For a fund where most threat-surface communication happens on Telegram rather than email, the marginal protection from Sublime is lower than for a traditional enterprise.

However, BEC is a real and growing threat specifically for funds, and it doesn't go through Telegram — it goes through email. Fake wire instructions, impersonation of counterparties, fake KYC requests from exchanges. CFZT provides zero protection against these. Sublime does.

**Revised positioning:**

- **Core package:** CFZT covers the Telegram/link-click attack vector, which is the most acute crypto-specific threat. This is sufficient for most Tier 1 and Tier 2 clients.
- **Add-on (Sublime):** Specifically for clients who process significant wire transfers, communicate with counterparties via email for transaction approvals, or have had BEC attempts. This is a narrower argument than "phishing protection" generally — and it's a stronger one.
- **Tier 3 consideration:** For the full Cadillac program serving a $250M+ fund with institutional relationships, Sublime probably belongs in the base scope rather than as an add-on. At that AUM, a single successful BEC attempt could represent millions in misdirected wires. The $2,500 setup cost is noise relative to the risk. Consider including it in Tier 3 by default and calling it out explicitly in the value framing.

**What to change in pricing-and-tiers.md:** Add a note in the Tier 3 description that Sublime is included (or "included for clients with email-based transaction approvals"), and update the add-on description to be more specific: "Email BEC protection (Sublime Security) — for funds handling wire transfers or counterparty approvals via email."

---

## Part 2: The Value Argument Against Boutique/Dedicated Security Firms

### The Real Problem

Andy will encounter prospects who have already spoken with — or are currently considering — a dedicated cybersecurity firm. These could be:

- A boutique MSSP that offers "crypto-aware" security services
- A fractional CISO firm (Fortium Partners, FractionalCISO.com, Netrix, etc.)
- A regional managed security provider who claims to serve financial services

The firms Andy has met carry real advantages: brand recognition, team depth (bench coverage during incidents), CISO-level credentials, possibly CISSP/CISM certifications, vendor relationships, and the implied institutional longevity that comes from running a real firm rather than a solo practice.

This is not a problem to dismiss or paper over. It's real. The value argument needs to be unbeatable, not clever.

### Their Actual Advantages (Honest Assessment)

**Bench depth and coverage.** A team-based MSSP or CaaS provider can guarantee incident response coverage 24/7 without depending on one person's availability. Andy cannot. He is explicitly not doing post-engagement IR. This is a real limitation.

**Credentialing.** CISSP, CISM, CISA certifications signal a body of knowledge that some buyers will weight heavily, especially if they're ex-TradFi with compliance-driven instincts. Andy's credentials are practical and demonstrated, but he doesn't carry alphabet soup.

**Vendor relationships.** Large MSSPs have direct relationships with CrowdStrike, SentinelOne, etc. — preferred pricing, faster escalation paths, dedicated technical account managers. Andy is buying through partner tiers.

**Longevity optics.** "What happens if your consultant is unavailable?" is a real question for a solo practitioner. A firm with 15 people has an answer. Andy doesn't — except that his engagement is designed to end cleanly and the client isn't dependent on him afterward.

### Where Andy Wins — and Why It's Decisive for This Market

**1. Skin in the game, not a service contract.**

The fundamental difference between Andy and any external firm is that Andy built and ran this program at Hyla and Amphibian as an embedded operator — not as a vendor. When an infection hit Hyla, Andy was in the room (or on the Zoom). He was in the Slack. He knew the people. His reputation was directly tied to the outcome.

A boutique MSSP delivers a service. Andy delivers accountability. For a 10-person fund where the founder knows everyone on the team personally, "the guy who built this program knows us, has done this in our specific environment, and was referred by Andrew Hoppin" is worth far more than a credentialed stranger with a firm behind them.

This isn't a positioning argument. It's structurally true. The referral from Andrew Hoppin — a known, trusted peer in a tight community — is a credibility transfer that no external firm can purchase.

**2. Crypto-native threat model, not generic financial services.**

Most security firms that claim to serve financial services are thinking about SOC 2, PCI-DSS, and ransomware. Andy is thinking about Stardust Chollima, fake Zoom malware, Telegram impersonation, BYOD exchange API key exposure, and seed phrase operational security. These are not adjacent — they are a different threat landscape entirely.

A boutique MSSP will deploy their standard financial services playbook. Andy's playbook was built in response to actual active threat actors targeting this specific community. That's not something that can be assembled from generic frameworks.

**3. Fixed scope, fixed price, clean exit.**

Every fractional CISO and MSSP has a structural incentive to extend the engagement. Monthly retainers, quarterly reviews, annual renewals — the business model requires ongoing dependency. Andy's model explicitly does the opposite: define the scope, deliver it, hand off cleanly, and leave the client fully operational without Andy in the loop.

For a fund manager who is justifiably skeptical of ongoing vendor relationships — especially one that involves access to their endpoints — a fixed-price, fixed-scope engagement with a clean handoff is qualitatively different from a retainer. It aligns incentives: Andy gets paid when the work is done well, not when the client stays dependent.

**4. No false bench.**

The critique of boutique firms — that they often have solo practitioners with inflated titles, no real executive experience, and no backup coverage — applies to the lowest tier of security consulting. But the critique also reveals something true about team-based firms: the "team" is often a thin veneer of junior analysts behind a credentialed figurehead.

Andy is not pretending to be a team. He's a practitioner who built a real program, delivered it, and is doing it again. The engagement is scoped specifically to what one experienced person can deliver to a high standard in four weeks. There's no junior analyst touching the client's infrastructure.

**5. The Hyla program got tested.**

This is the argument that ends the credibility comparison. Andy built a security program at Hyla. The program was tested against actual Stardust Chollima / Lazarus Group malware. The fund was not compromised. The infection that did occur was detected and contained. The program held.

Most security firms are selling a theoretical framework. Andy is selling a proven program. Andrew Hoppin's testimonial says this explicitly: "When sophisticated impersonation attacks started targeting our industry, Andy had a hardening program in place before it became our problem."

No boutique MSSP has a quote like that. It's the proof of concept that no credential can replicate.

### The Unbeatable Value Argument — Summary Form

When a prospect is comparing Andy to a dedicated security firm, the argument is:

*"You can hire a security firm that will deploy a standard financial services playbook, charge you $6–12K a month for ongoing coverage, and assign you a team you've never met. Or you can work with someone who built and ran this program at a crypto fund you know and trust, was referred by someone in your community, and will deliver it for a fixed price with a clean handoff. The question isn't credentials — it's who you trust and what you need."*

The strongest version of this argument doesn't position Andy against security firms. It positions the decision as: do you want a vendor relationship or an accountable operator? For a crypto fund with assets on the line and a privacy-conscious culture, those are genuinely different things.

### When Andy Loses This Comparison

Be honest about the cases where a dedicated firm wins:

- The client has already had a significant incident and needs active IR capability, not a hardening program. Andy is not the right call.
- The client's compliance requirements (SOC 2, FCA, etc.) require ongoing documentation and attestation that a one-time engagement doesn't produce. A fractional CISO retainer is the right answer there.
- The client has 50+ people and multiple office locations. The FSP scope doesn't fit; a larger engagement model is needed.
- The decision-maker has a compliance background and needs CISO-level credentials to justify the selection internally. Andy should be honest rather than try to win this one.

Knowing when not to compete is part of the value argument. Saying "that's not actually what I do, and here's what I do do" signals confidence and integrity — the opposite of the generalist MSSP who will promise anything to close the deal.

---

*Last updated: March 4, 2026.*
*Related files: pricing-and-tiers.md, crypto-hardening-package-wip.md, fsp-one-pager.md*
