# Cowork Platform Reference — Gaps, Workarounds, and Competitive Intel

*Reference material for session prep and client conversations. Separates what Cowork can do today from where it's headed.*

---

## Cowork Trajectory: Next Six Months (as of March 2026)

1. **Computer use becomes the core differentiator.** Claude Sonnet 4.6 hit 72.5% on OSWorld benchmarks, up from under 15% in late 2024. With the Vercept team inside Anthropic, Cowork's computer use will likely cross 90%+ by Q3. Qualitative shift from "hand it a folder" to "it navigates your actual apps."

2. **Windows + cross-device sync.** Already committed on Anthropic's roadmap. Gates enterprise addressable market. Expected GA by Q2-Q3. (Windows support launched Feb 10, 2026 with full feature parity.)

3. **Plugin marketplace matures into a platform.** Private enterprise marketplaces now available. Community-accessible ecosystem likely follows, mirroring how Claude Code built developer gravity.

4. **Scheduled and autonomous tasks get more capable.** Current implementation is primitive. Trajectory is toward background agents that monitor, trigger on events, and coordinate across tools without user initiation.

5. **Vertical deepening in high-stakes domains.** Prebuilt plugins for PE, HR, design, operations. A Cowork-native security audit workflow is a natural extension that lands in the fractional CISO wheelhouse.

6. **Trust and audit layer as enterprise table stakes.** Expect more granular permissioning, action logging, and approval workflows. The change management infrastructure regulated enterprises need to deploy broadly.

---

## Persistence & Backup Strategies

Two distinct client pain points. Keep separate in sales conversations.

### 1. Backup & Disaster Resilience (device lost, stolen, destroyed)

**Layer 1 — Sync (continuous, cross-device access):**
- **Mac:** iCloud Drive. Point Cowork folder here, zero friction after setup.
- **Windows:** OneDrive. Built into Windows 10/11 and M365. Zero additional cost.
- **Google Workspace clients:** Google Drive. Works identically on Mac and Windows.

**Layer 2 — True backup with versioning:**
- **Backblaze Personal Backup** at ~$9/month. 365-day version history, ransomware protection, works identically on Mac and Windows. Industry standard recommendation. Set-and-forget after initial setup.

**Layer 3 — Git (for willing clients):**
- Andy's current approach. Superior audit trail and version history.
- **launchd auto-commit script** (Mac) makes it set-and-forget: every 15 minutes, `git add -A && git commit -m "auto $(date)" && git push`.
- GitHub is more durable offsite backup than iCloud given account recovery pain.
- Sourcetree or GitHub Desktop for visual history if they ever want it.

**Critical distinction to communicate to clients: sync is not backup.** Sync services propagate deletions and ransomware corruption instantly. A file deleted or encrypted by malware syncs that destruction to the cloud before anyone notices. Backup with versioning lets you roll back.

**Recommendation by client profile:**
- Non-technical executive: Layer 1 + Layer 2 (sync + Backblaze). ~$9/month, zero friction.
- Technical founder / developer: Layer 3 (git). They already have GitHub, audit trail matters.

### 2. Mobile Access & Control (workflow continuity away from desk)

**Current state:**
- **Cowork:** No mobile story. Explicit product gap vs. OpenClaw.
- **Claude Code Remote Control:** Phone as window into local session. Outbound HTTPS only, files never leave machine. One connection per session. 10-minute network outage = timeout. Does NOT solve device loss — Mac must be on and connected.
- **OpenClaw structural advantage:** Routes through WhatsApp/Telegram. Works everywhere a phone works. Zero install friction.

**Likely Anthropic answer:** Vercept/Vy cloud-hosted Mac model. Solves both persistence and mobile simultaneously. Not yet deployed.

**Honest framing for clients:** Cowork is the more private, more auditable, more capable option that currently requires a desktop and some setup discipline. That's a feature for security-conscious executives, not a bug. Design their setup accordingly.

---

## Vercept/Vy Acquisition (Anthropic, Feb 25, 2026)

**What it is:** Vision-based UI grounding. Identifying and interacting with UI elements by seeing rendered pixels, not reading DOM. Solves the "app has no MCP, no API" problem.

**What it is NOT:** A general-purpose cloud VM for Cowork (that's a separate, presumably simpler infrastructure question).

**Key facts:**
- 9-person team, $50M raised, shut down March 25
- 92% accuracy on ScreenSpot v1 vs. OpenAI's 18.3%
- Ross Girshick (R-CNN author) on the team — serious computer vision pedigree
- Vy operated a cloud-hosted Mac agent: you gave it a task, it navigated a remote machine
- Learned-from-demonstration capability (fine-tuned by watching how users performed tasks)

**Why it matters for Cowork:**
- Cowork's current browser interaction (Claude in Chrome) is DOM-based and fragile
- Vercept team's job is closing that gap with vision-first perception
- Claude Code + Chrome is more reliable today because Code orchestrates and uses browser as output device; Cowork asks the Chrome extension to be both orchestrator and perception layer simultaneously

**Security angle (from Prism News):** Anthropic has not released a technical white paper or security specification for the acquisition. Agents that access local files and applications change the threat model. Clients need that gap filled now, before Anthropic publishes anything formal.

**For client conversations:** "You're thinking about this the right way. The distinction is between Cowork (sandboxed VM, specific connector permissions) and tools that get full system access. Different architectures, different risk profiles."

---

## Diagram Tools

- **External client-facing architecture diagrams:** Napkin.ai (generates clean professional diagrams from text descriptions)
- **Internal working diagrams:** Mermaid (Claude generates natively, renders in Notion and GitHub)

---

## Podcast Resources

- **Lenny's Newsletter/Podcast** — Boris Cherny (creator, Claude Code/Cowork) interview. Primary source, highest signal.
- **MacSparky** — Practitioner deep dive with Labs members. Real workflows. Paywalled.
- **AI Agents podcast (Jotform)** — Live demos, MCP connector walkthroughs.

---

*Created: March 8, 2026*
