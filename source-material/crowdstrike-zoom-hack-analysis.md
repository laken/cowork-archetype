# SOURCE: Crowdstrike deterrence for Zoom hack
# Fetched from Google Drive (laken@hylafunds.com)

# Crowdstrike deterrence for Zoom hack

*Andy: "Gemini \- would Crowdstrike Falcon running on Elijah's laptop before the attack have made a difference?"*

*Gemini:*

**Yes.**

Based on the evidence in your screenshots and CrowdStrike's capabilities, if the Falcon sensor had been installed and active **before** the attack occurred, it is highly probable it would have blocked the infection entirely at the initial "delivery" stage.

Here is the breakdown of exactly how Falcon would have stopped this specific kill chain:

### 1\. It Would Have Blocked the Terminal Command (The "Delivery")

The attack started with a `curl | bash` or similar terminal command to download and execute the script.

* **Falcon Capability:** **Script Control & Suspicious Process Prevention**.
* **How it works:** Falcon monitors terminal commands on macOS in real-time. It detects when a shell command attempts to download a file and immediately pipe it to execution (a technique known as "download and execute").
* **Evidence:** CrowdStrike has documented success in blocking similar "one-line installation commands" used by other macOS malware (like SHAMOS/AMOS) that try to bypass Gatekeeper. The sensor would have killed the `curl` or `sh` process before it could download the payload.

### 2\. It Would Have Blocked the File Write (The "Installation")

The script successfully wrote a binary file to `/Library/Fonts/com.apple.logd`.

* **Falcon Capability:** **File Integrity Monitoring & Custom IOAs**.
* **How it works:** The directory /Library/Fonts/ is a system folder reserved for fonts, not executable binaries. A process (like curl or bash) attempting to write an executable file (.logd) to this specific location is a high-confidence "Indicator of Attack" (IOA).
* **Evidence:** Falcon's behavioral logic flags executables running from or being written to unusual paths like /Library/Fonts/ as masquerading attempts. It would have blocked the *write* action or the subsequent *execute* action.

### 3\. It Would Have Blocked the C2 Immediately (The "Action")

Your screenshot shows the malware was running for **6 hours** before it was detected.

* **Your Screenshot Data:**
  * **Process Start Time:** 08:21:30 (When the infection happened)
  * **Detection Time:** 14:22:13 (When Falcon saw it)
* **The Difference:** Because Falcon was likely installed *after* the infection (during your remediation call), it only saw the malware once it scanned running memory. If it were running *before*, it would have seen the **Network Connect** attempt immediately at 08:21 and blocked the process for "Command and Control" behavior.

### Summary:

Falcon is designed to break the "Kill Chain." In your case, you caught it at the very end (Step 7: Command and Control) because the sensor wasn't there for Steps 1-6. Had it been there, it would have broken the chain at Step 1 (Delivery).
