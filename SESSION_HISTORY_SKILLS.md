# Skills, Strengths & Work Inventory — Distilled from Session History

> Source: ~35 sessions, Aug 20 – Oct 21, 2026. Client names are anonymized (financial, legal, non-profit, and professional-services clients of an NYC MSP).

---

## Profile in one paragraph

Senior MSP network/security engineer who works at the intersection of **Meraki/Cisco infrastructure, ticket-driven operations, and AI-assisted automation**. Strong at triage under pressure, verifying claims against vendor documentation before committing to changes, and turning tribal knowledge into runbooks and NOC-ready instructions. Increasingly builds tooling (agent workflows, diagram engines, audit spreadsheets) rather than just operating infrastructure.

---

## Core Skills

### Networking & Security (primary strength)
- **Meraki MX / MS / MR / Dashboard:** HA/warm spare, AutoVPN, client VPN, AnyConnect/Secure Client, switch stacking, STP root/priority design, RF profile tuning, licensing (co-term), firewall rules, uplink/event/log analysis
- **Cisco Catalyst 9300L stacks, CW9164I/9166I/917x APs, Wi-Fi 6E/7 selection**
- **Identity & access:** Meraki SAML SSO (MSP multi-org access), Entra ID SAML for AnyConnect, 802.1X / EAP-TLS architecture comparisons (JumpCloud, SecureW2, Google-native certs)
- **Compliance:** PCI scan remediation (3DES / DH group 2 findings traced to legacy L2TP client VPN)
- **Platforms in daily use:** ConnectWise, Thread PSA, IT Glue, NinjaOne, SentinelOne, Avanan, Umbrella, Pax8, Blackpoint, ConnectSecure, Intune, Microsoft 365/Exchange, Lucidchart

### Operations & Communication
- Client-ready writing: concise, direct, non-technical-audience communications
- Internal ticket notes, NOC runbooks, change plans, rollback baselines, and executive summaries
- Vendor escalation (ISP/SD-WAN) with evidence-based timelines and pointed questions

### Automation, AI & Engineering
- Designing **AI-agent workflows** against MSP stacks (Vega agent MCP, ConnectWise, Thread, IT Glue, Meraki API, Lucid)
- Prompt/skill authoring, multi-agent org design, MCP integrations
- Python scripting, Linux/VPS admin (systemd, installers, dependency debugging), spreadsheet automation (openpyxl)
- Quantitative thinking: sample-size critique, rug/EV analysis, filter validation, paper-first testing

---

## Things I've Solved

| Problem | What I found / did |
|---|---|
| **Intermittent ISP/SD-WAN outages (3 in 5 weeks)** | Full triage: ruled out our side (MX uplinks, DMZ switch ports, STP, PoE events), built an outage timeline from Meraki loss/latency data, spotted a 3 ms → 80 ms latency jump indicating a path change, and wrote a targeted escalation to the SD-WAN vendor |
| **Failed PCI scan** | Traced two Medium findings to the legacy L2TP/IPsec client VPN (not AutoVPN); proposed disabling it and migrating to AnyConnect; wrote the ticket reply |
| **VPN users can't reach home printers/NAS** | Diagnosed full-tunnel config; moved to split tunnel with correct routes/DNS; verified approach against Meraki docs; confirmed site-to-site tunnels unaffected |
| **SaaS access over AnyConnect (static-IP allowlist)** | Executed a controlled route change at night, verified via Meraki change log, DNS, and session logs; flagged approval-trail gaps |
| **Five-switch cascade outage + "configuration out of date"** | Researched cloud check-in behavior and daisy-chain failure patterns; gave wait/escalate thresholds |
| **Sticky clients / AP disconnects** | Diagnosed RF profile (5 GHz power at 27, low min-bitrate); staged one-change-at-a-time plan with rollback values |
| **Switch-stack replacement** | Step-by-step stack member swap preserving uplinks and STP; diagnosed dark stack ports (missing adapter modules/cables) |
| **HA pair breakup for a floor build-out** | Validated against live Meraki config: WAN side safe, but caught LAN-uplink leak, co-term license shortfall, and security-sensor mirroring gap |
| **Quote review before purchase** | Caught wrong-region AP SKUs, missing power cords/rack screws, port-count reduction, stale EoS firewall, and SOW model mismatches |
| **Multi-floor uplink topology** | Explained STP loop behavior; recommended MDF as root, controlled blocked link; later analyzed 6-switch ring diameter and bandwidth |
| **Meraki license questions** | Verified Enterprise → Advanced Security upgrade path via support (with credit); co-term calculator reconciliation |
| **Pre-staging MX config with no MX** | Researched dashboard behavior, then corrected my own overconfident claim when sources didn't support it |
| **Wired vs. wireless speed expectations** | Structured diagnostic order (link negotiation, bypass router, nearby server) |
| **Hermes agent install failure on Ubuntu** | Root-caused missing `libatomic`, partial root install, and PATH caching |
| **Duplicate/misrouted tickets** | Used PSA activity logs to show an assignment was a human action, not automation |

---

## Things I've Built

1. **Meraki → Lucidchart network diagram engine.** Generates standardized topology diagrams from live Meraki and IT Glue data. Handles firewalls behind upstream routers, suffixed hostnames, firewall-only sites, AP collapsing, and ISP/IP reconciliation. Passed overlap/line checks on all pages; surfaced real documentation drift (stale ISP records, missing account numbers). Packaged as a reusable skill.
2. **NOC audit workbook (Advanced Security license coverage).** Multi-tab Excel with live progress tracker, dropdown-driven fields, conditional formatting, expiry flags, and a rule that forces license-edition verification before threat-protection checks.
3. **Vega agent / Lucid integration plan.** Brainstormed architecture for an agent that builds network diagrams from chat input or from IT Glue + Meraki API data.
4. **Hermes "company OS."** Skill file defining a multi-agent organization: orchestrator/hiring manager, COO, channel-per-team, Obsidian vaults, company kanban, Discord permission model, and an idempotent `discord.py` setup script.
5. **Gil's Corner newsletter.** Bi-weekly AI/tech newsletter with an analog-techy design; evaluated Outlook Newsletters vs. HTML-import platforms and concluded the design required a custom-HTML tool.
6. **AP placement overlays & coverage plans.** Floorplan-driven AP counts and placement (school, retail, office) with annotated SVG/PNG output and install notes (PoE+, RF settings, wired POS).
7. **Ticket-ready write-ups in a consistent voice.** Internal notes, time entries, escalation emails, and a NOC runbook for a SAML AnyConnect rollout, including audit-before-post and an addendum when scope changed.

---

## Strengths (as demonstrated)

- **Verification discipline:** repeatedly asks for doc-backed confirmation before committing; I corrected my own claims when sources didn't support them
- **Triage structure:** rule out our side first, build a timeline, then escalate with specific questions
- **Risk awareness:** surfaces the non-obvious gotcha (license compliance, VLAN leakage, approval trail, rollback baseline)
- **Scope control:** narrows to the phase that matters (e.g., one site now, second later) and updates NOC when it changes
- **Concise communication:** prefers short, direct client messages and plain-language explanations
- **Tool-building mindset:** turns repeated tasks into engines, workbooks, and skills
- **Analytical skepticism:** small samples, survivorship, and "luck vs. signal" checks in quantitative work

---

## Secondary / Side Projects (in sessions)

- Reviewed a trading-bot filter-validation brief: found that rug rate dominates P&L, per-12h pass bars reward inactivity, and sample sizes can't support verdicts; produced a 10-point fix list
- Crypto and prediction-market research (token bull cases, launch positioning), including scam-spotting
- Self-hosted agent tooling (Grok Bot/model-routing, Hermes Agent)
- Android TV debloat walkthrough (ADB, storage-threshold workaround)

---

## Resume-ready bullets

- Led triage and vendor escalation for recurring SD-WAN outages, isolating root cause outside client infrastructure with Meraki telemetry
- Migrated legacy client VPN to AnyConnect to remediate PCI findings; executed controlled route changes with audit trail and rollback
- Built a Meraki/IT Glue → Lucidchart diagram engine that produces standardized network documentation and exposes documentation drift
- Created NOC audit workbooks and runbooks covering license coverage, VPN rollout, and SAML-based admin access
- Reviewed hardware quotes against vendor documentation, catching SKU, power, and compatibility errors prior to purchase
- Designed multi-agent AI workflows integrating PSA, RMM, documentation, and network APIs

---

*Generated from Claude session history. Update as new work lands.*
