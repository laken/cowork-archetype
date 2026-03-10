# Draft A: The Smart Person Problem

---

He knows what a SIM swap is. He ran a VPN. He used hardware keys for wallet access, thought carefully about which devices touched which systems, and had read enough about the threat landscape to be in the top few percent of security awareness among his peers. He got SIM-swapped anyway.

Verizon's account security protocols are inadequate in ways that have nothing to do with how sophisticated the account holder is. The attacker called in, social-engineered a support rep, and had the number transferred before anyone thought to notify the actual customer. All the knowledge in the world about how SIM swapping works doesn't change the fact that the carrier is the weak point, and the carrier isn't under your control.

I'm not telling this story to be discouraging. I'm telling it because it illustrates something that took me a while to articulate clearly from two years of building security programs for digital asset funds: there's a category of risk that individual vigilance can't address, no matter how good that vigilance is. Most of the funds I work with have people who are genuinely trying. The gap isn't awareness. It's structure.

## What good personal OPSEC actually covers

Running a VPN, using hardware keys, enabling MFA, being skeptical of unexpected requests — these are all genuinely useful. They raise the cost of certain attacks and close some real vulnerabilities. If everyone on your team did all of them consistently, you'd be better off than most.

What they have in common is that they depend on an individual making the right call, consistently, under conditions that are sometimes designed specifically to prevent that. A VPN doesn't protect a device that's already been compromised. Hardware keys don't help if someone social-engineers their way past account recovery. MFA doesn't stop an attacker who's already inside a Telegram account reading your messages and learning how you communicate. Individual vigilance is a layer. It's one layer.

## Where the structural gaps live

The concept security practitioners use for this is defense in depth: independent layers of protection, each of which catches what the previous one missed, such that an attacker has to defeat all of them rather than just find the one moment you weren't paying attention. The practical question for any firm is which layers they actually have in place.

Most digital asset funds I work with have some version of the personal OPSEC layer. What they're missing tends to cluster in a few specific places.

### Endpoint visibility

When a device is compromised — through a malicious download, a terminal command run during a convincing Zoom call, an infected link that bypassed a tired moment of judgment — you need to know about it before the malware has time to establish itself and exfiltrate. Endpoint detection and response software monitors device behavior in real time and kills malicious processes before they spread. Without it, the first indication of a compromise is often the damage. Most BYOD fund environments have no endpoint visibility at all.

### Network-level filtering

Every internet connection starts with a DNS lookup — your device asking where to send traffic. Routing that through a security gateway lets you block known malicious and impersonation domains before a connection is ever made, stopping a significant share of social engineering payloads before they reach the user. A personal VPN does not reliably do this. Most consumer VPNs handle DNS inconsistently, and the behavior varies by operating system and network in ways that are invisible to the user. The VPN creates the impression of protection at the network layer that often isn't fully there.

### Credential surface hygiene

In a firm that has been running for a few years, access tends to accumulate in ways nobody tracks. People who have left still have API keys to exchanges. Contractors who wrapped up engagements still hold admin rights. Shared accounts exist that multiple people know the password to and nobody owns. Getting a current, accurate picture of who has credentials to what — and then closing the gaps — is unglamorous work, but it's the work that removes the low-effort entry points attackers look for first.

### Communication channel protocols

Telegram is the primary attack surface for the crypto industry right now, partly because it's where so much real business happens and partly because account security on the platform is routinely inadequate. A SIM-swap attack on a Telegram account gives an attacker access to months of context about your organization — who approves what, how people write to each other, what a plausible request looks like. From there, the impersonation attacks that follow are hard to detect in the moment. Strong second-factor authentication on every account, hardened specifically against SIM-swap, is a firm-level decision, not an individual one. So is having an explicit protocol for verifying identity before any sensitive action, in a threat environment where real-time deepfake video calls are an active vector.

## Why the gap exists

None of these layers are exotic, and none of them are particularly expensive. The reason most funds don't have them in place isn't that they haven't heard of them. It's that implementing and maintaining them requires someone to own the whole picture, and in a lean fund, that's nobody's job.

Security decisions get made in response to moments of concern. Something happens in the industry, or someone reads about a new attack, and a decision gets made: enable MFA, get a password manager, update the wallet policy. Each decision was reasonable. But there's no one reviewing whether those decisions still hold six months later, no one noticing what's missing from the overall posture, no one whose job it is to evolve the program as the threat does.

For most firms at this stage, closing that gap doesn't require a full-time hire. It requires ten to twenty hours a month from someone senior enough to see the whole picture and accountable enough to keep it current. That's what turns a collection of security decisions into an actual posture.

The person who knew about SIM swapping and still got SIM-swapped wasn't doing the wrong things. He just didn't have the structural layer that the individual layer can't replace.
