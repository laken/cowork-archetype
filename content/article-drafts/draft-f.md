---
title: "Digital Asset Firms Are the Highest-Value Targets on the Internet. Most Act Like They Aren't."
date: "2026-03-01"
description: "State-sponsored attackers stole over $2 billion from the digital asset space in 2025 alone. Most firms have individual security decisions, not a program. Here's what closing the gap actually takes."
slug: "2026-03-why-digital-asset-funds-are-cybersecurity-targets"
---

You've been around the digital assets space long enough to be savvy. You've had friends get hit bad because they were sloppy with a keyphrase. You got SIM-swapped a few years ago. Nothing awful happened, but you learned the lesson: you've changed your carrier settings and feel confident it can't happen again. You've got your YubiKeys on your important wallets and credentials, and you've set up multi-sig where it counts. You run a VPN 24/7, have MFA on everything, and use your password manager like a wizard. And you're so good at spotting phishing emails; you're the unofficial firm expert who trains everyone else. 

So how did you just get SIM-swapped again?
And how did you miss that the email you just replied to, seemingly from a GP, was actually a phish?
And what about everyone else in your firm whose OpSec isn't on par with yours?

Augmented by AI and state level actors, the attacks and social engineering are much harder to detect. Now, it's not a matter of if, but when you'll accidentally click on that link.

Two years of building security programs for digital asset funds has made that gap the thing I'm most focused on: the space between what an individual can do and what a firm actually needs.

## The threat environment has changed from a year ago

The social engineering attempts that used to have tells — awkward language, suspicious urgency, something slightly off — now don't. Messages are constructed from scraped LinkedIn data, public filings, and blockchain analytics, then refined by AI to match the tone and communication style of people you actually work with. Business email compromise attacks don't announce themselves. An attacker sits quietly in a compromised inbox for weeks, reads the thread history, maps the org chart, learns who approves what and how they write when they do it. When they move, the message fits your world well enough that catching it requires exactly the kind of sustained, skeptical attention that's hardest to maintain in the middle of a normal workday.

The impersonation attacks have gone further. Deepfake video calls — a face reconstructed in real time from publicly available photos, a voice cloned from podcast appearances or recorded calls — are being used to impersonate colleagues, counterparties, and investors. Fund managers have described calls that felt completely normal until something small didn't add up, and by then the request had already been made.

You will eventually be fooled. The attacks are now good enough that this is a planning assumption, not a failure of vigilance. The question for your firm is what happens when that occurs — whether you have layers in place that catch what individual attention misses, or whether the breach is the end of the story.

## What personal OPSEC was built to do

The security skills and instincts you've built are all genuinely valuable. They raise the cost of certain attacks and close real vulnerabilities. But their effectiveness is fading in the face of these new threats. And even then, they were designed to protect an individual operating largely on their own.

Running a fund is different. You have shared systems — exchange accounts, custodians, cloud infrastructure, internal tools — with access distributed across a team. People join and leave. Contractors come in for projects and wrap up. Devices that may or may not meet any baseline security standard connect to trading infrastructure. The credential surface expands and contracts in ways that nobody is tracking in real time, because in a lean fund, that's nobody's job.

Personal OPSEC operates on the assumption that you'll catch the threat before it reaches the system. Firm-level security operates on the assumption that sometimes you won't — and builds layers that protect you anyway.

## Defense-in-depth

This is the part most security-aware fund operators haven't had occasion to think through, because it requires having run an actual security program rather than a series of individual security decisions.

**Endpoint detection and response.** When a device gets compromised — through a convincing Zoom call that ends with a terminal command, a malicious download, a link that caught someone at a tired moment — the window between initial infection and the malware establishing persistent access is short. EDR software monitors device behavior in real time, looking for processes doing things processes shouldn't do: writing executables to system directories, making unusual outbound connections, reaching into credential stores. When it sees those patterns, it kills the process. Without it, the first sign of a compromise is whatever the malware does after it's had time to settle in. Most BYOD fund environments have no endpoint visibility at all.

**Network-level filtering.** Every internet connection starts with a DNS lookup. Routing that through a security gateway blocks known malicious and command-and-control domains before a connection is ever made — stopping a significant share of attack payloads at the network layer, before they reach the user, regardless of whether the user recognized the threat. A consumer VPN does not reliably do this. Most handle DNS inconsistently, in ways that vary by operating system and network and are invisible to the user. The protection that feels like it's there often isn't, on any given connection.

**Browser isolation.** For the highest-risk browsing — counterparty due diligence, following links from Telegram, anything involving unknown sources — running the browser session in an isolated environment means that whatever lands on the page can't reach the underlying device. The session is disposable. The device isn't.

**Identity infrastructure.** A real identity provider, with every SaaS system gated through SSO, means access is granted and revoked in one place. When someone leaves, you disable their account in the IDP and they're out of everything — exchanges, cloud infrastructure, internal tools, all of it — rather than having to remember which systems they had access to and chase each one down manually. Onboarding works the same way in reverse. Without this, the credential surface of a firm that's been operating for a few years is almost certainly larger than anyone can accurately account for.

**Credential surface audit.** Even with good identity infrastructure going forward, most firms have years of accumulated access that predates it. Former employees often retain live API keys to exchanges; contractors leave behind admin access that outlasted their projects; shared accounts accumulate passwords that multiple people know and nobody owns. Getting a current, accurate picture of who has access to what — and then closing the gaps — is unglamorous work. It's also where a significant share of low-effort attacks find their entry point.

**Communication channel protocols.** Telegram is the primary communication channel for much of the crypto industry and its primary attack surface. When an account gets compromised, an attacker gains access to months of organizational context — enough to make the impersonation attacks that follow genuinely hard to detect in the moment. Strong second-factor authentication on every account, hardened specifically against SIM-swap, is a firm-level decision. So is having an explicit protocol — not a norm, a protocol — for verifying identity before any sensitive action, in an environment where real-time deepfake calls are an active vector.

## Why most firms don't have this in place

None of these layers are exotic or particularly expensive relative to what they protect. And you're probably familiar with most of these concepts at some level. But building and maintaining these layers requires someone to own the whole picture, and in a lean fund, that's nobody's job.

Security decisions get made in response to moments of concern. Something happens in the industry, or someone reads about a new attack, and a decision gets made. Each decision is reasonable. Nobody reviews whether it still holds six months later. Nobody notices what's missing from the overall posture. Nobody owns the program to evolve it in response to the threats.

The result is a firm where the security-aware people have done the personal OPSEC work, and the firm-level infrastructure either doesn't exist or was set up once and never maintained. That gap was exploitable before the current wave of attacks. It's more exploitable now.

Closing it doesn't require a full-time hire. It requires someone senior enough to see the whole picture and accountable enough to keep it current — someone who reviews access on a regular cadence, responds when something flags, and updates the program as the threat environment changes.

The attacks have gotten good enough to treat individual vigilance as a solved problem — something to route around rather than overcome. The structural layers are what contain the damage when that happens. For most funds, building them is still nobody's job.
