# Three Outlines: Digital Asset Security Article

---

## Outline A — "The Smart Person Problem"

**Central argument:** Individual security competence and firm-level security posture are different things. The gap between them is structural, not a knowledge problem, and it can't be closed by being more careful.

**Opening:** Start inside the experience of someone who has done a lot right — knows about SIM swaps, runs a VPN, uses hardware keys for wallet access, thinks about this stuff more than most people in his peer group. He got SIM-swapped anyway, because Verizon's account security protocols are inadequate regardless of how sophisticated the account holder is. His knowledge of the threat didn't prevent it. That's the first crack in the assumption the piece is here to examine.

**Section 1 — What individual vigilance actually covers**
Walk through what good personal OPSEC looks like and what it genuinely protects against. Give the reader credit. The point isn't that they've been careless — it's that there's a category of risk that individual attention can't address, no matter how good.

**Section 2 — Where the structural gaps live**
Introduce defense in depth as a concept: the idea that no single layer holds, and that a real posture is the accumulation of independent layers such that any one failure doesn't cascade. Then map the specific layers most BYOD crypto firms are missing: endpoint visibility, network-level filtering, account hygiene across the full credential surface, communication channel protocols. Frame each as a question the reader should be able to answer about their own firm — and probably can't.

**Section 3 — Why the gap exists and what closes it**
The gap isn't tools, it's ownership. Each of the missing layers requires someone to implement it, maintain it, and notice when it drifts. In a lean fund with no security owner, that doesn't happen. Introduce the ownership concept without making it feel like a sales pitch — frame it as the organizational question, not the product.

**Close:** The reader who did everything right is still exposed in ways that require infrastructure-level fixes, not more personal vigilance. The question is whether their firm has those layers in place.

---

## Outline B — "Defense in Depth, Explained from the Ground Up"

**Central argument:** Most digital asset firms understand individual threats. What they don't have is a mental model for how defenses layer — and without that model, they can't see the gaps they're exposed through.

**Opening:** A brief, concrete description of an attack that succeeded against someone who was trying to be careful — the Telegram-to-Zoom-to-terminal sequence — told as a sequence of moments, each of which felt normal. No drama. Just a series of plausible interactions that ended with persistent malware on a device. The point of the opening isn't the attack; it's that every layer the target had in place was bypassed, not defeated.

**Section 1 — The concept of defense in depth**
Explain it simply: independent layers, each of which catches what the previous one missed, such that an attacker has to defeat all of them rather than one. Draw the analogy to something familiar — physical security, a vault with guards and cameras and locks. Then introduce the basic layers as questions:
- What's on your devices and what can you see happening on them?
- What do your network connections filter before they reach you?
- Who holds credentials to what, and does that list still reflect reality?
- What happens to access when someone leaves?
- How do you verify identity in the channels where impersonation is active?

**Section 2 — What each layer actually does**
Walk through endpoint protection, network filtering, credential hygiene, and communication protocols as plain concepts — not product names — explaining what each one covers and what it leaves uncovered on its own. The point is to build the reader's mental model, not to prescribe a stack.

**Section 3 — Where most firms actually are**
Describe the typical BYOD crypto fund honestly: some things done, nothing connected, nobody with the whole picture. Use the "security decisions vs. security posture" framing from the brainstorm. The decisions were reasonable. The posture doesn't exist yet.

**Close:** Knowing about threats is a start. Having independent layers that don't depend on you making the right call in every moment is a different thing.

---

## Outline C — "Nobody's Job"

**Central argument:** The security failures that actually cost crypto funds aren't exotic. They're the predictable result of a structure where security is everyone's vague responsibility and therefore nobody's actual job.

**Opening:** Two years of working with digital asset funds, watching the threat environment change. The clients who got hit weren't doing nothing. They had done things. The pattern in the ones that stayed covered wasn't a superior set of tools — it was that someone was accountable for the whole picture and was maintaining it over time.

**Section 1 — What "doing things" actually looks like**
Describe the typical security posture of a thoughtful fund: MFA on important accounts, a password manager, hardware keys for custody, some awareness of phishing. These decisions were all right at the time they were made. The problem is there's no connective tissue between them, no one reviewing whether they still hold, and no process for noticing what's missing.

**Section 2 — The specific gaps that accumulate**
Account access that outlives the people it was granted to. Devices that have been connecting to trading infrastructure for years with no visibility into what's running on them. Communication channels with no firm-level protocols for identity verification — handled instead by each person's individual judgment in each individual moment. No single gap here is fatal. Together, in a fund that's been moving fast, they add up to a surface area that's much larger than anyone realizes.

**Section 3 — Defense in depth as the organizing principle**
Introduce the concept as the answer to the structural problem: independent layers, each maintained by someone accountable, such that no single failure opens the whole firm. Walk through the layers concisely — endpoint, network, credential surface, communication protocols — as a framework for thinking about coverage, not as a product list.

**Close:** The question most funds haven't asked isn't "are we doing security?" They've done things. The question is whether those things are connected, current, and owned.

---
