# AI Connectivity Governance Framework

*Working draft. This is standalone IP and a key differentiator for the practice. Developed from the Hyla/Andrew Hoppin case study and generalizable to any firm adopting agentic AI tools.*

---

## The Core Problem

Agentic AI tools (Cowork, Claude Code, OpenClaw, and successors) create data flows from personal and organizational data into AI service providers faster than any governance process. These connections happen at individual initiative, often without the connecting person understanding the data handling implications. Standard IT security wasn't built for this class of decision.

The result: executives connect work email, calendar, CRM, and documents to AI tools because the productivity gains are obvious and the setup takes minutes. Nobody asks whether the org has authorized that data flow, whether a DPA exists, or what happens to the data once it's in the AI provider's infrastructure.

---

## Six Decision Categories

### 1. Data Source Classification

What kind of data lives in each connector? Classification determines everything downstream.

- **Personal productivity** — personal calendar, personal notes, individual task lists
- **Internal business communications** — work email, Slack, team messaging
- **Sensitive business data** — deal flow, investor relations, fund documents, board materials, client information
- **Regulated data** — anything with contractual or legal data handling requirements (LP agreements, SEC-related, HIPAA, etc.)

Andrew's personal task list connecting to Claude is categorically different from his fund email connecting to Claude, even though both feel like "productivity tools."

### 2. Service Provider Assessment

For each AI service receiving data:

- Does the service use customer data for model training? Under what conditions?
- Is a Data Processing Agreement (DPA) available?
- What's the data retention policy?
- Is Zero Data Retention (ZDR) available, and at what tier?
- Is the service SOC 2 certified?

Anthropic has clear answers to most of these. Many agentic tools don't. The consumer vs. commercial terms distinction (see `cowork-security-privacy-research.md`) is critical here: Team plan is under Consumer Terms, same as Pro.

### 3. Authorization Level

Who has authority to approve each combination of data source x service provider?

- **Individual discretion** — low sensitivity data, personal accounts, no organizational data
- **IT awareness required** — organizational accounts, even if low sensitivity
- **IT approval required** — any connector touching business communications or sensitive data
- **Formal review required** — sensitive business data with a DPA in place
- **Legal + compliance required** — regulated data, regardless of DPA status

### 4. Inventory and Audit

- **Nudge Security** for retroactive discovery (email-scan-based, surfaces historical OAuth grants)
- **Google Workspace OAuth audit** via Admin console (Security > API Controls) for Google-ecosystem visibility
- **Quarterly review cadence** — triggered review when major new agentic tools launch (happening monthly right now)
- **Offboarding process** — connector revocation when someone leaves the org

### 5. Incident and Exception Handling

- What happens when a connection is discovered that wasn't approved?
- Retroactive approval vs. immediate revocation — decision framework needed
- The "Andrew situation" protocol: how to have that conversation without it feeling punitive
- Who gets notified, what gets documented

### 6. Communication and Policy

- How you communicate decisions to non-technical executives without making it feel like security theater
- Goal is enabling AI tool use with appropriate controls, not blocking it
- Policy documents that executives will actually read and follow
- The framing matters: "here's how to use these tools safely" vs. "here's what you can't do"

---

## The Decision Matrix (Rubric)

| Data Sensitivity | Service Has DPA | Authorization Required |
|---|---|---|
| Low / personal | Either | Individual discretion |
| Low / organizational | Yes | IT awareness |
| Low / organizational | No | IT approval |
| Medium / business | Yes | IT approval |
| Medium / business | No | Formal review |
| High / sensitive | Yes | Formal review + legal |
| High / sensitive | No | Blocked pending review |
| Regulated | Any | Legal + compliance required |

---

## Engagement Structure (How This Becomes a Deliverable)

**Discovery phase** — Nudge audit, Google OAuth inventory, interview with key users about what they're using. Deliverable: current state map of AI connectivity. This is where you find the Andrews.

**Classification phase** — Apply the data source classification to the org's actual data landscape. Deliverable: data source inventory with sensitivity ratings.

**Policy phase** — Draft the authorization matrix calibrated to the org's risk tolerance, legal obligations, and culture. Deliverable: written AI connectivity policy.

**Implementation phase** — Configure the controls (Google Workspace OAuth settings, Nudge alerting rules, any MDM policies). Deliverable: technical controls in place.

**Ongoing** — Quarterly review, triggered reviews when major new agentic tools launch, policy updates.

---

## What Makes This Different

Standard security frameworks treat AI tools as shadow IT to be blocked. This framework treats them as productivity infrastructure to be governed. The goal is enabling Andrew to use Cowork with his email, with appropriate controls in place, not preventing him from using it. That's a fundamentally different posture that executives will actually engage with rather than route around.

---

## Google Workspace OAuth Controls: Available Levers

Three layers of granularity available in Google Admin console (Security > API Controls):

1. **Blanket policy** — restrict all third-party apps from accessing Gmail/Drive/Docs/Chat at the service level without enumerating specific apps.
2. **App-specific blocking** — block individual OAuth2 apps by name or client ID; can be done preemptively before any user connects.
3. **Allowlist model** — restrict to approved apps only; new installs of unverified apps blocked unless explicitly trusted. Can be applied per organizational unit.

If access is changed to Restricted, previously installed apps stop working and tokens are revoked immediately.

Anthropic's Gmail MCP connector (launched Feb 24, 2026) may not yet be in Google's verified app registry, making it potentially blockable via blanket "unverified third-party apps" policy.

---

## Live Case Study: Hyla Funds

Andrew Hoppin (CIO) connected work Gmail to Cowork MCP as personal productivity. No governance conversation, no org authorization. Fund communications and investor relations potentially flowing through Anthropic servers without formal DPA review.

Andy administers the Google Workspace and has full admin controls available. Nudge Security is deployed but underutilized. Cloudflare CASB (once deployed) closes this gap at the infrastructure layer and maps directly onto Cloudflare Zero Trust already in deployment at Hyla.

**Action items:**
- [ ] Run Nudge audit on Hyla before next conversation with Andrew
- [ ] Evaluate Cloudflare CASB scope for current Zero Trust deployment
- [ ] Review current Google Workspace OAuth policy (default unrestricted?)
- [ ] Determine if conversation with Andrew needs to happen before or after audit

---

## SaaS Discovery Tool Recommendations

| Tool | Model | Best For | Pricing |
|---|---|---|---|
| **Nudge Security** | Email-scan retroactive discovery | One-time forensic audit as engagement deliverable | $750 flat (<150 users); free trial available; Andy has prior relationship |
| **Push Security** | Browser extension, forward-looking | Ongoing monitoring post-engagement | $5/user/month; first 10 free |
| **Cloudflare CASB** | Google Workspace/M365 integration | Orgs already on Cloudflare Zero Trust | Part of Zero Trust platform |

**Recommended engagement model:** Nudge free trial for initial forensic discovery (surfaces historical connections), then Push Security for ongoing monitoring at $5/user/month. For orgs already on Cloudflare (like Hyla), CASB replaces Push at the infrastructure layer.

---

*Created: March 8, 2026*
