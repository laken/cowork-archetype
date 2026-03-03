# Draft C: Nobody's Job

---

Two years of building security programs for digital asset funds has taught me to look past the question of what a firm has done and ask a different one: who owns it?

The funds I've worked with that stayed covered when the industry's attack rate spiked in 2025 weren't using better tools than the ones that got hit. They had someone accountable for the whole picture — reviewing access, maintaining the program, noticing when something drifted. The ones that got hurt were mostly doing things. They'd made reasonable security decisions over time. What they didn't have was an owner, and over time the gaps between their decisions had quietly accumulated into something an attacker could use.

State-sponsored groups, organized criminal operations, and social engineering rings stole over $2 billion from the digital asset space in 2025. That's the disclosed figure. The actual losses are higher, because a meaningful number of incidents in this industry never become public. The firms on the wrong side of those numbers weren't, in most cases, doing nothing. They were doing something — just not enough of the right things, maintained over time, with someone responsible.

## What "doing things" looks like from the inside

A thoughtful digital asset fund will typically have made a set of security decisions that feel, individually, quite reasonable. MFA on the important accounts. A password manager for shared credentials. Hardware keys for custody access. Some awareness of phishing and social engineering, passed along to the team informally. Perhaps a VPN for the people who travel.

Each of these was a good decision at the time it was made. The problem is that they accumulate without connecting. Nobody reviews whether they still hold six months later. Nobody notices that a former employee's API access to two exchanges is still active. Nobody asks whether the VPN the partners are using actually protects DNS traffic on the networks they're connecting from — it often doesn't, in ways that are invisible to the user. Nobody went back after the contractor's project ended to verify that their admin access was revoked.

The result is a posture with a credential surface nobody has fully mapped, devices connecting to trading infrastructure with no visibility into what's running on them, and communication channels with no firm-level protocols for identity verification — each person managing that judgment individually, in each moment, in an environment where the impersonation attacks are good enough that individual judgment is an unreliable defense.

## How the gaps get exploited

The attacks landing on crypto funds right now are designed to operate precisely in the space between what individual attention covers and what infrastructure-level protection covers.

A compromised Telegram account — taken through a SIM swap, a session hijack, or a social engineering play on account recovery — gives an attacker access to months of organizational context. They learn who approves transfers, how people write to each other, what a plausible request looks like. From there, the escalation to a fake Zoom call is a short step. The face on screen is reconstructed from publicly available photos; the voice is cloned from podcast appearances or recorded calls. The conversation is unhurried. When the "colleague" asks the target to run a command in the terminal to fix a technical issue, there's no reason not to.

The command is the delivery mechanism. It installs malware that establishes persistent access to the device — exchange sessions, API keys, wallet software, saved credentials. Endpoint detection and response software running on the device before the attack would have killed the process within seconds of the terminal command executing, because the behavioral signature of that kind of installation is recognizable. Network-level filtering routing DNS through a security gateway would have blocked the command-and-control domain the malware tried to phone home to. Without either layer, the malware had eight hours to operate before anyone noticed something was wrong.

## Defense in depth as the organizing principle

The security concept that addresses this is defense in depth: independent layers of protection, each maintained by someone accountable, such that any single failure doesn't cascade into a complete compromise. The layers a digital asset fund needs to have in place map directly to the gaps described above.

Endpoint visibility — software on every device that touches firm infrastructure, watching for malicious process behavior in real time — is the layer that catches what gets through everything else. Network-level filtering at the DNS layer blocks known threat domains before a connection is made. A current, accurate audit of the full credential surface removes the stale access that makes low-effort attacks possible. Firm-level protocols for communication channel security replace individual judgment with enforced standards at the moments when individual judgment is most likely to fail.

None of these are expensive relative to what they protect. None of them require exotic expertise to implement. What they require is someone whose job it is to implement them correctly, maintain them over time, and evolve the program as the threat environment changes. For most firms at this stage, that's ten to twenty hours a month from a senior technologist — not a full-time hire, but a real commitment to someone with real accountability.

The question that determines whether a fund's security posture is real or notional isn't what decisions they've made. It's who owns the picture those decisions are supposed to add up to.
