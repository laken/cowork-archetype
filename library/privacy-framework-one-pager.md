# Security Tools: What They See and Who You're Trusting

*Delivered to all team members before any tool is deployed.*
*This document is yours to keep. Ask questions before we begin.*

---

When we implement your security program, we'll be deploying tools that have real visibility into activity on your devices. That's not incidental — it's how security works. A tool that can't see anything can't stop anything.

The more useful question isn't "what can these tools see?" It's "who are you trusting with that access, and why?" Every security tool on the market requires you to trust someone. The choice between tools is really a choice between trust relationships. This document lays out what each tool sees and who holds the keys.

---

## Identity Provider (Google Workspace / Microsoft 365)

**What it sees:** Who signs into what, when, and from where. Login history, device information, which apps are authorized. Admin-level access includes the ability to reset passwords and revoke sessions.

**Who you're trusting:** Google or Microsoft as the platform, plus your organization's designated admin and [Andy Laken, Archetype Consulting] during the engagement period.

**What it doesn't see:** Content of documents, emails, or messages — unless an admin actively opens them. The IDP is a key registry, not a content monitor.

**When it's used:** Routine access management, onboarding and offboarding, and security investigations if an account shows signs of compromise.

**Data retention:** Governed by your Google Workspace or M365 agreement. Audit logs retained for 6 months (Workspace) or up to 1 year (M365 E3+) by default.

---

## Endpoint Detection and Response (EDR)

This is where the trust question matters most, and where you need to understand what you're choosing between.

**What all EDR tools see:** Security-relevant activity on your device. At minimum: every process running on your machine (file path, parameters, hashes, start time, parent process, user account), system and network configuration, and persistence mechanisms. This telemetry is continuous, comprehensive, and uploaded to the vendor's cloud platform where detection logic is applied. It does not include keystroke logging, document contents, or browser history — but it is not minimal. Every process on your laptop is being monitored.

During an active incident investigation, the EDR vendor or admin can initiate expanded forensic collection — additional artifact retrieval from your device. The specific scope of what can be collected in this mode varies by tool and is not always explicitly bounded in documentation.

**The trust question — and it's a real one:** No enterprise EDR tool we evaluated is fully automated in a way that technically prevents human access. Incident response, by design, requires humans to take action on your device. The question is which humans, under what accountability structure.

**Self-managed EDR (SentinelOne is our current fallback option):**
The platform vendor (SentinelOne) provides the tool. Remote shell access — the ability to run arbitrary commands on your device — exists as a feature and is equivalent in capability to what CrowdStrike provides. The keys to that access are held by whoever you designate as your console admin. During the engagement, that's Andy Laken. After handoff, it's your designated admin. SentinelOne the company is not in the chain. You know exactly who can touch your endpoints because you control the admin accounts. All actions are audited.

**Managed EDR with 24/7 SOC (Huntress is our current preferred option, pending verification):**
The SOC vendor (Huntress) both provides the tool and operates it. Their analysts watch your endpoints continuously and can take action during incidents. You are trusting Huntress as a company — their hiring practices, internal access controls, and operational policies — not just a named individual. The telemetry they collect (every process on every machine, continuously) sits on their infrastructure. Their documentation describes a "wide range of surgical actions... along with other steps our SOC can take" — the full scope of what their analysts can do on your endpoints is not explicitly bounded in public documentation, and we have not yet obtained written confirmation of the specific limits.

The case for Huntress isn't that they have less access — it's that they are a specialized security company with reputational and contractual accountability for how they use it, and their SOC removes the operational burden from you entirely. The case against is that you are permanently delegating access to a third party whose individual employees you cannot vet.

**Neither option eliminates the need for trust. They route it differently.**

With self-managed EDR: you trust a named person (your admin) who you control.
With managed EDR: you trust a company and its policies.

---

## Network Protection (Cloudflare WARP / Zero Trust)

**What it sees:** DNS queries — the domain names your device requests when loading websites or apps. Used to block known malicious domains before your device connects to them. Does not decrypt connection content.

**Who you're trusting:** Cloudflare as a service provider. Their DNS privacy terms prohibit selling individual query data to advertisers or third parties, and their policy is publicly audited. For context: your ISP has legal authority in the US to sell aggregated DNS data to data brokers and has no accountability relationship with your firm. Cloudflare is a meaningfully better trust relationship than the default.

**Individual browsing history** is not surfaced to your organization's admins in standard configurations.

**Data retention:** DNS query logs not retained by default in WARP consumer configurations. Zero Trust enterprise configurations can log queries for security review, retained up to 6 months.

---

## Password Manager (1Password / Bitwarden)

**What it sees:** Vault structure — which credentials exist and which team members have access to which vaults. Vault contents are end-to-end encrypted; neither the vendor nor your admin can read stored passwords.

**Who you're trusting:** The vendor for vault security; your admin for access policy structure only. No one can read your credential values.

**Data retention:** Vaults persist as long as your account is active. Deletion is permanent and admin-controlled.

---

## A Note on This Engagement

During implementation, [Andy Laken / Archetype Consulting] will have elevated access to configure these tools. That access is scoped to what's needed for setup and will be reduced to standard admin levels at handoff. If you'd like to review or revoke any access at any point, ask.

After the engagement concludes, your organization owns the accounts and controls all admin access. There is no ongoing access by Archetype unless you initiate a separate engagement.

---

*Questions about any of this before we start? Good. Ask them now.*
