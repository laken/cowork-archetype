# SOURCE: 2026 Security - Evolving Threats and Protective Action
# Fetched from Google Drive (laken@hylafunds.com)
# Co-authored: Andy Laken and Andrew Hoppin | December 2025 / January 2026

# CyberSecurity – Evolving Threats and Protective Action

## Urgent security plan for Amphibian and Hyla Teams — Andy Laken and Andrew Hoppin

# TL;DR

* Personal devices and personal networks are now the primary attack surface in crypto. That's us.
* We were directly targeted and successfully compromised via a highly sophisticated malware attack.
* We already had tools to prevent this, they just hadn't been adopted/installed
* Now Hyla and Amphibian leadership and IT strongly recommend adoption of Falcon and WARP to protect personal and company assets

# 1. Context and recent events

Over the past several weeks, we've seen a clear shift in how attackers are targeting individuals and organizations in the crypto/Web3 ecosystem. These are no longer generic phishing attempts or low‑effort scams. Instead, attackers are running **highly targeted, interpersonal attacks** that exploit trust, familiarity, and real‑time communication channels like Telegram and Zoom.

We're sharing this update both to reflect on a recent confirmed incident and to explain why we're moving forward with additional protective measures.

## The current threat landscape

These **sophisticated, multi‑step attacks** blend impersonation, compromised accounts, real‑time calls, and malicious downloads. These attacks are designed to look like normal work interactions and are difficult to detect in the moment.

💥 In December, a Hyla staff member fell prey to a highly sophisticated Telegram impersonation that escalated into a fake Zoom interaction, resulting in a sophisticated malware infection. The impact included several **days of lost productivity**, **extensive cleanup and password resets**, and some personal **financial loss**. In this case, we believe no broader firm systems were compromised – but we were lucky, and it could have easily spread the infection or worse. This underscores how effective and costly these attacks have become.

💥 If the protections below had been in place, we know the attack would have been deflected.

💥 Members of our teams and close associates have also been repeatedly subject to sim-swapping attacks, Telegram impersonation, etc.

# 2. Why we're taking action now

This threat is no longer abstract or "out there." We have been **directly targeted**, and in one case successfully compromised. These attacks are aimed specifically at personal devices and personal networks to bypass institutional safeguards, and they exploit exactly the tools and workflows we use every day.

## Our current vulnerability

We have been operating unprotected in a **BYOD (Bring Your Own Device)** environment without consistent endpoint detection or network-level filtering across all machines. This leaves both company operations **and your personal assets** exposed – even if you're security-savvy, use a VPN, etc.

**Relying solely on individual vigilance is no longer sufficient.**

## What we're doing about it

We've already vetted, purchased, and configured two class-leading security tools that together provide enterprise-grade protection against these threats. These two tools serve **different but complementary purposes**:

* **Cloudflare WARP** protects the *network path* your device uses to reach the internet — blocking nasty domains so your machine can't even download them
* **CrowdStrike Falcon** protects the *device itself* from malware and active compromise – should anything get through WARP

In crypto terms: ***WARP is counterparty risk management for browsing**, and **Falcon is execution-risk containment** if a bad interaction still slips through.*

Using both **significantly** reduces the risk of incidents like the recent fake-Zoom and impersonation attacks.

Enrollment in these protections is now **strongly encouraged** and explicitly endorsed by the leadership of both Hyla and Amphibian. These measures are intended to materially **reduce risk to both company operations and personal assets**, while maintaining clear privacy boundaries. Given recent events, we believe adopting these protections should be the default for anyone doing active work in Hyla and Amphibian environments.

## Privacy concerns

We recognize and respect that some people may be hesitant to apply these protections to a computer they also use for personal matters. If that's you, please have a conversation with **Andy or Andrew** immediately to discuss alternative options.

# 3. Summary of protective actions

## Protection #1: CrowdStrike Falcon

**CrowdStrike Falcon** is the same endpoint protection standard used by hundreds of major firms (e.g. Salesforce, Amazon). It's a next-generation antivirus and malware detection software that runs on your PC/laptop.

**What it DOES:**
* **Stops Attacks:** detect and block malware, ransomware, and suspicious activity.
* **Defends the Device:** from software threats and physical risks (e.g. infected USB drives, Bluetooth etc)
* **Isolates Infections:** In a security incident, IT can isolate your device from the network to stop the spread of infection or data theft.

**What it DOES NOT do:**
* It **does not** read your emails, Signal/Telegram chats, or documents.
* It **does not** record your screen, keystrokes, webcam, or microphone.

**Real-Time Response (RTR):** In **rare, confirmed attacks**, a secured administrator can temporarily run limited commands on your device to kill malicious processes or clean up the infection. **This access is time-bound, audited, and not used for routine monitoring.**

**Who has ACCESS:**
Currently only two people have access to the Crowdstrike console with the ability to view enrollments and take response actions: Andy Laken (Hyla IT/infosec) and Austin Quam (Zero Sum Defense / Fractional CISO)

## Protection #2: Cloudflare WARP

### Why DNS matters for security

Every internet connection starts with DNS — a lookup that reveals **which domains your device is trying to reach**, even if the rest of the traffic is encrypted. All web browsing, email, chat protocols, APIs — every communication on the internet rests on DNS.

Without WARP, DNS is typically handled by whatever network you're on (Home ISP, hotel, café Wi‑Fi, airline WiFi). Those providers commonly log your DNS requests with no transparency or accountability, and with unknown retention and no consistent protections.

Your personal DNS data is often abused:
* US ISPs have admitted long-term DNS retention and monetization
* Data brokers sell "domain visitation" and "interest category" data
* Law enforcement routinely subpoenas DNS logs for attribution

### What WARP is for (plain-language summary)

Cloudflare WARP protects against attacks that occur **over the network itself**, especially when working from home, coworking spaces, hotels, or public Wi‑Fi.

In simple terms, it:
* Blocks malicious links or domains **before they load**, no matter where they originate (email, chat, web, or background processes)
* Reduces exposure to attacks before they reach your browser or device
* Encrypts network traffic between your device and Cloudflare (similar to a VPN) but also protects all your DNS lookups from your home ISP and public wifi providers.
* Allows protections to adapt as threats evolve, without inspecting personal content

### Why personal VPNs don't reliably solve this

Some personal VPNs route DNS through their own systems; others do so inconsistently. In practice:
* DNS behavior varies by VPN, operating system, and network
* DNS can silently fall back to the local ISP or Wi‑Fi resolver
* Users usually have no visibility when this happens

As a result, a VPN alone does **not reliably guarantee** predictable or protected DNS.

### What WARP changes

When WARP is **enabled**:
* DNS is explicitly routed through Cloudflare instead of a random local network
* DNS traffic is encrypted
* Known phishing, malware, and impersonation domains are blocked before connection
* Behavior is consistent across home, travel, and public Wi‑Fi
* Logging scope and access are clearly defined and governed

When WARP is **disabled**, traffic does not pass through Cloudflare and **no Cloudflare DNS or network logging occurs**.

### Privacy boundaries, retention, and access controls

WARP provides **network‑level protection only**. It does not inspect or decrypt page content, messages, files, form inputs, or keystrokes.

For security purposes, WARP logs limited **DNS metadata only** (domain names, not URLs or in‑site activity), retained for a **short, rolling period** based on our configuration.

**Guardrails:**
* DNS logs are accessed **only** for threat detection, incident investigation, or user‑reported issues
* Access is restricted to named security administrators (currently Andy Laken and Austin Quam)
* Routine, exploratory, or productivity monitoring is **expressly forbidden**
* Any admin access is **audited and time‑bounded**

Our current deployment retains DNS logs for a **minimal period** (currently 24 hours).

### User Control

While not recommended, in our current setup, you may disable WARP for personal activity. When WARP is **off**, no Cloudflare traffic or logging occurs — and you lose all WARP protections.

### WARP and VPNs

* WARP is itself a VPN-style encrypted tunnel.
* For most users who run a consumer VPN primarily for **network privacy or safety on public Wi‑Fi**, WARP already provides equal or better protection.
* Running two VPNs at the same time often causes connectivity problems.
* If you use another VPN: disconnect WARP while using the other VPN, then reconnect WARP afterward — or use WARP alone for day‑to‑day work networking.
* WARP does not provide geo‑location shifting or anonymity services.
