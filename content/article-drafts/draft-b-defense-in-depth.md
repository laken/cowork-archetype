# Draft B: Five Questions Your Fund Should Be Able to Answer

---

The attack didn't start with anything that felt like an attack. A message from a contact on Telegram — someone the target had worked with, whose account they'd been in conversation with for months. A quick Zoom call to sort something out. The person on screen looked right and sounded right. Somewhere in the conversation, there was a technical issue, and a request to run a command in the terminal to fix it. The command took about four seconds to execute.

Eight hours later, someone noticed the device was behaving strangely. By then the malware had been running for the better part of a working day, connected to a command-and-control server, with access to saved credentials, exchange sessions, and everything else on the machine.

The target had done things to protect himself. That's what makes this particular pattern worth understanding. The attack didn't succeed because someone was careless. It succeeded because it was designed to operate in the gap between what individual vigilance covers and what infrastructure-level protection covers. Those are not the same gap, and knowing about one doesn't close the other.

## The idea behind defense in depth

Security practitioners use the phrase "defense in depth" to describe something simple: instead of relying on any single protection to hold, you build independent layers, each of which catches what the others miss. The value of the approach is that it removes single points of failure. An attacker who gets past one layer still has to contend with the next one, and the next, rather than having full access once the first thing fails.

Physical security works this way intuitively. A building with a good lock on the front door is less secure than one with a good lock, cameras, a keycard system, and a guard — not because the lock is inadequate, but because the lock is one layer. If someone defeats it, everything else depends on nothing.

Digital asset funds tend to have one layer, or pieces of a few layers, implemented inconsistently and owned by no one in particular. Understanding where the coverage actually is — and where it stops — is the starting point for building something real. There are five questions that map the territory.

**Can you tell when something malicious lands on a device?**

When a device gets compromised — through a download, a terminal command, an infected link — the window between initial infection and the malware establishing persistent access is often very short. Endpoint detection and response software monitors device behavior in real time, looking for processes that are doing things processes shouldn't do: writing executables to system directories, making unusual network connections, trying to access credential stores. When it sees those patterns, it kills the process. Most BYOD fund environments have no endpoint visibility at all, which means the first indication of a compromise is whatever the malware does after it's had time to settle in.

**Does your network filter known threats before they reach you?**

Every internet connection starts with a DNS lookup — your device asking a server where to send traffic. If that lookup goes through a security gateway, known malicious and impersonation domains can be blocked before a connection is ever made. This stops a significant portion of social engineering payloads at the network layer, before they reach the user. A personal VPN does not reliably provide this. Consumer VPNs handle DNS inconsistently, and the behavior varies by operating system and network in ways the user can't see. The protection may or may not be there on any given connection.

**Do you know who holds credentials to what — and is that list current?**

In a fund that has been operating for a few years, access tends to accumulate faster than it gets cleaned up. Someone leaves, and their API keys to three exchanges stay active because no one went through the process of revoking them. A contractor wraps up a project, and the admin access they needed for it stays on. Shared passwords exist for accounts that multiple people use and nobody specifically owns. Getting a current, accurate picture of the full credential surface — every exchange, custodian, cloud account, and internal system, mapped to actual current people — is the kind of unglamorous work that removes the low-effort entry points attackers look for first. In most funds I work with, it hasn't been done since the early days.

**When someone leaves, does their access actually end?**

This is a subset of the previous question, but it deserves to stand alone because the failure mode is so consistent. Offboarding in a lean fund is usually focused on the obvious things — removing email, recovering equipment. Access to trading infrastructure, custody platforms, and API integrations is harder to audit and easier to miss. A former employee with live exchange credentials is a quiet vulnerability that could sit unnoticed for a long time.

**How does your team verify identity in the channels where impersonation is active?**

Telegram is the primary communication channel for much of the crypto industry and its primary attack surface. When an account gets compromised, an attacker gains access to months of organizational context — who approves what, how people write to each other, what a plausible request looks like — and can use that context to manufacture convincing interactions. Combined with the deepfake video technology that can reconstruct a face and voice from publicly available material, the impersonation attacks coming through these channels are harder to detect in the moment than most people expect. The question for any fund is whether there's an explicit, firm-level protocol for verifying identity before taking sensitive action — or whether each person is making that judgment individually, in each moment, under conditions designed to make the judgment wrong.

## What the answers reveal

Most funds that go through these questions honestly find that the answers cluster in similar ways: some endpoint protection missing entirely, network filtering either absent or less comprehensive than assumed, a credential surface that hasn't been audited recently, offboarding that handles some things but not others, and communication protocols that live in individual judgment rather than firm policy.

None of these gaps are exotic vulnerabilities. They're the predictable result of building security by responding to individual moments of concern, over time, without anyone maintaining the whole picture. Each decision made along the way was reasonable. The posture that results from those decisions, looked at as a whole, tends to have more gaps than anyone realized.

The value of defense in depth as a framework is that it gives you a way to look at the whole picture — to see which layers are genuinely in place, which ones are partially in place, and which ones are absent. Most firms find that the work required to close the gaps is less than they expected. What it requires is someone accountable for doing it and for keeping it current as the threat evolves.
