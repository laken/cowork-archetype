# SOURCE: BYOD Transparency & Informed Consent
# Fetched from Google Drive (laken@hylafunds.com)

# HYLA: BYOD Transparency & Informed Consent

## Version 1.1 – October 8, 2025

As a crypto hedge fund, we operate in a high-risk environment — managing assets, trading, interacting with crypto custodians, exchanges, company banking partners, and HNWIs. 

Hyla staff access company tools and transact company business primarily on personally-owned devices ([BYOD](https://www.ibm.com/think/topics/byod)). Hyla installs and manages security tools on devices that impact the security of company systems and operations to protect the company, assets, and customers.

These security tools are widely used by leading security-conscious organizations including Amazon, Salesforce, and other major firms. They defend against real emerging threats such as zero days and physical risks to computers but also have privacy implications. This document explains what each tool does and doesn’t do, who can use them, and how we balance their power with protecting your privacy. 

We value your trust and your privacy. Please read carefully, ask questions if anything is unclear, and know that we require your **informed consent (per user and per device)** before these tools are installed.

# 1\. Security Tools We Use

## A. CrowdStrike Falcon (Endpoint Detection & Response — EDR)

### Where it runs

Agent installed on corporate or BYOD laptops/desktops (Mac or Windows)

### What it does

* Detects malware, ransomware, unauthorized programs, and suspicious activity.  
* Collects **telemetry**: metadata about running processes, file activity, system configuration, and **network traffic patterns**.  
* Quarantines or blocks malicious files and code processes.  
* Protects USB ports, Bluetooth etc from physically introducing devices with malware  
* Alerts security staff if the device shows signs of compromise.  
* Allows responders to **contain a device** (cut it off from network communication while leaving the user logged in, to prevent spread of an infection).  
* In rare cases, allows an **administrator-level Real Time Response (RTR)** session, which opens a secure command line on *your laptop/computer*. RTR can:  
  * Kill malicious processes  
  * Delete malware files  
  * Upload or download files for forensic investigation  
  * Run scripts to clean or repair the system

### What it does not do

* Does not record or monitor your keystrokes, webcam, or microphone.  
* Does not capture the contents of your emails, documents, chats, or web sessions.  
* **What telemetry means:** Falcon sees *system events* (e.g., “Chrome process made a network connection to example.com at 2:15pm”), but not the full page you viewed, messages exchanged, or files opened.  
* In other words: Falcon collects **metadata about system activity** for security, not the *contents of personal activity.*

### What admins can do (on your computer)

* **Contain**: Isolate your computer from the network to stop spread of malware or data theft. You can still use the machine locally.  
* **Investigate**: View and analyze flagged processes or suspicious files.  
* **RTR session**: Temporarily open an admin-level shell to run limited commands directly on your computer for threat remediation. This is used only in confirmed or strongly suspected security incidents.

### Audit & logging

* Every RTR session, containment action, or file operation is logged automatically by Falcon and cannot be deleted by responders.

## B. Cloudflare Zero Trust / WARP Client

*The Domain Name System (DNS) is how devices translate website names into IP addresses; protecting DNS is critical because attackers often exploit it to redirect traffic or deliver malware.*

### Where it runs

* WARP is installed on BYOD laptops (and potentially phones).  
* It creates an encrypted connection to Hyla’s Cloudflare Zero Trust Gateway.

### What it does

* Routes DNS lookups and network traffic through Hyla’s Cloudflare Zero Trust service.  
* **Encrypts all DNS traffic** with HTTPS/TLS (your ISP can no longer log what sites you visit\!)  
* Applies Hyla’s DNS-level security policies to block known harmful domains (e.g. *Phishing, Malware, Spyware, Command & Control, DNS Tunneling,* and *Cryptomining* sites).  
* Reports basic “device posture” checks such as whether CrowdStrike Falcon is running and the operating system is up to date.  
* Logs DNS-related metadata (e.g., which domains were queried, timestamp, and policy result) to the Cloudflare Gateway console.  
* **Does not** inspect or decrypt the content of web pages, emails, messages, or files.  
* Administrators see only domain-level information (for example, *that your device looked up coinbase.com*, not which account or page you visited).

### Current configuration (BYOD baseline)

* WARP operates in **Gateway-with-WARP (DNS-only)** mode.  
* This means the Gateway enforces DNS-based threat blocking but **does not proxy or decrypt** any web content.  
* Users may see a standard browser “site not found” message when a domain is blocked; visual Cloudflare block pages appear only if Secure Web Gateway mode is later enabled.

### Future configuration (possible enhancement)

* In the future, Hyla may upgrade WARP to **Secure Web Gateway (full HTTP/HTTPS proxy)** mode for selected devices or roles.  
  * This would allow more granular filtering—such as blocking risky file downloads or enforcing safe-browsing policies—and would display branded Cloudflare “block” pages instead of generic browser errors.  
* Hyla may also introduce **Remote Browser Isolation (RBI)** for certain high-risk categories, which would safely open web pages in a remote Cloudflare container so that no code executes locally on the device.  
* If either of these changes is planned, staff will receive advance notice and a revised consent document describing the new level of visibility and control.

### What it does not do

* Does not log or store the contents of web pages, emails, chats, or files.  
* Does not view, record, or analyze what you read, write, or send online.  
* Does not decrypt HTTPS traffic or capture information entered into websites.  
* Does not use DNS data for HR, productivity monitoring, or any purpose other than threat detection and network protection.  
* While DNS lookups can reflect the domains you visit, this information is limited to **domain names only** (e.g., *coinbase.com*)—not the specific pages, messages, or accounts you access.

### What administrators can do

* View DNS metadata and policy actions for work-related traffic routed through the Gateway.  
* Adjust or add DNS-level security policies.  
* Contain or revoke access if a device shows clear compromise or policy violation.  
* All administrative actions and log queries are automatically recorded in Cloudflare’s audit system.

### Audit & logging

* Each DNS request is logged with its result (Allowed / Blocked) and category.  
* Logs are retained only for security and compliance purposes under Hyla’s data-retention policy.  
* Any expansion to content inspection or longer-term log retention would require updated notice and consent.

## C. Google MDM (Mobile Device Management)

### Where it runs

Profiles installed on BYOD mobile devices (iOS/Android) and laptops enrolled in Google Workspace management.

### What it does

* Enforces security settings such as screen lock, disk encryption, and OS patch levels.  
* Can require that certain apps (like Gmail or Drive) only run on compliant devices.  
* Allows IT to remotely **wipe company data** from a lost or stolen device.  
* Provides basic inventory (device type, OS version, compliance status).

### What it does not do

* Does not give IT access to your personal apps, personal files, or personal usage.  
* Does not track GPS location unless explicitly configured (we do not enable location tracking).  
* Does not monitor texts, calls, or photos.

### What admins can do

* Enforce compliance checks (e.g., device encryption enabled).  
* Block access to work apps on non-compliant devices.  
* Remotely remove company apps/data if the device is lost or you leave the organization.

### Audit & logging

* All device management actions (wipes, access restrictions) are logged in Google Workspace.

## D. Nudge Security (SaaS / Shadow IT Discovery)

### Where it runs

Cloud-only; connects to your work Google account.

### What it does

* Detects apps and services connected to your work Google account.  
* Flags risky OAuth permissions or unapproved SaaS tools.  
* Helps us manage SaaS sprawl and control sensitive data exposure.

### What it does not do

* Does not access your personal Gmail or personal apps.  
* Does not monitor activity on your device.

### What admins can do

* Review apps linked to your work identity.  
* Recommend safer, approved alternatives.

### Audit & logging

* All app discovery is tied to work accounts only.

## E. Google Workspace Administration

### Where it runs

Cloud-side (Google Admin Console).

### What it does

* Allows admins to reset passwords, enforce 2FA, manage group access.  
* Maintains audit logs of account and file activity.

### What it does not do

* Does not continuously monitor your emails or documents.  
* Does not provide covert or unlogged access.  
* Does not affect personal Gmail or other accounts.

### What admins can do

* Manage access and group memberships.

### Audit & logging

* Google automatically records all admin actions.

## F. Sublime Security (Email Threat Detection & Analysis)

### Where it runs

Cloud-only. Sublime connects to company-managed Google Workspace email via secure API integration. No software or agent is installed on user devices.

### What it does

* Continuously scans inbound, outbound, and internal messages for phishing, spoofing, malware, and other suspicious indicators.  
* Analyzes sender reputation, URLs, attachments, and headers to detect threats that native Workspace filtering may miss.  
* Provides dashboards and alerts so IT and the CISO can review potentially malicious messages and tune detection rules.  
* Retains only the message data required for analysis, following SOC 2–compliant retention and deletion policies.

### What it does not do

* Does not monitor or access personal Gmail or non-company email accounts.  
* Does not use email data for any non-security purpose such as employee monitoring or HR review.  
* Does not store message bodies indefinitely; retention aligns with security and compliance requirements.

### What admins can do

* **Review flagged messages for verification**, including message content when necessary to determine whether an email is malicious, spam, or legitimate.  
* Release or permanently block messages based on that review.  
* Create and adjust detection rules (for example, flagging external senders impersonating executives).  
* Content access is limited to IT and the CISO, used **only for security analysis**—never for employee monitoring or general reading of inboxes.

### Audit & logging

* Sublime records all administrative and remediation actions—such as message releases, rule changes, and account access—in its audit log.  
* Viewing of message content occurs within Sublime’s secure console and is limited to IT and the CISO; while not every passive view is individually logged, all user sessions and configuration actions are recorded.  
* Logs are periodically reviewed to confirm that access and investigations align with legitimate security purposes.  
* Access is restricted via SSO and MFA.

## G. Other Tools 

* **Password Managers (1Password / Bitwarden):** For work credentials. Admins cannot see your personal vaults.  
* **YubiKeys & MFA:** Issued for secure login. We track which keys are issued, but cannot use them to access personal accounts.

# 2\. Who Can Take Privacy-Sensitive Actions

* **Authorized users at this time:**  
  * **Andy Laken** (Head of IT & Security)  
  * **Austin Quam** (Fractional CISO, Zero Sum Defense)  
* **Principal oversight authority:**  
  * **Andrew Hoppin (CIO)** and other principals may change or revoke access to all tools at any time, protecting the company if IT or CISO roles change.  
* **Safeguards:**  
  * All admin accounts are protected with hardware MFA/passkeys.  
  * Credentials are stored only in hardened password managers.  
  * Recovery processes are documented and controlled.  
  * All other staff roles are restricted to least privilege, without ability to impersonate, run RTR, or view personal data.

# 3\. Why These Measures Are Necessary

We connect directly to **crypto custodians, exchanges, hot wallets, and company banking systems**, among other critical tools. These are prime targets for attackers. Malware in particular targets all of these systems and can act in a matter of seconds following exposure, including [software packages that are commonly used](https://socket.dev/blog/2025-blockchain-and-cryptocurrency-threat-report).

* A single compromised laptop could enable **immediate theft of assets or funds.**  
* Attackers deliberately target hedge funds and crypto managers with malware and social engineering.  
* Regulators (SEC, banking partners) expect robust controls.

The privacy trade-offs of these tools are real, but they are outweighed by the need to protect assets, staff, and reputation. With strict access limits, audit trails, and principal oversight, the balance is both **necessary and fair.**

# 4\. Logging and Auditing

* **Falcon:** All RTR sessions, containment actions, and file operations logged and immutable.  
* **Cloudflare:** All policy changes and log queries recorded.  
* **Google MDM:** Device wipes and enforcement actions logged.  
* **Google Workspace:** Admin impersonations and account actions logged.  
* **Sublime email:** Administrative and message-release actions logged; all user sessions recorded  
* **Review:** Any invasive action requires reporting and after-action review; periodic audits conducted jointly by IT and CISO with principal oversight.

# 5\. Consent & Options

* By using your personal device for work, you consent to the installation and operation of these tools.  
* By using company-provided communication and document systems (e.g. Drive, Slack), you consent to the measures above necessary to secure such services.  
* Privacy-sensitive actions (RTR, impersonation, log review) will only be taken for confirmed incidents or compliance — never for casual monitoring.  
* If you are uncomfortable, let us know. For sensitive roles (e.g., trading ops), we may issue a **company-owned device** with monitoring restricted to work data only.  
* Each user must sign this document, and each BYOD device must be registered under a signed consent.

# 6\. Our Commitment

* This document will be reviewed annually or upon major tool or policy change.  
* We **value your privacy** and will continue to balance strong protections with respect for personal data.  
* We **welcome questions and concerns** — please ask if anything is unclear.  
* We will remain transparent about what these tools do, how they’re used, and how your data is protected.