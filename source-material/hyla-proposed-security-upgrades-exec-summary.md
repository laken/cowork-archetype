# SOURCE: Hyla Proposed Security Upgrades Exec Summary
# Fetched from Google Drive (laken@hylafunds.com)

# Hyla Proposed Security Upgrades Executive Summary

## Andy Laken | 2 June 2025

Recent successful attacks and cyber theft at some underlying funds spurred us last week to examine our security posture and develop a pragmatic, quick, and cost-effective plan to significantly improve Hyla's operational and information security posture.

The plan is being developed by Andy Laken in collaboration with Austin Pham, who is a potential consultant for some of the implementation. It's been run by Andrew Hoppin as it's evolved.

We also plan to check it with Amphibian for two reasons: 1\) they may want to participate simultaneously (potential cost-sharing and benefit getting us all on most of the same systems/protection), 2\) ensure it's compatible with their upcoming compliance needs (thus will check w/Harris at Aspect advisors also).

This document outlines Hyla's current and target security posture in key operational areas. Each section includes a brief overview, current state, desired future state, and rationale for change.

---

## **💻 Devices & Connections**

Hyla staff use an unmanaged mix of personal computers, smartphones, tablets and other devices. Many of these are dual-use work/personal devices. We need to roll out lightweight management of personal devices — appropriate by user role and device — to protect our data and applications.

MDM (Mobile Device Management) allows us to enforce basic security standards like **full-disk encryption**, **screen lock**, **OS updates**, and **remote wipe in case of loss/theft** — without accessing personal content.

**Current:** Fully BYOD (Bring Your Own Device), no endpoint visibility or controls, no MDM

**Target:** Deploy Google Workspace MDM for laptops/desktops, initially Mac and Windows; evaluate optional mobile MDM.

**Why It Matters:** Endpoint security is foundational. With trading and investor data flowing through personal machines, any single device compromise could create major risk.

---

## **📥 Email & Message Security**

Phishing remains the top threat vector. We rely heavily on email for fund operations and investor comms. Strengthening defenses here reduces exposure to impersonation and malware.

**Current:** Google Workspace protections only (SPF/DKIM/DMARC \+ native filters) \- significant spam and phishing (basic and advanced) are getting through

**Target:** Adopt Sublime Security for pre-delivery inspection and anomaly detection; ongoing tuning based on threat patterns. *Currently trialing this and getting ready to deploy*

**Why It Matters:** Phishing, spoofing, and malware-laced messages are still the #1 cause of breaches in financial and crypto orgs.

---

## **🔐 Passwords, secure notes, & MFA**

Most of our team uses 1Password for credentials, but adoption is not yet universal. MFA is inconsistent and sometimes reliant on insecure backup methods. Some storage of sensitive passwords in unmanaged systems (e.g. chrome password storage)

**Current:** 1Password Teams in use, not mandated; some MFA via SMS or multiple apps

**Target:** Universal use of 1Password with enforced MFA and shared vaults for team-critical credentials. 1Password also used for secure storage/sharing of other sensitive info: bank acct credentials, etc.

**Why It Matters:** Strong secrets hygiene helps block both targeted and opportunistic account takeovers.

---

## **🧩 Fallback & Recovery Security**

Even the best MFA is useless if you lose account access and can't recover. Backup codes and MFA codes are critical recovery layers that need proper storage.

**Current:** No consistent policy for storing account recovery codes; TOTP codes are spread across multiple tools with no clear backup.

**Target:** Centralize MFA account codes in Bitwarden, and store printed recovery codes in physical safe or safe-deposit — not in any cloud storage

**Why It Matters:** Without them, a lost or broken phone could permanently lock someone out of critical platforms like exchanges or banking.

---

## **👩‍💻 Application Access & Segmentation**

**Current:** Access to most tools and documents is broad; login is via Google Workspace but without device checks or role restrictions

**Target:**
* Use Cloudflare Access to protect sensitive tools and dashboards, allowing access **only if the right person is using a secure device**.
* Improve document sharing practices to reduce overexposure.
* Prefer tools that support Single Sign-On (SSO).

**Why It Matters:** Role-based access controls and real-time checks help stop lateral movement before it leads to deeper compromise.

---

## **🧠 SaaS Account Awareness, Visibility, and Spend control**

**Current:** No centralized view of SaaS usage, account ownership, or spend

**Target:** Deploy Nudge Security or similar tool to inventory SaaS tools, identify account usage, and surface potential risks or redundant spend.

**Why It Matters:** Prevents data leakage through unsanctioned tools, flags unauthorized access or misuse, and improves cost control.

---

## **🧬 Endpoint Detection & Response (EDR)**

**Current:** No endpoint monitoring in place

**Target:** Deploy CrowdStrike Falcon (or comparable EDR) to all work devices

**Why It Matters:** If a device is compromised — for example, by malware from a phishing link — EDR can detect the threat quickly, alert our team, and automatically block the activity.

---

## **🔍 Platform Access & Financial Ops**

**Current:** Access spread across users/devices, mix of MFA methods, no clear inventory

**Target:** Document current platform security requirements and internal policies — roles, platforms, and required auth mechanisms (e.g. Yubikey, shared vaults); create auditable record.

**Why It Matters:** Prevents unauthorized transfers, helps with onboarding/offboarding, and ensures continuity in an emergency.

---

## **🛡️ Risk Spotlight: Ransomware Defense**

**How We're Addressing It:**

* **Email Security (Sublime):** Blocks common delivery methods like phishing attachments and malicious links.
* **EDR (CrowdStrike):** Detects unusual behavior and can halt ransomware processes before they spread.
* **Device Management (MDM):** Enforces updates, restricts risky software, and isolates compromised devices.
* **Vault Hygiene (1Password):** Prevents stolen credentials from giving ransomware actors initial access.
* **Zero Trust Access (Cloudflare):** Limits lateral movement, even if one system is compromised.

**Why It Matters:** A single ransomware incident could block access to banking, exchanges, or investor communications — or worse, leak sensitive data. This layered approach greatly reduces our exposure.
