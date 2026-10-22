# Gihuber Then — Profile & Resume Refresh

> Working document: skills, projects, and working products built together, pruned for the current job market. Built from a full inventory of our collaboration (Sep–Oct 2026).

---

## Positioning

Senior IT / Network Engineer (19+ yrs) who has spent the last year building **production-grade AI trading and automation systems** — self-hosted infrastructure, multi-agent orchestration, real-time data pipelines, and deterministic risk engines. The differentiator for the current market: **I don't just administer infrastructure — I design and operate autonomous systems that make decisions and move money.**

---

## Core Skills

### Infrastructure & Networking (foundation)
- **Networking:** Cisco CCNA (Routing & Switching, Network Security), full Meraki suite (80+ deployments), Cisco ASA 5500, switches, core chassis, wireless controllers, Aironet APs
- **Windows Server administration**, VMware virtual environments, AzureAD, Google Workspace, Office 365
- **MSP platforms:** Kaseya, N-Able; hardware procurement via Tech Data / Ingram Micro
- **Team leadership:** supervised 12+ junior engineers (ticketing, time tracking, task assignment); $1M+ project budgets

### Modern Engineering & Automation (new, high-demand)
- **Self-hosted automation:** n8n workflow orchestration (custom workflows, SQL-level activation, webhook APIs, failure-watcher crons)
- **Linux / VPS operations:** systemd service units, SSH, process management, journald, firewall/iptables, resource-constrained deployment
- **Python engineering:** deterministic trading backends, risk engines, data pipelines, CLI tools, hermetic test suites (pytest, TDD)
- **AI / LLM integration:** Anthropic Claude (structured outputs, schema validation, fail-closed design), prompt engineering, multi-agent orchestration
- **Git / GitHub:** repo management, PR workflows, CI, branch protection, secrets management
- **Real-time data:** REST/WebSocket APIs, order-book data, market data aggregation, rate-limit handling

### Quantitative & Risk Engineering (the edge)
- **Deterministic risk engines:** Kelly criterion sizing, stop-loss bands, kill switches, daily loss stops, order caps, fill reconciliation
- **Backtesting & paper-first validation:** out-of-sample testing, honest performance measurement, avoiding curve-fitting
- **Data-driven decision gates:** hard validation gates that short-circuit before any action (fail-closed design)

---

## Working Products (built together, live or validated)

### 1. Polymarket Smart Money Consensus — copy-trading pipeline
- **What:** Self-hosted n8n workflow that scans the Polymarket PnL leaderboard (top 40 traders), extracts fresh positions, finds **consensus** (≥3 top traders on the same market+outcome), verifies via gamma API, runs LLM analysis, and posts a sized bet report to Discord.
- **Engineering highlights:** half-Kelly position sizing from a tracked bankroll, bankroll webhook, Discord webhook delivery, SQL-level workflow activation, failure-watcher cron, scorecard + picks history ledger.
- **Status:** Built, deployed, verified end-to-end. Report-only (no auto-orders).

### 2. Northstar — XLF options call-debit-spread engine
- **What:** Paper-first options trading backend for XLF call debit spreads (credit spreads explicitly excluded by design).
- **Engineering highlights:** deterministic option backend (payoff, net Greeks, Black-Scholes), spread validation gates (debit cap, DTE window, liquidity, staleness, account risk), append-only SQLite ledger, LLM research-report adapter with a deterministic thesis gate that short-circuits before spread validation, local dashboard (systemd, localhost), 104 tests green.
- **Status:** Built, committed, daily scan cron live.

### 3. pumpfun-scout — Solana memecoin scanner
- **What:** Real-time Solana/pump.fun token scanner with a proprietary scoring model (M16) for early signals.
- **Engineering highlights:** multi-factor scoring (first buys, early share, volume, velocity, cohort), concentration/pump detection, market-cap preference, Anthropic redteam/thesis split, hermetic tests.
- **Status:** Built; pipeline paper-only + paused.

### 4. BTC 15-min Up/Down copy-trader
- **What:** Copy-trading executor for Polymarket BTC 15-min Up/Down markets.
- **Engineering highlights:** SecureClient + RelayerApiKey auth, marketable-limit (FAK) order placement, Kelly sizing, kill switch, daily loss stop, order cap, fill reconciliation against data API, execution monitor cron that verifies end-to-end fills.
- **Status:** Built and deployed on VPS.

### 5. Gaming/esports copy-trader executor
- **What:** Copy-trader for esports tournament markets (LoL, Dota 2, CS2, Valorant), reusing proven order mechanics with gaming-aware settlement.
- **Status:** Built, deployed with kill switch.

### 6. Freqtrade — Hyperliquid perps bot
- **What:** Automated perps trading on Hyperliquid via Freqtrade.
- **Engineering highlights:** event-driven results reporter (only emits on trade open/close), honest performance assessment (win rate, R:R, leverage analysis), OI/funding data integration.
- **Status:** Running; data-driven strategy iteration.

### 7. earn-or-die — crypto swing book (Ophiel TA method)
- **What:** Disciplined crypto swing-trading system with a named TA analyst persona (Ophiel).
- **Engineering highlights:** hard gate system (trend, OI conviction, funding, volume, no-chase rules), entry/SL/TP zones, fractional-Kelly sizing, setups + trade logs, chart rendering from live data, 15-min candidate-scan cron.
- **Status:** Live, 250+ setups logged.

### 8. CoinPoker Offline Table Advisor
- **What:** Offline poker table advisor (range charts, push/fold, hand evaluation) — built with a hard compliance gate (no real-time assistance while client open).
- **Engineering highlights:** range parser (wildcard/dash notation), sourced push/fold charts, 61 tests, PR workflow, gap-tracking sync doc.
- **Status:** Built, merged, open-source.

### 9. Hermes & Co. — multi-agent company OS
- **What:** An operating system for running an AI "company" of named agent personas (Atlas, Daedalus, Ophiel, Midas) with distinct roles, channels, and webhooks.
- **Engineering highlights:** persona webhook-posting layer, standup digest cron, kanban board, Obsidian vault, org chart, escalation ladder.
- **Status:** Live.

### 10. Kalshi API integration
- **What:** Kalshi prediction-market API integration (auth, portfolio/balance, leaderboard research).
- **Status:** API auth verified; research done.

---

## Ideas & Methodologies (proven thinking)

- **"Consensus itself is the signal"** — copy-trading top-trader consensus EARLY, ride the move; don't let an LLM veto a data-backed consensus.
- **Agents propose; deterministic software decides; only a separately controlled adapter executes.** The core safety architecture across every trading system.
- **Fail-closed design** — if the LLM/key/data is unavailable, degrade to a deterministic chain-only path or halt; never guess.
- **Paper-first validation** — backtest, replay, out-of-sample test, then forward paper-trade before any live capital.
- **Honest measurement** — report win rate, R:R, and confidence intervals; refuse to curve-fit on small samples.
- **Kill switches and hard caps** — every live system has a kill switch, daily loss stop, and order cap.
- **No-chase discipline** — never chase a move past a defined limit; wait for the retest.

---

## What this means for the job market

- **For IT/Network roles:** 19+ years of MSP/enterprise networking + modern automation (n8n, Linux, Python, CI/CD) — you're not just "the network guy," you automate the network.
- **For DevOps / Platform / Automation roles:** self-hosted infrastructure, systemd, API integration, multi-agent orchestration, real-time pipelines.
- **For Quant / Trading-adjacent roles:** production risk engines, Kelly sizing, backtesting, data pipelines, LLM integration — real, working systems, not demos.
- **For AI / LLM Engineering roles:** structured-output LLM integration, fail-closed design, multi-agent orchestration, prompt engineering at scale.

---

*Generated from a full inventory of our collaboration. Update as new projects land.*
