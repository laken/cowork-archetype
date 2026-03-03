# SOURCE: CONDENSED Joint Security Executive Summary (Hyla + Amphibian)
# Fetched from Google Drive (laken@hylafunds.com)

# CONDENSED Joint Security Executive Overview: Hyla \+ Amphibian

## Andy Laken | July 7, 2025

### Want more detail? [*Full version available here*](https://docs.google.com/document/d/1Qvy58a7lqnJ9BSFbLT8yAFJpu_g2uU96StwWN_QyD5c/edit?tab=t.0#heading=h.d95mxoo4jtov)

# 

# 

# 

# 

# 

# 

# 

# 

# 

# **Why This Matters**

Hyla and Amphibian are closely linked with shared staff, operational interdependence, and elevated cyber risk. **Recent attacks against affiliated funds prompted a rapid review of our security posture.** This joint proposal outlines a streamlined path to modernizing security—reducing risk and aligning controls across both orgs while respecting lean operations.

**The goal:** practical, overlapping defenses that are implementable by small teams, cost-effective, and suited to the evolving compliance landscape (especially as Amphibian approaches RIA status in 2026).

# **Core Security Layers & Targets**

Each layer below includes a **"Current"** state and a **"Target"** future state, along with context and rationale for joint implementation.

---

## 💻 Devices & Connections

*Why it matters:* Devices are common entry points for attackers; unmanaged systems present significant exposure.

* *Current:* Fully unmanaged personal devices.  
* *Target:* Secure mobile profiles (via Google Workspace); endpoint protection via **Cloudflare** \+ **CrowdStrike**.

## 📡 Resilient Connectivity & Secure Wireless

*Why it matters:* SIM-swapping increasing, can be disastrous. Communications needs to be continuous even in outage or travel scenarios.

* *Current:* No backup connectivity or secure wireless.  
* *Target:* **Starlink** at key sites; **Efani** secure SIMs for principals and high-risk users.

## 

## 

## 

## 

## 

## 

## 

## 

## 

## **📥** Email & Message Security

*Why it matters:* Phishing remains the top threat vector; malware risk.

* *Current:* SPF/DKIM/DMARC; Google filtering.  
* *Target:* **Sublime Security** for email threat inspection and custom detection rules. (*nearly completed for Hyla*)

## 

## 

## 

## 

## 

## 

## 

## 

## 

## **🔐** Passwords, MFA, and Recovery

*Why it matters:* Stolen or reused credentials and poor recovery practices can result in lockouts or compromise.

* *Current:* **1Password** in use at Hyla but not universal; inconsistent MFA and backup key handling.  
* *Target:* Org-wide password manager usage with enforced MFA and team vaults; increased use of Yubikeys; **Bitwarden** for MFA codes; offline backup codes stored securely.

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 👩‍💻 App Access & Segmentation

*Why it matters:* Not every user or device should have access to every app. Custom apps like Cyclical and Amphibian Dashboard increase the urgency. 

* *Current:* Basic Google login; weak Dropbox role boundaries.  
* *Target:* **Cloudflare Access** to enforce app access by role, device, and geography. Tighter document sharing policies.

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 🧠 SaaS Account Awareness

*Why it matters:* Staff regularly sign up for unapproved SaaS and AI tools, creating risk and visibility gaps.

* *Current:* No visibility into tool usage or access.  
* *Target:* **Nudge Security** to discover, audit, and manage shadow IT and app sprawl.

## 

## 

## 

## 

## 

## 

## 

## 

## 🧬 Endpoint Detection & Response (EDR)

**EDR** is modern security software for computers and laptops. It goes far beyond traditional antivirus — it watches for suspicious behavior in real time, such as unusual logins, unauthorized software activity, or attempts to send sensitive data out of the network. It also **controls physical access attacks** like malicious use of USB ports or other vectors that are possible with physical access to a machine. 

*Why it matters:* Helps detect and contain attacks and penetration.

* *Current:* No monitoring.  
* *Target:* **CrowdStrike Falcon** (or similar) deployed across laptops and desktops.

## 

## 

## 

## 

## 

## 

## 

## 

## 

## 🔍 Crypto Asset Security

Critical systems like exchanges, custodians, and banks each have different authentication setups. We need a clear policy and inventory of who has access, how it’s granted, and how it’s protected.

*Why It Matters:* Prevents unauthorized transfers, helps with onboarding/offboarding, and ensures continuity in an emergency. Standardized access patterns and protocols make it easier to detect bad actors. 

*Joint Context:* **Hyla** and **Amphibian** both use **Anchorage** and **Coinbase** platforms — sharing a common access framework ensures continuity and mitigates transaction risk.

* *Current:* Undocumented access inventory and enforcement.  
* *Target:* Role-based access records for exchanges, custodians, and banks using tools like 1Password and Yubikey.

## 

## 

## 

## 

## 

## 

## **🛡 Secure Communications**

Set up clear security settings and simple how-to guides for tools like **Zoom**, **Signal**, and **Telegram** to help the team use them safely and effectively. Define best practices for avoiding scams, verifying identities, and protecting sensitive conversations. Some of the breaches seen among underlying funds Hyla were initiated via fake Zoom scams.

**Current:** Standard **Zoom** configuration; no consistent hardening policies applied. Naive Telegram usage.  
**Target:** Cloud configuration of communication platforms and detection of unauthorized or risky usage

## **Why It Matters:** Messaging platforms are frequent targets for social engineering and impersonation. Clear protocols and basic OPSEC practices reduce risk, improve team awareness, and help demonstrate proactive controls to regulators and partners.

## 

## 

## 

## 

## 

## 

## 

## **🌐** DNS Filtering & Threat Blocking

Both **Hyla** and **Amphibian** rely heavily on internet-based tools and communications. Attackers frequently use malicious links or domains to deliver malware, steal credentials, or impersonate trusted services like **Zoom**, **Google Docs**, or fund admins.

*Why it matters:* Proactively blocks access to malicious domains

* *Current:* No domain-based threat protection  
* *Target:* **Cloudflare Gateway** to block phishing/malware links **proactively**

## 

## 

## 

## 

## 

## 

## 

## ISMS Program

Information Security Management System: structured framework of policies, procedures, and controls used to systematically manage and protect an organization’s sensitive information.

*Why it matters:* Helps Amphibian meet SEC expectations for cybersecurity risk management as it transitions to RIA status—demonstrating governance, internal controls, and preparedness in areas like access, vendors, and incident response without overbuilding.

## Detection platform

Set up a single, centralized system that watches for security issues across all key tools—like Cloudflare, CrowdStrike, Google Workspace, and 1Password. This system pulls in and connects activity from different sources, so you can spot real problems faster without jumping between dashboards. It becomes your main view into what’s happening across the firm’s security environment.

***Why it matters:*** With no full-time security staff, a centralized detection platform ensures visibility and timely alerting across all systems—allowing lean teams to triage incidents efficiently and meet SEC expectations for oversight and response.

# **Key Risks We’re Addressing**

Examples drawn from real-world fund breaches:

* **BEC (Business Email Compromise):** Impersonation leading to fraudulent transfers.  
* **Zoom Malware:** Fake invites delivering remote access trojans.  
* **Telegram Social Engineering:** Clone pages and impersonation leading to compromise.  
* **SaaS Sprawl:** Sensitive data in untracked apps; unmanaged release of data to AI tools.  
* **Lost Devices / MFA Lockout:** No fallback, resulting in urgent bypasses.  
* **Device compromise:** Malware, data exfiltration, keylogging  
* **Insider Risk:** Inadequate access offboarding.

# **Vendor recommendation**

## Austin Quam – Zero Sum Defense

* Solid industry credentials and recommendations (ex Vercel, AWS)  
* 1 Month of collaboration passes legitimacy test

Cost-effective effort split Austin / Andy

# **Phased Implementation Plan**

* Each phase delivers immediate security value  
* Minimizing vendor lock-in \- tools and vendors can be changed between phases  
* Subscription costs scale with actual rollout timeline  
* Amphibian can opt out of future phases without penalty  
* Stand up a security program that can operate mostly “headless” – a bit heavier upfront to reduce operational lift going forward

---

# **What’s Next**

A phased implementation plan, final cost breakdown, and proposed vendor scope of work are underway and will be shared this week. This includes:

* Sequenced rollout plan  
* Final pricing from Zero Sum Defense  
* Internal vs. vendor roles

**Hyla / Amphibian shared implementation \= reduced costs \+ consistent security foundation across both orgs.**

Reach out with questions or feedback anytime.