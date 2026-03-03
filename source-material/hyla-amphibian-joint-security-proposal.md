# SOURCE: Authoritative - Hyla/Amphibian Joint Security Enhancement Proposal
# Fetched from Google Drive (laken@hylafunds.com)

# Hyla/Amphibian Joint Security Enhancement Proposal

## Zero Sum Defense & Archetype Consulting | July 7, 2025

# Overview

Hyla and Amphibian are closely linked with shared staff, operational interdependence, and elevated cyber risk. Recent attacks against affiliated funds have prompted a full review of our security posture. We have found **several fundamental gaps in our protections that present clear and present risk.**

This joint proposal outlines a streamlined path to modernizing and security — closing all major gaps, reducing risk, and aligning technical and policy controls across both companies, while respecting the reality of small, distributed, fast-moving teams.

## Risks and needs

A 360-degree modern security posture for firms like ours consists of several interlocking defenses:

* Device and endpoint management to detect, contain, or prevent compromise on devices critical to ongoing security  
* Strong identity and access controls to reduce account takeover risk and prevent unauthorized access and actions  
* Protection at points of communication — primarily email, Zoom, and customer facing platforms (Telegram, etc)— where attackers most often strike.  
* Continuous monitoring and digital forensics capabilities to respond quickly and effectively when incidents occur.  
* Access governance for sensitive actions, tools, accounts, and financial platforms.

This plan addresses both preventive and detective controls, with scalable tooling that respects lean operations and distributed teams.

**The goal:** an integrated, practical, layered defenses and policies that are implementable by small teams, cost-effective, responsive to the security risks of crypto businesses, and suited to the evolving compliance landscape (especially as Amphibian prepares for RIA status in 2026). 

## Benefits of joint approach

Hyla and Amphibian share several staff, and both have small distributed teams, similar risk profiles, and use many of the same products. A joint coordinated approach will save money and time by performing each phase of work simultaneously for both companies. And there are additional benefits from adopting the same policies and systems: a part-time IT resource can effectively manage the ongoing security program for both companies efficiently, and shared staff can smoothly interoperate.

## Vendors

**Zero Sum Defense (ZSD): Austin Quam** is a fractional CISO and infosec professional with significant infosec experience at Vercel, AWS, and Deloitte, among others.

**Archetype Consulting: Andy Laken** has been acting as fractional Head of IT for Hyla for nine months. He initiated the security review.

The implementation plan targets cost-effectiveness by splitting each phase of work between ZSD and Archetype by skillset.

---

# Project Phases and Outcomes

* Each phase addresses a single layer of current vulnerability or security program gap  
* Each phase performs work that results in specific, demonstrable security value  
* The phases are ordered logically to build on prior work  
* Specific recommended products are **in bold** below

# 🔥 Critical Mitigations

These phases are regarded as security ‘musts’

## 📋 Organizational Prioritization

#### **Phase A**

Meet to align on project outcomes, phased approach, touchpoints, and cadence. Set expectations around work and organizational impact.

## 📥 Email Security

#### **Phase C**

### Why it matters

We rely heavily on email for fund operations and investor comms. Email is also primary for establishing account credentials, password resets, etc. Phishing and [Business Email Compromise (BEC)](https://www.cloudflare.com/learning/email-security/business-email-compromise-bec/) remain top threat vectors, and we’re already experiencing sophisticated attacks. Strengthening email defenses mitigates exposure to social engineering attacks such as impersonation, BEC, account takeover, and delivery of malware. 

### Current

## Basic Google antiphishing / antispam (inadequate)

### Target

* ## Eliminate 95% of phishing / BEC from mailboxes. **Sublime Security** for email threat inspection and custom detection rules. (*nearly completed for Hyla*).

* ## **Valimail** Configure SPF/DKIM/DMARC to secure email sending domains.

## 🛡 Zero Trust Access & Threat Protection

#### **Phase D**

### Why it matters

Today, users access sensitive systems and the open internet from unmanaged networks and devices — with no visibility or control.  That opens the door to phishing & malware. Custom apps like Cyclical and Amphibian Dashboard increase the urgency. **Cloudflare Zero Trust replaces the need for a traditional VPN** — offering secure access to apps and the web, but without the performance, usability, or management tradeoffs.

### Current

Google login is the only gatekeeper. No enforcement based on device, IP, or risk level. No protection against malicious domains or link-based threats.

Target

All user internet traffic is routed through **Cloudflare Zero Trust**, with an agent on each device enforcing security policies. App access (including future internal tools) is limited to verified users on healthy devices. DNS filtering and Remote Browser Isolation protect users from phishing, malware, and exploit links — all invisibly in the background.

## 💻 Securing Laptops and Mobile Devices

#### **Phase E**

### Why it matters

Laptops and phones are often the front door for attackers — especially in lean teams where personal devices double as work machines. Without management tools, there’s no visibility into device health, patch status, or exposure. A single compromised device can give attackers a foothold into email, files, apps, or crypto platforms.

### Current

Devices are fully unmanaged — no centralized control, no mobile policies, no visibility into software or security settings. If a device is lost, stolen, or compromised, there’s no reliable way to lock it down or detect misuse.

Target

* Phones and tablets are enrolled in **Google Workspace Mobile Management**, enforcing screen locks, remote wipe, and basic hygiene standards.  
* All laptops run **CrowdStrike Falcon**, a lightweight security agent that continuously monitors for suspicious behavior like unauthorized access attempts, malware, physical access like USB — and can isolate a device in real time. Together with **Cloudflare Zero Trust**, this gives the team visibility, control, and the ability to stop threats at the device level before they spread.

## 🔐 Secure Factors (Passwords, MFA & Recovery)

#### **Phase F**

### Why it matters

Stolen or reused credentials and poor recovery practices can result in lockouts or compromise.

### Current

**1Password** in use at Hyla but not universal; inconsistent MFA and backup key handling.

### Target

Org-wide password manager usage with enforced MFA and team vaults; increased use of Yubikeys; **Bitwarden** for MFA codes; offline backup codes stored securely.

## 🧠 SaaS Discovery & Risk Management

#### **Phase G**

### Why it matters

Users often adopt AI tools or SaaS platforms without review — leading to unmanaged data exposure, compliance risk, and growing vendor overhead.

### Current

No visibility into what tools are in use, who has access, or what data is flowing through them.

### Target

**Nudge Security** continuously discovers SaaS and cloud accounts, flags risks, and helps the team control app sprawl — enabling safer adoption and better vendor oversight, with cost controls.

## 🧰 Google Workspace Hardening

### Phase H

### Why it matters

Google Workspace is the backbone of communication and collaboration — and a top target for attackers. Without secure settings, sensitive data can be overshared, access can go unchecked, and suspicious activity can go undetected. Workspace also holds key compliance tools, but they require the right tier and configuration to be effective.

### Current

Using a lower-tier Workspace plan with limited security features. No mobile device management, loose admin access, and minimal visibility into risky behavior or sensitive data sharing.

### Target

Upgrade to **Google Workspace Business Plus**, unlocking advanced features like **Vault** for email retention and legal hold, and **Mobile Device Management (MDM)**.

Key controls will be configured:

* **2-Step Verification** enforced across users  
* **Super-admin access** restricted and monitored  
* **Sharing settings** hardened  
* **Log alerts** enabled to flag suspicious behavior  
* **Formalized onboarding/offboarding** tied to Workspace provisioning  
   A lightweight internal review process will help maintain secure configuration over time.

## 🔑 Hardware-Based MFA

#### **Phase I**

### Why it matters:

Phishing-resistant multi-factor authentication (MFA) is one of the most effective ways to block account takeovers — especially for sensitive systems like email, password managers, and crypto platforms. Hardware security keys (like YubiKeys) eliminate the risks of SMS codes, app-based MFA, and social engineering.

### Current

MFA is inconsistent and relies on weaker methods (e.g. SMS, authenticator apps). No backup method is standardized. Lost access or device changes create support and security risks.

### Target

* Every user receives **two YubiKeys** (primary and backup), enrolled across Google Workspace, 1Password, Bitwarden, and any SSO/SSH services in use.  
* Create a registry to track Yubikey serial numbers, usage, and lifecycle status. Security keys are configured for broad compatibility and ease of use — enabling strong MFA without adding friction.

## 🛡 Secure Communications

#### **Phase J**

### Why it matters

Messaging and meeting platforms like **Zoom**, **Signal**, and **Telegram** are frequent targets for social engineering and impersonation — including real-world incidents tied to fake invites and cloned accounts. Without hardened settings and clear protocols, attackers can exploit everyday communication. Strengthening these tools helps reduce risk, build team awareness, and demonstrate proactive controls to regulators and partners.

### Current

Default Zoom settings, naive usage of Telegram, and no consistent hardening or training. No safeguards to verify participant identity or detect impersonation attempts.

### Target

Apply security best practices across Zoom, Signal, Telegram, and similar platforms:

* **Zoom is hardened** with tighter settings (e.g. waiting rooms, screen sharing restrictions, and host verification)  
* **Standard operating procedures (SOPs)** guide safe usage, identity checks, and out-of-band validation  
* **OPSEC practices** are documented and adopted team-wide  
* **Detection tools** may be evaluated to spot and respond to impersonation threats

The goal is safer, smoother collaboration with less exposure to scams or regulatory risk.

## 🔍 Crypto Asset Security

#### **Phase K**

### Why it matters

Critical systems like exchanges, custodians, and banks each have different authentication setups. We need a clear policy and inventory of who has access, how it’s granted, and how it’s protected.

Prevents unauthorized transfers, helps with onboarding/offboarding, and ensures continuity in an emergency. Standardized access patterns and protocols make it easier to detect bad actors. 

### Current

Undocumented access inventory and enforcement.

### Target

Define roles, platforms, and required auth mechanisms (e.g. **Yubikey**, shared 1Password vaults); create auditable record. Detection of attacks against crypto assets.

## 🔒ISMS Program

#### **Phase M**

### Why it matters

Investors and regulators expect documented security governance — especially as Amphibian moves toward RIA registration. A lightweight **ISMS** (Information Security Management System) creates clear accountability, defines key controls, and provides evidence of maturity without excessive overhead.

### Current

No formal security program or documentation. Risk tracking and policies are informal or incomplete.

### Target

Stand up a lightweight ISMS with:

* A top-level **Information Security Policy**  
* Brief, practical procedures for access, vendors, incident response, and more  
* A **risk register**  
* Assigned owners across leadership, IT, and legal (via **RACI**)  
* Evidence collection (e.g. training logs, minutes) for audits or investor review  
* Select policies published in the investor **data room**

## 🕵️‍♀️ Detection platform

#### **Phase N**

Set up a single, centralized system that watches for security issues across all key tools—like Cloudflare, CrowdStrike, Google Workspace, and 1Password. This system pulls in and connects activity from different sources, so you can spot real problems faster without jumping between dashboards. It becomes your main view into what’s happening across the firm’s security environment.

### Why it matters

Without dedicated security staff, it’s easy to miss warning signs across multiple systems. A centralized detection platform enables timely alerts and efficient triage — helping lean teams respond to threats and meet SEC expectations for oversight and incident handling.

### Current

No unified view of security activity. Alerting is siloed across tools (if it exists at all), and there’s no easy way to correlate or investigate events.

### Target

Deploy **RunReveal**, a centralized platform that ingests and correlates signals from tools like Cloudflare Zero Trust, CrowdStrike, Google Workspace, 1Password, and others. Single source of truth for monitoring — connecting the dots between tools, alerting on real risks, and simplifying response.

## 🛠 Amphibian – Custom App Security & Cloud Migration

#### **Phase O**

### Why it matters

Internal apps like **Amphibian Dashboard** built by outside developers often run in shared or informal cloud environments — creating risk around access, monitoring, and long-term control. Migrating them into properly configured org-owned cloud accounts ensures security, ownership, and operational continuity. *Hyla has already completed this work for Cyclical on AWS.*

### Current

Custom internal apps are deployed in third-party-controlled AWS or GCP environments. Possibly lack centralized access management, logging, or consistent security baselines.

### Target

Migrate custom applications into **or Amphibian-controlled AWS/GCP accounts**, configured with:

* Proper **IAM policies**  
* **Logging and monitoring**  
* **Network and API access controls**  
* Enforced **separation of environments** (e.g. prod vs. dev)

This gives the team full control over infrastructure, security, and lifecycle — while maintaining the flexibility to evolve the apps internally or with new vendors.

---

# 💡Recommended Mitigations

## 📱Efani Secure Wireless

#### **Phase B**

### Why it matters

SIM-swap attacks remain one of the highest-impact threats for crypto executives and hedge fund operators. Even without SMS-based 2FA, exposed phone numbers can still enable account resets, impersonation, or support abuse. Efani hardens this vulnerable layer with zero-breach protections and insurance-backed guarantees.

### Current state

* Carrier-level protections (AT\&T, Verizon) are easily bypassed via social engineering  
* No centralized control over SIM/account recovery workflows  
* Risk persists through fallback authentication and number-based recovery  
* Ad-hoc mobile connectivity while traveling

### Target

* Key staff protected by Efani’s 11-layer SIM-swap defense and $5M insurance  
* Unlimited data roaming  
* Optional central POC or self-verification model per user  
* eSIM \+ dual-SIM support for secure global use and VoIP access to U.S. lines abroad  
* Built-in hotspot for secure tethering and mobile backup connectivity

## 📡 Satellite Internet Backup

#### **Phase L**

### Why it matters

Internet outages — whether due to local infrastructure, travel, or targeted disruptions — can delay critical operations and expose the firm to risk. Satellite backup (e.g. Starlink) provides a resilient fallback, keeping key roles online during incidents and supporting business continuity.

### Current

No backup internet connection at home offices or primary work locations. Operations dependent on standard broadband with no failover options.

### Target

Deploy **Starlink** or equivalent satellite internet at key sites, including power backup where needed.

* Enables continued access to trading, communications, and response tools during outages  
* Supports remote staff and leadership in high-dependence roles  
* Includes setup, testing, and lightweight documentation for operational readiness

This ensures that core functions stay online even when primary infrastructure fails — with modest up-front and recurring costs.

---

# Key Risks We’re Addressing

Examples drawn from real-world fund breaches:

* **BEC (Business Email Compromise):** Impersonation leading to fraudulent transfers.  
* **Zoom Malware:** Fake invites delivering remote access trojans.  
* **Telegram Social Engineering:** Clone pages and impersonation leading to compromise.  
* **SaaS Sprawl:** Sensitive data in untracked apps; unmanaged release of data to AI tools.  
* **Lost Devices / MFA Lockout:** No fallback, resulting in urgent bypasses.  
* **Device compromise:** Malware, data exfiltration, keylogging  
* **Insider Risk:** Inadequate access offboarding.

---

# Phase Cost Breakdown Estimates and Durations

| Phase | Deliverable | Products | Est. Duration | Week | Product Cost | Service Cost | Total Cost | Hyla Previous Investment | Hyla Share | Amphibian Share |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| **0** | Analysis & Plan Development |  | — (completed) | — (completed) | $0 | $7,700 | $7,700 | $7,700 | $1,925 | $5,775 |
| **A** | Org Prioritization |  | 2 days | Week 1 | $0 | $600 | $600 |  | $150 | $450 |
| **C** | Email Security | Sublime email & Valimail | 3 days | Week 1 | $0 | $1,200 | $1,200 |  | $300 | $900 |
| **D** | Zero Trust Access & Threat Protection | Cloudflare Zero Trust Access | 1 week | Week 2 | $4,039 | $3,000 | $7,039 |  | $2,770 | $4,270 |
| **E** | Securing Laptops and Mobile Devices | Crowdtrike Falcon EDR | 1 week | Week 3 | $3,564 | $3,900 | $7,464 |  | $2,757 | $4,707 |
| **F** | Secure Factors | 1Password, Bitwarden | 1 week | Week 4 | $3,132 | $1,200 | $4,332 |  | $1,920 | $2,412 |
| **G** | SaaS Discovery & Risk Management | Nudge Security | \<1 week | Week 5 | $2,016 | $1,400 | $3,416 |  | $1,394 | $2,022 |
| **H** | Google Workspace Hardening | Workspace upgrade | 1 week | Week 5 | $5,184 | $3,000 | $8,184 |  | $3,180 | $5,004 |
| **I** | Hardware MFA | Yubikeys | \<1 week | Week 6 | $1,920 | $1,500 | $3,420 |  | $1,575 | $1,845 |
| **J** | Secure Communications | \- | \<1 week | Week 6 | $0 | $2,000 | $2,000 |  | $500 | $1,500 |
| **K** | Crypto Asset Security | \- | \<1 week | Week 7 | $0 | $600 | $600 |  | $150 | $450 |
| **M** | ISMS Program | \- | \<1 week | Week 7 | $0 | $1,100 | $1,100 |  | $275 | $825 |
| **N** | Detection Platform | RunReveal | \<1 week | Week 8 | $3,192 | $3,000 | $6,192 |  | $2,346 | $3,846 |
| **O** | Custom App Security \- Amphibian Dashboard | TBD | 1 week | Week 9 | $0 | $6,500 | $6,500 |  | \- | $6,500 |
|  | **Hyla Prior Investment** |  |  |  |  |  |  | **$7,700** |  |  |
|  | **Hyla Planned Share (Phases A–N)** |  |  |  |  |  |  |  | **$19,242** |  |
|  | **Net Hyla Contribution** |  |  |  |  |  |  |  | **$11,542** |  |
|  |  |  |  |  |  |  |  |  |  |  |
|  | **Critical subtotals** |  |  |  |  | **$36,700** | **$59,747** |  | **$11,542** | **$40,506** |
|  |  |  |  |  |  |  |  |  |  |  |
| **B** | Secure Wireless (Efani) | Efani SAFE | \< 1 week | Week 1 | $4,046 | $800 | $4,846 |  | $200 | $3,634 |
| **L** | Satellite Internet Backup \- 2 sites | Starlink | \<1 week | TBD | $3,558 | $600 | $4,158 |  | $150 | $4,008 |
|  | **Recommended subtotals** |  |  |  |  | **$1,400** | **$9,004** |  | **$350** | **$7,642** |
|  |  |  |  |  |  |  |  |  |  |  |
|  | **Grand totals** |  |  |  |  | **$38,100** | **$68,751** |  | **$11,892** | **$48,148** |

**Notes on cost breakdown:**

| \- Product costs are allocated across orgs based on \# users \- Services costs shared 75/25 Amphibian/Hyla Product costs based on these User Counts: Hyla-only staff: 9Amphibian-only staff: 8Shared staff: 6 |  |  |  |
| :---- | ----- | ----- | ----- |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

---

# Roles and Responsibilities

* **Zero Sum Defense:** Security program design, policy frameworks, tool deployment in certain cases, validation / assessment of implementation, documentation  
* **Archetype Consulting**: Oversee tool deployment, policy enforcement, and staff training.  
* **Security Vendor(s)**: Provide tool configuration support and SME advice as well as incident response as needed.  
* **Hyla and Amphibian Staff**: Install and comply with new security policies and products and participate in training.

# Deliverables Summary

* Configured security tools (Google Workspace profiles, Cloudflare WARP, CrowdStrike, Sublime Security, etc.)  
* Policy documents (device classification, recovery code storage, role-based access, etc.)  
* Training materials (Zoom security, impersonation awareness, etc.)  
* Reports (SaaS inventory, BEC threat analysis, platform access inventory, etc.)

# Acceptance Criteria

* All tools deployed and configured as specified  
* Policies adopted by staff  
* Training completed for all staff  
* Quarterly reports confirm ongoing threat detection and mitigation