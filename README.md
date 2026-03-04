# Archetype Consulting — Working Repository

Andy Laken / Archetype Consulting. Fractional CTO practice focused on crypto funds and fintech.

**Start here for any new session:** Read `CLAUDE.md` first (session orientation), then `context.md` (standing brief — clients, voice, pricing, pipeline).

---

## Folder Structure

### `/library`
Research, strategy documents, and working design briefs. The primary working files for the crypto hardening package live here.

- **`crypto-hardening-package-wip.md`** — Master WIP for the productized security offering. Start here for any package design, scope, or pricing work. Contains settled decisions, open questions, and links to all related files.
- **`edr-evaluation-report.md`** — Full EDR comparison across 9 tools. Shortlist: Huntress (preferred, channel question pending) and SentinelOne (fallback). CrowdStrike, Sophos, Malwarebytes off the list with documented reasons.
- **`privacy-framework-one-pager.md`** — Client-facing day-one deliverable. What each tool sees, who has access, under what conditions. Delivered before any agent is deployed.
- **`value-based-pricing-synthesis.md`** — Methodology reference: Stark, Blair Enns, Pia Silva, Ron Baker/Alan Weiss.
- **`fsp-pricing-analysis.md`** — Sub-agent pricing research. $35K fixed fee recommendation (not yet validated by Andy).
- **`fsp-sales-script.md`** — Draft 20-minute discovery call script.
- **`fsp-one-pager.md`** — Draft client-facing positioning for the package.
- **`fsp-financial-model.md`** — Unit economics and revenue scenarios.
- **`Archetype-Business-Model-and-Pricing.docx`** — Earlier business model document (AI-generated in prior session, treat with caution — not validated decisions).
- **`Archetype-Marketing-Plan.docx`** — Earlier marketing plan (same caveat).
- **`Archetype-Consulting-QA-Critique.docx`** — QA critique of earlier AI-generated materials.

### `/article-drafts`
Working drafts for archetypeconsulting.io blog. Not for publication until approved.

- **`draft-d-combined.md`** / **`draft-d-combined.mdx`** — Current active draft: SIM swap / defense in depth article.
- Earlier drafts (`draft-a` through `draft-c`, `draft-e`, `draft-f`) are prior iterations.
- **`outlines.md`** — Article outlines.

### `/outreach-resources`
Materials for Andrew Hoppin's warm Telegram outreach to Amphibian Unite members.

- **`amphibian-unite-members.md`** — 194-member Telegram channel list, tiered by ICP fit. Note: this is a loosely aggregated community list, not a curated prospect list. Tier 1 = crypto funds/capital management, not necessarily the biggest names.
- **`telegram-blurbs-andrew.md`** — Three draft Telegram messages for Andrew to use (group post, story-led, casual DM variants).

### `/source-material`
Internal documents from Hyla/Amphibian engagements. Ground truth for package design.

- **`hyla-amphibian-joint-security-proposal.md`** — Full 9-phase joint security proposal (July 2025). Primary source for package scope.
- **`hyla-amphibian-infosec-cost-estimates.md`** — Cost breakdown. Key: Andy billed at $150/hr, ~$15,300 total across both orgs — a floor, not a pricing anchor.
- **`hyla-proposed-security-upgrades-exec-summary.md`** — Hyla-only exec summary (June 2025).
- **`condensed-joint-security-executive-summary.md`** — Condensed joint proposal summary.
- **`2026-security-evolving-threats-protective-action.md`** — Co-authored by Andy and Andrew Hoppin. Documents the real Stardust Chollima malware incident (fake Zoom), threat landscape, and case for CrowdStrike + Cloudflare WARP. Contains the privacy boundary language used with Hyla staff.
- **`crowdstrike-zoom-hack-analysis.md`** — Analysis of the CrowdStrike/Zoom hack incident.
- **`byod-transparency-informed-consent.md`** — BYOD transparency and informed consent framework.
- **`hyla-phishing-1-pager.md`** — Phishing one-pager for Hyla staff.
- **`principals-joint-security-executive-overview.md`** — Executive overview for principals.

---

## Key Context for New Sessions

**Business situation:** Tight runway (1.7–3.1 months as of early March 2026). Primary goal: get checks in the door. Andrew Hoppin is the referral pipeline — warm Telegram intros to peer fund managers.

**Primary work in progress:** Productized crypto fund security hardening package. Fixed scope, fixed price, solo delivery. Target: $35K (unvalidated). Core scope settled (7 components). Primary open question: EDR default and post-handoff incident response ownership. See `library/crypto-hardening-package-wip.md`.

**Key decisions made:**
- CrowdStrike off the list (UI complexity for non-security operators)
- Tailscale is not a Cloudflare WARP replacement (different architectural problem)
- Huntress SOC does not have interactive shell access — verified against documentation
- Single password manager, not split 1Password/Bitwarden
- Austin Quam (Zero Sum Defense) is a potential IR referral partner, not a co-delivery partner

**Key decisions pending:**
- Huntress vs. SentinelOne as EDR default (Huntress preferred but channel/handoff question needs a call with their partner team)
- Final price validation
- Whether to offer a light post-handoff retainer

**Pricing note:** The tier structure and diagnostic pricing that may appear in older documents (Archetype-Business-Model-and-Pricing.docx, context.md) were AI-generated in prior sessions and are not validated decisions. Treat as drafts only.

---

*Last updated: March 2026*
