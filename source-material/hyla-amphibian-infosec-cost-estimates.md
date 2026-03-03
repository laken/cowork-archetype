# SOURCE: Hyla/Amphibian Infosec Cost Estimates
# Extracted from PDF (multi-tab spreadsheet)

---

## Tab 1: Project Plan Summary

Phase-by-phase implementation plan with timing, costs, and Hyla/Amphibian cost splits.

| # | Deliverable | Products | Duration | Week | Product Cost | Service Cost | Total Cost | Hyla Share | Amphibian Share |
|---|---|---|---|---|---|---|---|---|---|
| 0 | Analysis & Plan Development | — | 2 days | Week 1 | $0 | $648 | $648 (est $1,296) | $7,725 | $5,715 |
| 1 | Org Prioritization | — | 1 day | Week 1 | $0 | $648 | $648 | $7.56 | $843 |
| 2 | Email Security | Sublime Mail + Valimail | 1 week | Week 1 | $0 | $1,200 | $1,200 | $0.00 | $2463 |
| 3 | Zero Trust Access & Threat Protection | Cloudflare, Zero Trust | 1 week | Week 2 | $4,039 | $3,000 | $7,039 | $2,775 | $6,721 |
| 5 | Securing Laptops and Mobile Devices | CrowdStrike Falcon EDR | 1 week | Week 3 | $3,564 | $3,900 | $7,464 | $2,757 | $4,707 |
| 7 | Secure Factors | 1Password, Bitwarden | 1 week | Week 4 | $2,131 | $1,200 | $3,331 | $7,029 | $6,211 |
| 2 | SaaS Discovery & Risk Management | Nudge Security | ~1 week | Week 6 | $3,516 | $1,200 | $4,976 | $7,296 | $6,032 |
| 8 | Sought Workspace Hardening | Workspace appgub | 1 week | Week 6 | $913 | $3,000 | $3,693 | $7.56 | $3,060 |
| 1 | Hardware MFA | YubiKeys | ~1 week | Week 6 | $382 | $1,500 | $1,782 | $495 | $1,323 |
| 2 | Secure Communications | Zoom, Telegram, Signal | 1 week | Week 6 | $0 | $2,000 | $2,000 | $688 | $1,463 |
| 3 | Crypto Asset Security | — | 1 week | Week 7 | $0 | $600 | $600 | $7.56 | $602 |
| 10 | ISMS Program | — | ~1 week | Week 7 | $0 | $1,130 | $1,130 | $275 | $813 |
| 8 | Detection Platform | RunReveal | ~1 week | Week 8 | $3,943 | $3,000 | $5,703 | $2,336 | $3,944 |
| 3 | Custom App Security / Amphibian Dashboard | TBD | 1 week | Week 9 | $0 | $6,000 | $6,000 | $0 | $6,000 |

**Hyla Plan Investment (Phases A–N):** $17,732
**Net Hyla Contribution:** $8,032
**Critical subtotals:** $16,730 / $55,497
**Recommended subtotals:** $1,669 / $9,937 (est)
**Grand Totals:** $221,130 / $75,977 (est)

---

## Tab 2: Cost Summary by Phase (Criticality View)

### Critical Items — Hyla: $13,752 | Amphibian: $35,881 | Total: $49,634

| Ref | Phase | Outcome | Type | Hyla | Amphibian | Total |
|---|---|---|---|---|---|---|
| 0 | Infosec Plan Development | Needs assessment, plan documented, vendor secured | Services | $1,913 | $5,738 | $7,650 |
| A | Organizational Prioritization | Align security projects to business outcomes | Services | $141 | $422 | $563 |
| C | Email Security | Anti-phishing & Malware | Product | $0 | $0 | $0 |
| C | Email Security | Anti-phishing & Malware | Services | $300 | $900 | $1,200 |
| D | Cloudflare Zero Trust | App & Service Access control | Product | $2,020 | $2,020 | $4,039 |
| D | Cloudflare Zero Trust | App & Service Access control | Services | $750 | $2,250 | $3,000 |
| E | Crowdstrike | On-device threat detection & containment | Product | $1,782 | $1,782 | $3,564 |
| E | Crowdstrike | On-device threat detection & containment | Services | $975 | $2,925 | $3,900 |
| G | Secure Factors | Centralizes passwords and MFA recovery to block account takeover | Product | $1,044 | $972 | $2,016 |
| G | Secure Factors | Centralizes passwords and MFA recovery to block account takeover | Services | $338 | $1,013 | $1,350 |
| H | Google Workspace | Upgrade includes Vault for compliance and Mobile Device profiles | Product | $0 | $1,320 | $1,320 |
| H | Google Workspace | Upgrade includes Vault for compliance and Mobile Device profiles | Services | $750 | $2,250 | $3,000 |
| I | Hardware Security | Adds phishing-resistant MFA keys to block unauthorized access | Product | $120 | $120 | $240 |
| I | Hardware Security | Adds phishing-resistant MFA keys to block unauthorized access | Services | $375 | $1,125 | $1,500 |
| J | Secure Communications | Documenting SOP for Secure Zoom and messaging | Services | $488 | $1,463 | $1,950 |
| K | Crypto Asset Security | Locks down crypto platform access with vaulting and audit | Services | $150 | $450 | $600 |
| M | ISMS Program | Compliance: Builds repeatable security practices for readiness | Services | $263 | $788 | $1,050 |
| N | Detection | Monitors logs across systems to spot threats and anomalies in real time | Product | $1,596 | $1,596 | $3,192 |
| N | Detection | Monitors logs across systems to spot threats and anomalies in real time | Services | $750 | $2,250 | $3,000 |
| O | Custom Application Security | Amphibian Dashboard — Secures workloads on AWS and Google Cloud | Services | $0 | $6,500 | $6,500 |

**Critical Total: Hyla $13,752 | Amphibian $35,881 | Total $49,634**

### Recommended Items — Total: $20,588

| Ref | Phase | Outcome | Type | Hyla | Amphibian | Total |
|---|---|---|---|---|---|---|
| B | Secure Wireless Service | Prevent SIM-swap, global hotspot, SEC compliance | Product | $8,091 | $4,855 | $12,946 |
| B | Secure Wireless Service | Prevent SIM-swap, global hotspot, SEC compliance | Services | $178 | $534 | $713 |
| F | Nudge Security | Finds unsanctioned apps and SaaS risk to improve visibility and reduce cost | Product | $1,620 | $1,512 | $3,132 |
| F | Nudge Security | | Services | $300 | $900 | $1,200 |
| L | Satellite Backup | Keeps secure access online during internet or power outages | Product | $0 | $1,998 | $1,998 |
| L | Satellite Backup | | Services | $150 | $450 | $600 |

**Recommended Total: Hyla $10,339 | Amphibian $10,249 | Total $20,588**

**Grand Total: Hyla $24,091 | Amphibian $46,130 | Total $70,222**

---

## Tab 3: Year 1 Total Costs by Org

### Product Spend

| Billing Freq | Hyla Costs | Amphibian Costs | Notes |
|---|---|---|---|
| Annual Recurring | $8,091 | $6,175 | Subscriptions |
| Monthly Recurring | $8,062 | $7,882 | Subscriptions |
| One-time | $120 | $2,118 | Hardware |
| **Grand Total** | **$16,273** | **$16,174** | |

### Services Spend

| Billing Freq | Hyla | Amphibian | Notes |
|---|---|---|---|
| One-time | $7,819 | $29,956 | Services |
| **Grand Total** | **$7,819** | **$29,956** | |

---

## Tab 4: Recurring Costs by Vendor (Annual Basis)

| Billing Freq | Vendor | Hyla | Amphibian | Total |
|---|---|---|---|---|
| Annual Recurring | Efani | $8,091 | $4,855 | $12,946 |
| Annual Recurring | Google | $0 | $1,320 | $1,320 |
| Monthly Recurring | Cloudflare | $2,020 | $2,020 | $4,039 |
| Monthly Recurring | Crowdstrike | $1,782 | $1,782 | $3,564 |
| Monthly Recurring | RunReveal | $1,596 | $1,596 | $3,192 |
| Monthly Recurring | Nudge | $1,620 | $1,512 | $3,132 |
| Monthly Recurring | 1Password | $900 | $840 | $1,740 |
| Monthly Recurring | Bitwarden | $144 | $132 | $276 |
| Monthly Recurring | Sublime | $0 | $0 | $0 |
| Monthly Recurring | Starlink | $0 | $0 | $0 |
| One-time | ZSD (Zero Sum Defense) | $3,994 | $11,981 | $15,975 |
| One-time | Archetype | $3,825 | $11,475 | $15,300 |
| One-time | Starlink | $0 | $1,198 | $1,198 |
| One-time | Various | $0 | $800 | $800 |
| One-time | Yubikey | $120 | $120 | $240 |
| **Grand Total** | | **$24,091** | **$39,630** | **$63,722** |

---

## Tab 5: 3-Year Cost View (Equal Cost Split between orgs)

### Critical Total: Hyla $29,233 | Amphibian $29,209 | Total $58,442
### Recommended Total: Hyla $11,425 | Amphibian $8,997 | Total $20,422
### Grand Total: Hyla $40,657 | Amphibian $38,206 | Total $78,864

Key differences from Year 1 (equal split version):
- Crowdstrike: $3,732 each ($7,464 total)
- Cloudflare: $3,520 each ($7,039 total)
- Google Workspace: Hyla $5,460 / Amphibian $5,988 ($11,448 total — higher due to user count diff)
- Custom App Security (Amphibian Dashboard): $3,250 each ($6,500 total)
- Secure Wireless: Hyla $7,234 / Amphibian $4,806 ($12,040 total)

---

## Tab 6: Detailed Line Items (AAA - Formulas tab)

Core pricing assumptions: Archetype at **$150/hr**, ZSD Consulting at **$250/hr**, 10% discount applied.

### Key line items:

| Ref | Phase | Criticality | Item | Vendor | List Price | Units | Annualized Cost | Hyla Cost | Amphibian Cost |
|---|---|---|---|---|---|---|---|---|---|
| 0 | Infosec Plan Dev | Critical | Archetype - Implementation | Archetype | $150/hr | 40 hrs | $7,650 | $0 | $5,738 |
| A | Org Prioritization | Critical | ZSD Consulting | ZSD | $250/hr | 2 hrs | $563 | $113 | $338 |
| A | Org Prioritization | Critical | Archetype - Implementation | Archetype | $150/hr | 3 hrs | $450 | $113 | $338 |
| B | Secure Wireless | Recommended | Efani Safe | Efani | $899/user/yr | — | $12,946 Annual | $8,091 | $4,855 |
| C | Email Security | Critical | Sublime Email security | Sublime | $0/user/month | Org | $0 Monthly | $0 | $0 |
| D | Cloudflare Zero Trust | Critical | Cloudflare Zero Trust with RBI | Cloudflare | $17/user/month | Per user | $337 Monthly | $2,020 | $2,020 |
| E | Crowdstrike | Critical | Crowdstrike Advanced Defend | Crowdstrike | $15/user/month | Per user | $297 Monthly | $1,782 | $1,782 |
| F | Nudge Security | Recommended | Nudge SSPM | Nudge | $10/user/month | Org | $261 Monthly | $1,620 | $1,512 |
| G | Secure Factors | Critical | 1Password MSP | 1Password | $5/user/month | Org | $145 Monthly | $900 | $840 |
| G | Secure Factors | Critical | Bitwarden Individual | Bitwarden | $1/user/month | Per user | $23 Monthly | $144 | $132 |
| H | Google Workspace | Critical | Workspace Business Plus | Google | $264/user/yr | Org | $1,320 Annual | $0 | $1,320 |
| I | Hardware Security | Critical | Yubikeys | Yubikey | $120/unit | Per user | $900 One-time | $120 | $120 (+ $600 services) |
| J | Secure Comms | Critical | ZSD Consulting | ZSD | $250/hr | 6 hrs | $1,350 | $488 | $1,463 |
| L | Satellite Backup | Recommended | Starlink Hardware | Starlink | $599/unit | Per user | $1,198 One-time | $0 | $1,198 |
| M | ISMS Program | Critical | Archetype - Implementation | Archetype | $150/hr | 4 hrs | $150 One-time | $38 | $113 |
| N | Detection | Critical | RunReveal | RunReveal | $9.50/user/month | Org | $2,700 One-time | $1,596 | $1,596 |
| O | Custom App Security | Critical | Archetype - Implementation | Archetype | $150/hr | 10 hrs | $1,500 One-time | $0 | $1,500 |
| O | Custom App Security | Critical | ZSD Consulting | ZSD | $250/hr | 20 hrs | $5,000 One-time | $0 | $5,000 |

---

## Tab 7: User/Seat Count by Product

| Product | Hyla only | Amphibian only | Shared | Total |
|---|---|---|---|---|
| 1Password MSP | 9 | 8 | 6 | 29 (but org-priced) |
| Bitwarden Individual | 9 | 8 | 6 | 23 |
| Cloudflare Zero Trust with RBI | 8 | 8 | 6 | 22 |
| Crowdstrike Advanced Defend | 8 | 8 | 6 | 22 |
| Nudge SSPM | 9 | 8 | 6 | 29 (but org-priced) |
| RunReveal | 8 | 8 | 6 | 28 |
| Valimail Align | 8 | 8 | 6 | 22 |
| Sublime Email security | 9 | 11 | 6 | 32 (but org-priced at $0) |
| Workspace Business Plus | 0 | 5 | 0 | 5 |
| Efani Safe | 7 | 3 | 6 | 16 |
| Yubikeys | 1 | 1 | 0 | 2 |
| Backup power UPS | 1 | 1 | 0 | 2 |
| Starlink Hardware | 1 | 1 | 0 | 2 |

---

## Tab 8: Product Master List with Pricing

| Item | Type | Vendor | Units | List Price | Cost Split | Category | Current Cost | ZSD Reseller |
|---|---|---|---|---|---|---|---|---|
| 1Password MSP | Product | 1Password | per user/month | $5.00 | Org | 1 - Essential | $2.25 | ✓ |
| Bitwarden Individual | Product | Bitwarden | per user/month | $1.00 | Per user | 1 - Essential | — | ☐ |
| Cloudflare Zero Trust with RBI | Product | Cloudflare | per user/month | $17.00 | Per user | 1 - Essential | — | ✓ |
| Crowdstrike Advanced Defend | Product | Crowdstrike | per user/month | $15.00 | Per user | 1 - Essential | — | ✓ |
| Nudge SSPM | Product | Nudge | per user/month | $10.00 | Org | 1 - Essential | — | ✓ |
| RunReveal | Product | RunReveal | per user/month | $9.50 | Org | 1 - Essential | — | ✓ |
| Valimail Align | Product | Valimail | — | $16.00 | — | 1 - Essential | — | ✓ |
| Sublime Email security | Product | Sublime | per user/month | $0.00 | Org | 1 - Essential | — | ☐ |
| Workspace Business Plus | Product | Google | per user/year | $264.00 | Org | 1 - Essential | $102.00 | ✓ |
| Efani Safe | Product | Efani | per user/year | $899.00 | Per user | 2 - Comprehensive | — | ✓ |
| Yubikeys | Product | Yubikey | One-time | $120.00 | Per user | 2 - Comprehensive | — | ☐ |
| Backup power UPS | Product | Various | One-time | $400.00 | Per user | 3 - Absolute | — | ☐ |
| Starlink Hardware | Product | Starlink | One-time | $599.00 | Per user | 3 - Absolute | — | ☐ |
| Starlink individual | Product | Starlink | per user/month | $65.00 | Per user | 3 - Absolute | — | ☐ |
| Archetype - Implementation | Services | Archetype | per hour | $150.00 | Shared | 4 - N/A | — | — |
| ZSD Consulting | Services | ZSD | per hour | $250.00 | Shared | 4 - N/A | — | — |

**Product Categories:**
- **1 - Essential:** Core security stack (EDR, Zero Trust, email security, password management, detection)
- **2 - Comprehensive:** Enhanced protection (mobile security, hardware MFA)
- **3 - Absolute:** Maximum resilience (satellite backup, power backup)
- **4 - N/A:** Services (implementation hours)

---

## Key Financial Summary

- **Archetype implementation rate:** $150/hr
- **ZSD Consulting rate:** $250/hr (co-vendor, Zero Sum Defense)
- **Archetype Year 1 fees:** Hyla $3,825 + Amphibian $11,475 = **$15,300 total**
- **Critical security stack, first year:** $49,634 (product + services, both orgs)
- **Full program including recommended:** $70,222
- **3-year view, equal split:** $78,864 grand total
- **Hyla is a smaller org** (fewer seats/users) — lower share on per-user items
- **Amphibian drives higher services cost** due to larger team + custom dashboard work + compliance (approaching RIA status)
- **ZSD** (Zero Sum Defense) appears to be a co-vendor/partner on implementation alongside Archetype
