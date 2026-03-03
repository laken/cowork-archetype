# SOURCE: Principals: Joint Security Executive Overview: Hyla + Amphibian
# Fetched from Google Drive (laken@hylafunds.com)

# Joint Security Executive Overview:  Hyla \+ Amphibian Andy Laken | 2 June 2025

*Pressed for time? [Condensed version available here](https://docs.google.com/document/d/1AJ_HkRq6bosbJF1tDFFGNJp3LCaJ8EZ9JgNCn7gDhio/edit?tab=t.0#heading=h.q3n9hbqn0274)*

This document outlines the proposed security posture improvements across both **Hyla** and **Amphibian**. These two closely linked crypto investment firms share staff roles, operational dependencies, and elevated risk profiles. By pursuing a coordinated approach to security upgrades, we reduce cost, implementation overhead, and inter-org friction, while addressing risk & aligning on capabilities  that protect both firms and all individuals involved

Recent successful attacks and cyber theft at some underlying funds spurred us last week to examine our security posture and develop a pragmatic plan to significantly improve our operational and information security posture.

**Amphibian** is approaching SEC RIA threshold status in 2026 and is actively planning toward increased compliance obligations. **Hyla** has already implemented basic email authentication measures and initiated adoption of advanced email protection. The goal is to expand and unify these efforts across both organizations, ensuring comprehensive coverage in the areas of devices, access control, monitoring, and recovery.

A 360-degree modern security posture for firms like ours consists of several interlocking defenses:

* Device and endpoint management to detect, contain, or prevent compromise on devices critical to ongoing security  
* Strong identity and access controls to reduce account takeover risk and prevent unauthorized access and actions  
* Protection at points of communication — primarily email, Zoom, and customer facing platforms (Telegram, etc)— where attackers most often strike.  
* Continuous monitoring and digital forensics capabilities to respond quickly and effectively when incidents occur.  
* Access governance for sensitive actions, tools, accounts, and financial platforms.

This plan addresses both preventive and detective controls, with scalable tooling that respects lean operations and distributed teams.

We are working closely with a third-party operational security vendor, **Austin Quam** of **Zero Sum Defense**, whose resume includes offensive security, security consulting, and IT experience including leadership roles at **Vercel** and **AWS**. He is preparing a detailed proposal and Statement of Work to guide a phased rollout of the recommended tools, configurations, and policy upgrades as well as ongoing program support to meet compliance objectives and provide a path for security escalation as needed. Implementation work would be split between myself and external vendor to optimize for skillset and cost.

The following security layers are proposed for joint planning and implementation.

---

## **💻 Devices & Connections**

**Hyla** staff use an unmanaged mix of personal computers, smartphones, tablets and other devices. Many of these are dual-use work/personal devices. We need to roll out lightweight management of personal devices — appropriate by user role and device — to protect our data and applications especially in the case of lost or compromised devices. These steps will provide a defensible foundation while protecting user privacy and data, improving security on an individual level. 

**Current:** Fully unmanaged BYOD (Bring Your Own Device), no endpoint visibility or controls.

**Target:** Use [**Google Workspace** mobile profiles](https://workspace.google.com/products/admin/endpoint/) for iOS/Android; rely on [**Cloudflare Zero Trust agents**](https://www.cloudflare.com/learning/access-management/what-is-ztna/) and **CrowdStrike** agents to actively secure and defend PC/Mac endpoints.

**Why It Matters:** Endpoint security is foundational. With trading and investor data flowing through personal machines, any single device compromise could create major risk. And without appropriate context security events cannot be successfully detected or responded to.

*Joint Context:* **Amphibian** has similar device diversity and usage patterns. Coordinated rollout across both orgs will streamline device classification, onboarding, and posture monitoring.

---

## **📡 Resilient Connectivity & Secure Wireless**

Our teams depend on mobile connectivity for access to critical systems, especially during travel or emergencies. At the same time, mobile numbers are a known weak point in many authentication flows. SIM swaps and internet outages have both contributed to operational disruption and loss in crypto environments.

**Current:** Standard mobile carriers with weak account protections; no backup internet connectivity for key roles or offices

**Target:** Enable **Starlink** or equivalent at key sites for continuity; offer **Efani** secure eSIM service for principals and high-risk users as a fallback line for the most sensitive communications and credentials

**Why It Matters:** SIM swap attacks remain a common method of account takeover, especially in crypto. **Efani** dramatically reduces this risk with strict onboarding and real-time monitoring. **Starlink** ensures reliable internet access during outages, natural disasters, or targeted disruptions — supporting operational continuity and incident response.

*Joint Context:* Shared staff across **Hyla** and **Amphibian** often handle high-value transactions or sensitive operations while remote. Secure mobile service and internet failover protect both security and continuity at a modest cost.

---

## **📥 Email Security**

Phishing remains the top threat vector. We rely heavily on email for fund operations and investor comms. Strengthening email defenses mitigates exposure to social engineering attacks such as impersonation, [Business Email Compromise (BEC)](https://www.cloudflare.com/learning/email-security/business-email-compromise-bec/)  and delivery of malware. 

**Current:** **Google Workspace** protections only (SPF/DKIM/DMARC \+ native filters)

**Target:** Adopt [**Sublime Security**](https://sublime.security/) for pre-delivery inspection and anomaly detection; ongoing tuning based on threat patterns – proactively screening and addressing email related risks. 

**Why It Matters:** Phishing, spoofing, and malware-laced messages are still the \#1 cause of breaches in financial and crypto orgs. Sublime is the state of the art detection engine for email security. 

*Joint Context:* **Hyla** has completed email authentication setup and is deploying **Sublime**; **Amphibian** can adopt the same playbook with cost and implementation efficiencies.

---

## **🔐 Passwords & MFA**

Most of **Hyla** uses **1Password** for credentials, but adoption is not yet universal. MFA is inconsistent and sometimes reliant on insecure backup methods.

**Current:** **1Password Teams** in use, not mandated; some MFA via SMS or multiple apps

**Target:** Universal use of **1Password** with enforced MFA and shared vaults for team-critical credentials

**Why It Matters:** Strong secrets hygiene helps block both targeted and opportunistic account takeovers.

*Joint Context:* A shared rollout for both orgs will ensure consistency across shared staff roles and critical platforms. *Need to ascertain current Amphibian Password / MFA tools.*

---

## **🧩 MFA Fallback & Recovery Security**

Even the best MFA is useless if you lose access and can’t recover. Backup codes and **TOTP** (i.e. authenticator codes) are critical recovery layers that need proper storage, and MFA support will vary by platform.

**Current:** No consistent policy for storing account recovery codes; **TOTP** codes are spread across multiple tools with no clear backup

**Target:** Centralize **TOTP** account codes in **Bitwarden**, and store printed recovery codes (used to regain access if MFA device is lost) in physical safe — not in any cloud storage.

**Why It Matters:** These are *not* crypto wallet keys — they're backup access methods for systems with multi-factor authentication. Without them, a lost or broken phone could permanently lock someone out of critical platforms like exchanges or banking.

*Joint Context:* Shared tools like **Bitwarden** can be used with role separation across orgs; centralizing recovery practices avoids future lockouts and confusion. Separating access by software supplier (using Bitwarden for some use cases and 1Password for others) mitigates risk of upstream supplier compromise. 

---

## **👩‍💻 Application Access & Segmentation**

**Hyla** and **Amphibian** rely on a mix of cloud, SaaS, and internal tools to operate. And we access these often from personal devices and various geographies. And soon we’ll be adding more ‘attack surface’ with Hyla’s Cyclical app and Amphibian Dashboard. Today, access is generally wide open once you’re logged in. We want to introduce more precise, role-based controls that take context (like geography & device security) into account — without adding friction for users.

**Current:** **Sign In With Google** login controls only; broad access to most internal docs. Poor / inconsistent setup of roles, groups, and folder permissions in Dropbox.

**Target:** Enforce [**Cloudflare Access**](https://www.cloudflare.com/zero-trust/products/access/) for role-based zero-trust control of key apps; tighter document sharing policies; SSO preferred.

**Why It Matters:** Role-based controls \+ device posture checks prevent data leakage and lateral movement. This will mitigate risk around unauthorized access. 

*Joint Context:* **Hyla** and **Amphibian** are planning internally-hosted apps; joint [**Cloudflare Access**](https://www.cloudflare.com/zero-trust/products/access/) adoption will provide consistent enforcement without traditional VPN infrastructure and provide better assurance around application usage

---

## **🧠 SaaS Account Awareness, Visibility, and Spend Control**

Across both firms, staff rely on dozens of third-party SaaS tools — from productivity platforms to AI assistants — often signing up ad hoc using Google logins. These accounts are typically unmanaged, unaudited, and may persist long after use. This introduces risk of data leakage, unauthorized access, and redundant spend.

Knowing who is using which apps gives us a more complete threat picture. SaaS visibility also reduces [**shadow IT**](https://www.grip.security/glossary/shadow-it) and access sprawl, and **helps us audit and manage SaaS spend**.

**Current:** No centralized view of SaaS usage or access

**Target:** Deploy [**Nudge Security**](https://www.nudgesecurity.com/) to monitor and manage SaaS footprint

**Why It Matters:** Even one compromise of a user inside SaaS applications can provide adversaries with information access and direct access to shared data. Prevents data from leaking into unmonitored or unauthorized tools; identifies unauthorized logins or connected apps; audits accounts, licenses, and spending across all our SaaS tools.

*Joint Context:* Shared staff roles often involve multiple SaaS tools across both orgs — centralizing visibility helps reduce duplication and blind spots. 

---

## **🧬 Endpoint Detection & Response (EDR)**

**Endpoint** refers to any user device — typically laptops, desktops, and mobile devices — that connects to company systems. These are common targets for attackers because they serve as entry points to sensitive data and infrastructure.

**EDR** is modern security software for computers and laptops. It goes far beyond traditional antivirus — it watches for suspicious behavior in real time, such as unusual logins, unauthorized software activity, or attempts to send sensitive data out of the network. It also **controls physical access attacks** like malicious use of USB ports or other vectors that are possible with physical access to a machine. 

**Current:** No endpoint monitoring in place

**Target:** Deploy [**CrowdStrike Falcon**](https://www.crowdstrike.com/en-us/platform/endpoint-security/) (or comparable EDR) to all work devices

**Why It Matters:** If a device is compromised — for example, by malware from a phishing link — EDR can detect the threat quickly, alert our team, and automatically block the activity. It acts as a “security camera \+ alarm system” for every laptop.

*Joint Context:* EDR tools typically offer volume licensing discounts — coordinating deployment will cut cost and ensure coverage for all shared staff.

---

## **🔍 Platform Access & Financial Ops**

Critical systems like exchanges, custodians, and banks each have different authentication setups. We need a clear policy and inventory of who has access, how it’s granted, and how it’s protected.

**Current:** Access spread across users/devices, mix of MFA methods, no clear inventory

**Target:** Define roles, platforms, and required auth mechanisms (e.g. **Yubikey**, shared vaults); create auditable record

**Why It Matters:** Prevents unauthorized transfers, helps with onboarding/offboarding, and ensures continuity in an emergency. Standardized access patterns and protocols make it easier to detect bad actors. 

*Joint Context:* **Hyla** and **Amphibian** both use **Anchorage** and **Coinbase** platforms — sharing a common access framework ensures continuity and mitigates transaction risk.

---

## **🛡 Secure Communications**

Set up clear security settings and simple how-to guides for tools like **Zoom**, **Signal**, and **Telegram** to help the team use them safely and effectively. Define best practices for avoiding scams, verifying identities, and protecting sensitive conversations. Optionally, explore tools that detect and remove fake or impersonating accounts targeting the firm. Some of the breaches seen among underlying funds Hyla were initiated via fake Zoom scams.

**Current:** Standard **Zoom** configuration; no consistent hardening policies applied. Naive Telegram usage.  
**Target:** Cloud configuration of communication platforms and detection of unauthorized or risky usage

**Why It Matters:** Messaging platforms are frequent targets for social engineering and impersonation. Clear protocols and basic OPSEC practices reduce risk, improve team awareness, and help demonstrate proactive controls to regulators and partners.

---

## **🌐 DNS Filtering & Threat Blocking**

Both **Hyla** and **Amphibian** rely heavily on internet-based tools and communications. Attackers frequently use malicious links or domains to deliver malware, steal credentials, or impersonate trusted services like **Zoom**, **Google Docs**, or fund admins.

**Current:** No centralized DNS policy; users may reach malicious domains if clicked

**Target:** Use [**Cloudflare Gateway**](https://cf-assets.www.cloudflare.com/slt3lc6tev37/KsZKn2TJN1wboqzbUeVS0/655f2f026eea7ad7a4e3cbb77aa979ed/Secure_Web_Gateway__Cloudflare_Gateway__-_Product_Overview.pdf) DNS filtering to block known threat domains, phishing links, and malware infrastructure

**Why It Matters:** DNS filtering stops many attacks *before* they reach the browser — it’s a low-friction, high-impact layer that protects against human error and evolving threat infrastructure.

*Joint Context:* A unified DNS policy across both orgs adds protection without requiring changes to end-user behavior — and is especially powerful in blocking social engineering payloads.

---

## **Risk Spotlights**

These examples reflect real-world incidents observed across the crypto investment landscape, including cases that have impacted funds in our network. Each highlights a different class of threat, and underscores the importance of multiple, overlapping layers of defense.

### **Business Email Compromise (BEC)**

[**BEC**](https://www.cloudflare.com/learning/email-security/business-email-compromise-bec/) attacks — often impersonating colleagues or fund admins — remain the most frequent threat we face. Successful cases have resulted in large crypto transfers to malicious wallets. These attacks are highly targeted, subtle, and can bypass less advanced email protections.

🛡 **Primary Defense:** **Sublime Security** for pre-delivery detection, quarantine and pattern analysis; **Cloudflare Zero Trust** for app access segmentation

### ---

### **Zoom-Based Malware**

Several recent losses across our fund network originated from attackers spoofing **Zoom** invites, luring users into downloading fake updates or plugins that deployed C2 (command and control) malware. These attacks are particularly dangerous because they mimic a familiar platform used daily by staff.

🛡 **Primary Defense:** Hardened **Zoom** settings \+ **Cloudflare Gateway** DNS filtering to block malicious domains

### ---

### **Telegram-Based Social Engineering**

**Telegram** has become a high-risk platform in the crypto ecosystem due to its informality, speed, and lack of native security enforcement. Attackers frequently pose as fund representatives, partners, or even internal staff to initiate contact. From there, they may lure targets into fake group chats, spoofed login pages (e.g. **Zoom**), or request sensitive information under time pressure.

One particularly damaging variant involved **impersonation** via Telegram that led to a link for a cloned Zoom login page. The page deployed malware granting remote access and ultimately resulted in the theft of crypto assets. This is just one example of how Telegram can be used as a launchpad for sophisticated social engineering and malware delivery.

🛡 **Primary Defense:** **Cloudflare Gateway** DNS filtering to block fake Zoom/C2 domains; **Zoom** hardening; internal training to recognize impersonation attempts; standardized usage protocols for tools like **Zoom** and **Telegram**; strong account protection via **1Password** and enforced **MFA** to prevent takeover of team identities.

### ---

### **Endpoint Compromise via Malware or Infected USB**

A staff member unknowingly runs malicious software — from a phishing email, cracked app, or compromised USB drive — allowing attackers to take control of the device, capture credentials, and move laterally into connected services.

🛡 **Primary Defense:** **CrowdStrike Falcon EDR** monitors device behavior in real time, automatically flagging and isolating suspicious activity. **WARP agent posture checks** add a second line of defense.

---

### **Untracked SaaS Sprawl & Shadow IT**

Staff regularly sign up for SaaS tools using work emails — from AI tools to file-sharing platforms — without centralized oversight. Over time, these tools accumulate sensitive data, become forgotten, and may be breached or misused.

🛡 **Primary Defense:** **Nudge Security** discovers all SaaS tool usage across both orgs, flags risks, and enables cleanup or policy enforcement. This also reveals overlapping spend and unused services.

---

### **Insider or Former Employee Access Risk**

Without a clean, auditable record of who has access to what — especially for banking, custody, or file-sharing platforms — there’s a real risk of **inadvertent leaks** or **malicious use** by former staff or contractors.

🛡 **Primary Defense:** Formalizing platform access via **1Password**, **Yubikey**, and shared access inventory ensures tighter onboarding/offboarding, while **Cloudflare Access** enforces role-based policy.

---

### **Device Loss or Account Lockout**

A phone with MFA codes is lost or damaged, and the user can’t regain access to banking, custodian, or trading platforms — or worse, is tempted to bypass security out of urgency.

🛡 **Primary Defense:** Standardized **TOTP fallback recovery** via **Bitwarden**, with secure offline backup codes and enforced MFA policy, avoids business disruption during emergencies.

## **Next Steps**

A detailed **phased implementation plan**, **cost estimate**, and **division of responsibilities** are currently in development in collaboration with **Zero Sum Defense**. These supporting materials will outline:

* Priority sequencing of each security upgrade  
* Estimated vendor and implementation costs  
* Roles and responsibilities across **Hyla**, **Amphibian**, and external partners

These documents will be shared this week (2 June)  to inform decision-making and support rollout planning. Upon review we may decide to solicit bids from other vendors as well.