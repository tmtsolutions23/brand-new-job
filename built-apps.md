# Built Apps — Solo Projects

> Two production SaaS products, designed, built, and shipped solo. Both are live and monetized.

---

## 1. Alexandria — AI-Powered Knowledge Base for Organizations

**Site:** https://libalexandria.org · **App:** https://app.libalexandria.org

A private, searchable AI knowledge base that turns an organization's documents into a grounded Q&A system — answers are cited and sourced exclusively from the user's own content, never hallucinated from general knowledge.

### Capabilities
- **AI-Powered Q&A** — plain-language questions, real-time streaming answers with cited sources, grounded via semantic search
- **Document Management** — upload PDF, DOCX, TXT, Markdown; auto-extract, chunk, and embed as vectors with live progress tracking
- **Access Control & Roles** — four permission tiers (Super Admin → User), category-based document access, invitation-based onboarding
- **External Sources** — add URLs as supplementary knowledge with automatic web scraping; toggle external sources per query

### Security (built-in, not bolted on)
- Row-level security (RLS) on every table — multi-tenant isolation
- Grounded answers only — no hallucination from general knowledge
- JWT auth via Supabase, password-strength enforcement, invitation onboarding
- CORS + rate limiting on every API endpoint, server-side input validation
- Sentry production monitoring
- Runs on SOC 2 Type 2 certified infrastructure (Supabase, OpenAI, Cloudflare)
- Zero data retention by AI providers; encryption at rest and in transit; org-level TOTP 2FA

### Pricing (per-organization)
- **Starter** $29/mo — 5 users, 100 docs, 1,000 msgs/mo
- **Team** $79/mo — 25 users, 500 docs, 5,000 msgs/mo (Most Popular)
- **Business** $199/mo — 100 users, 2,000 docs, 25,000 msgs/mo
- **Enterprise** — unlimited, custom integrations

### Serves
Growing SMBs, privacy-first teams, and compliance-conscious orgs needing role-based access and audit-ready security.

---

## 2. MSPSync — PSA-Native Knowledge for MSPs

**Site:** https://mspsync.app

A client-scoped knowledge search for managed service providers. Connects ITGlue, ConnectWise, Zendesk, and Autotask so technicians can ask client-specific questions from the web, Slack, or Teams — without opening five tools.

### Capabilities
- **Client-scoped answers** — ask a plain-language question; MSPSync searches synced documentation, configurations, and tickets for the selected client
- **PSA & documentation connectors** — ITGlue (configs, contacts, documents, flexible assets), ConnectWise Manage (tickets, notes, time entries), Zendesk (tickets + comment threads), Autotask PSA (service tickets, notes)
- **Slack & Teams workflow** — query from chat with client shorthand (e.g. `/mspsync acme: what changed on the VPN ticket?`); answers cite the source record (ticket #, confidence, matching records)
- **Tenant-aware access** — records scoped by organization; role-based access for users, org admins, platform admins
- **Scheduled sync** — keep documentation/tickets current with scheduled syncs, manual refreshes, per-org status tracking
- **Security controls** — row-level security, org-level MFA (TOTP), webhook verification, server-side connector management (credentials never read back into the browser), product/billing event logging

### How it works
1. **Connect your tools** — link ITGlue, ConnectWise, Zendesk, or Autotask (server-side writes)
2. **Sync client data** — normalize, embed, and index configs, documents, tickets, contacts
3. **Ask client questions** — from the web dashboard or Slack, with cited source records

### Built for
MSP teams handling sensitive client records that need clear access boundaries and fast triage.

---

## Shared engineering DNA (both apps)

- **Security-first architecture:** row-level security, org-level MFA, server-side validation, rate limiting, production monitoring
- **AI grounded in user data:** semantic search + retrieval over the user's own content, with cited sources — no hallucination
- **Multi-tenant SaaS:** per-organization isolation, role-based access, invitation onboarding
- **Real integrations:** Supabase, OpenAI, Cloudflare; PSA/RMM/helpdesk/chat connectors
- **Monetized and live:** real pricing tiers, onboarding flows, contact/sales funnel

---

*Both products built solo by Gihuber Then. Contact: info@tmtsolutions.tech · TMT Solutions, Westchester, NY.*
