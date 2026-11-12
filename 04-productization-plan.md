# 04 – Productization Plan: Returns & Orders Assistant (ROA)

**Version:** 1.0 (after the workshop) | **Owner:** Product Manager | **Decision:** Launch with conditions ([feedback log #12](03-stakeholder-feedback-log.md))

> All figures are **sample data / documented assumptions** for the fictional Northwind scenario.

## Contents
1. Launch scope
2. Target users
3. Release criteria & launch readiness checklist
4. Rollout plan
5. Onboarding & change management (Prosci ADKAR)
6. Adoption & success metrics (Google HEART)
7. Customer onboarding
8. Support & operations
9. Risks, dependencies & mitigations
10. Prioritized next backlog

---

## 1. Launch scope

| In scope for GA | Out of scope for GA (and why) |
|---|---|
| Order status & tracking (web + app chat) | **Exchanges / size swaps**: accuracy below target → escalate to a human (BL-02) |
| Standard returns within the 30-day window + prepaid label | **Damaged / defective items**: needs judgment and photos → human |
| Refunds ≤ $200 to the original payment method | **Refunds > $200**: stays a manual team-lead approval (BL-12 revisits) |
| Identity verification (email + order #) | **Spanish**: post-launch (BL-04); routed to bilingual agents |
| Human handoff with full context | **Voice / phone channel**: not planned this half |
| English only, US customers | **International orders**: different policies and carriers |

**Scope principle:** the assistant only *acts* where policy is unambiguous. Everywhere else it *hands off*. A wrong action costs more than an escalation.

## 2. Target users

| Segment | Size (yearly) | Need | Success looks like |
|---|---|---|---|
| **Primary:** customers with an existing order asking about status/returns | ~520K in-scope contacts | Fast, accurate answer or action without waiting | Resolved in < 3 min, no repeat contact |
| **Secondary:** Tier-1 support agents (~85 FTE) | — | Receive escalations they can resolve without re-asking | Lower handle time on escalated chats; more time on complex cases |
| **Internal:** Support team leads, policy owners | ~10 | Keep bot content current; monitor quality | Policy updates live within 24 h |

## 3. Release criteria & launch readiness checklist

### 3a. Release criteria (phase gates)

All must be **met and evidenced** before the 25% → 50% gate. P0 items must be closed before GA at 5%.

| # | Criterion | Threshold | Evidence | Status |
|---|---|---|---|---|
| RC1 | Answer accuracy (audited) | ≥ 99.0% on n = 500, stratified by intent | QA audit report | 🟡 98.2% |
| RC2 | Containment, in-scope intents | ≥ 35% | Analytics dashboard | ✅ 41% |
| RC3 | CSAT, contained conversations | ≥ 4.2 / 5 | Post-chat survey | ✅ 4.3 |
| RC4 | Handoff keeps context | 100% on a 200-conversation test incl. app→web | Test report | 🟡 97% |
| RC5 | Load test | 2× forecast peak, p95 latency < 4 s, 0 dropped label requests | Load test report | 🔴 Not run |
| RC6 | Security & privacy review | Passed; PII redaction verified; retention = 6 mo | Signed review | 🟡 In progress |
| RC7 | AI disclosure wording | Legal sign-off | Approval email/ticket | 🟡 Pending |
| RC8 | Accessibility | WCAG 2.2 AA, no critical issues | Audit report | 🟡 Scheduled |
| RC9 | Operational readiness | On-call, runbook, alerts, kill switch tested | Game-day record | 🔴 Not started |
| RC10 | Agent readiness | ≥ 90% of Tier-1 agents trained + certified on handoff console | LMS report | 🔴 Not started |

**Kill switch / rollback rule:** if accuracy on the daily sample falls below 97%, CSAT falls below 3.9 for 2 days in a row, or there is a Sev-1 incident, traffic returns to the previous phase (or to 0%) within 15 minutes using a feature flag.

### 3b. Launch readiness checklist (adapted from the Aha! launch checklist)

| Area | Item | Owner | Status |
|---|---|---|---|
| **Product** | Scope frozen; release notes written | PM | ☐ |
| | Feature flags per traffic phase | Eng | ✅ |
| **Engineering** | Load test (RC5); carrier queue/retry (BL-03) | Eng | ☐ |
| | Monitoring dashboards + alerts | Eng | ☐ |
| **Quality** | Accuracy audit (RC1); regression suite of 300 golden conversations | QA | ☐ |
| **Legal / Privacy** | AI disclosure (RC7); retention + DPA review (RC6) | Legal | ☐ |
| **Support** | Agent training (RC10); macros for handoff scenarios; escalation paths | Support Ops | ☐ |
| **Marketing / Comms** | Help-center article "Get help faster with chat"; in-app entry-point copy | Marketing | ☐ |
| **Internal comms** | Announcement to support org; FAQ for agents | Support Ops | ☐ |
| **Go/no-go** | Phase-gate meeting booked for each phase | PM | ☐ |

## 4. Rollout plan

| Phase | Dates (target) | Traffic | Gate to proceed |
|---|---|---|---|
| 0 – Fix & harden | Nov 17 – Jan 9 | 5% (current pilot) | All P0 items closed |
| 1 – GA start | Jan 12 | 5% → **25%** | 7 days stable; RC2, RC3 held |
| 2 – Expand | ~Jan 26 | **50%** | **All** RC1–RC10 met (sponsor go/no-go) |
| 3 – Full | ~Feb 9 | **100%** | 14 days stable at 50%; no Sev-1 |
| 4 – Extend | Mar+ | — | Spanish, exchanges (backlog) |

*Why January:* it avoids changes during the holiday code freeze while still catching the post-holiday returns peak at a controlled 25–50% exposure.

## 5. Onboarding & change management (Prosci ADKAR)

The biggest change is for **support agents**, whose work shifts from simple lookups to complex escalations. Customers see a small change (a better chat), but agents see a large one.

| ADKAR stage | Goal for agents | Tactics | Measure |
|---|---|---|---|
| **Awareness** | Know *why* we're launching and what it means for them | Message from the VP CX: "the bot takes the repetitive work; you take the hard problems." Make clear no role reductions are planned for this launch *(confirm with HR/leadership)* | Pulse survey: % who can state the reason |
| **Desire** | Want it to succeed | Agents' top 3 pain points fixed in the handoff console; champions from each shift chosen | Champion sign-ups; sentiment survey |
| **Knowledge** | Know how to work with handoffs | 45-min training + sandbox practice with 5 scenarios; one-page quick-reference | ≥ 90% certification (RC10) |
| **Ability** | Do it under real load | Champions on the floor for the first 2 weeks of each phase; daily huddle | Escalated-chat handle time; QA scores |
| **Reinforcement** | Keep it going | Weekly "bot fail of the week" review where agents flag bad answers; recognition for top flaggers; agent feedback feeds the backlog | Flags submitted per week; repeat-issue rate |

## 6. Adoption & success metrics (Google HEART)

Following HEART's **Goals → Signals → Metrics** method.

| Dimension | Goal | Signal | Metric | Target (90 days after GA) | Pilot baseline |
|---|---|---|---|---|---|
| **Happiness** | Customers feel helped | Post-chat survey | CSAT on contained chats | ≥ 4.2 | 4.3 |
| **Engagement** | Customers use chat instead of email for in-scope issues | Chat sessions, by intent | Share of in-scope contacts starting in chat | ≥ 55% | 38% |
| **Adoption** | New users try the assistant | First chat from a customer who used email before | % of returning customers using chat for the first time | ≥ 20% per quarter | n/a |
| **Retention** | Customers come back to it | Repeat chat for a later order | % of chat users who use it again within 90 days | ≥ 40% | n/a |
| **Task success** | Problem solved correctly, first time | Contained; no repeat contact within 72 h; audited accuracy | Containment; repeat-contact rate; accuracy | ≥ 35% · ≤ 8% · ≥ 99% | 41% · 11% · 98.2% |

**Business outcome metrics (for Finance):** cost per contact, net yearly savings (target ≥ $350K after run cost), agent handle time on escalated chats.
**Guardrail metrics (must not get worse):** overall CSAT across all channels, complaint rate, refund error rate, chargebacks.

**Reporting:** live dashboard + weekly one-page exec update (BL-11).

## 7. Customer onboarding

- **Entry points:** "Track or return an order" button on the order-history page, order confirmation email and the help center. Customers start where the problem shows up.
- **First message:** AI disclosure + what it can do ("I can track orders and start returns. For anything else I'll connect you to a person.")
- **Always-visible "Talk to a person" button.** Lowering the cost of escalating builds trust.
- **Help-center article** and a short GIF showing a return in chat.

## 8. Support & operations

### Support model
| Tier | Handles | SLA |
|---|---|---|
| Assistant | In-scope intents | Instant |
| Tier 1 agents | Handoffs, out-of-scope requests | First response < 2 min in chat |
| Tier 2 / team leads | Refunds > $200, disputes, escalated complaints | < 4 h |
| Platform on-call (Eng) | Outages, errors, latency, wrong-answer incidents | Sev-1: 15 min response |

### Operations
- **Monitoring:** latency, error rate, carrier API failures, escalation rate, daily accuracy sample, cost per conversation
- **Alerts:** paging when error rate > 2% (5 min), p95 latency > 6 s, carrier queue backlog > 500
- **Runbook:** feature-flag rollback, carrier outage message, model provider outage → route all chat to agents
- **Quality loop:** QA analyst reviews 50 transcripts a day (🖐️, funded for 90 days) → errors labeled → fixes to prompts or retrieval → added to the regression suite
- **Content updates:** Support Ops edits policy content; changes go to staging, pass the regression suite, then go live within 24 h (BL-05)
- **Cost control:** monthly run-cost review against the $58K/yr estimate; alert at 120% of budget

### RACI

| Activity | Product | Engineering | Support Ops | Legal | VP CX |
|---|---|---|---|---|---|
| Go/no-go at phase gates | R | C | C | C | **A** |
| Platform uptime & on-call | I | **A/R** | I | — | I |
| Policy content accuracy | C | C | **A/R** | C | I |
| Metrics & exec reporting | **A/R** | C | C | — | I |
| Privacy & disclosure compliance | C | R | I | **A** | I |
| Agent training | C | — | **A/R** | — | I |

## 9. Risks, dependencies & mitigations

| # | Risk / dependency | Likelihood | Impact | Mitigation | Owner | Backlog |
|---|---|---|---|---|---|---|
| R1 | Wrong policy answer (hallucination) damages trust | Med | High | Exchanges escalate to humans; retrieval cites a source; 99% gate; daily QA sample; kill switch | Eng Lead | BL-01, BL-02 |
| R2 | **Dependency:** carrier API rate limit (20 req/s) throttles at peak | High (at peak) | High | Queue + retry; "label emailed within 10 min" message; request higher limit from carrier | Eng Director | BL-03 |
| R3 | Agents not ready → handle time rises | Med | Med | ADKAR plan; RC10 gate; floor champions | Support Ops | BL-06 |
| R4 | Privacy / regulatory exposure (PII, AI disclosure) | Low | High | Redaction, 6-month retention, Legal sign-off gate | Legal | BL-07, BL-08 |
| R5 | **Dependency:** LLM provider outage or model version change | Low | High | Pin model version; regression suite before any upgrade; failover to human chat | Eng | BL-10 |
| R6 | Policy content goes stale (manual weekly refresh) | Med | Med | Move ownership to Support Ops with a 24 h workflow | Support Ops | BL-05 |
| R7 | Run cost higher than forecast at 100% traffic | Med | Low | Cost dashboard; caching; route simple tracking lookups without the LLM | Eng | BL-09 |
| R8 | Spanish-speaking customers get a worse experience | High | Med | Route to bilingual agents; Spanish as top post-launch item | PM | BL-04 |

## 10. Prioritized next backlog

Ranked by **value × risk reduction ÷ effort**, with launch blockers first. Effort: S < 1 wk, M 1–3 wks, L > 3 wks.

| Rank | ID | Item | Why it matters (value) | Effort | Priority | Owner |
|---|---|---|---|---|---|---|
| 1 | BL-01 | Raise accuracy to ≥ 99%: fix retrieval for exchange/edge-case policies; expand the golden test set | Trust; release criterion RC1 | M | P0 | Eng Lead |
| 2 | BL-03 | Carrier API queue/retry + higher rate limit | Protects the core money-saving action at peak | M | P0 | Eng Director |
| 3 | BL-10 | On-call, runbook, alerts, kill-switch game day | Can't operate safely without it (RC9) | S | P0 | Eng Director |
| 4 | BL-06 | Agent training + certification on the handoff console | Agent readiness (RC10) | M | P0 | Support Ops |
| 5 | BL-07 | Legal sign-off on AI disclosure | Compliance gate (RC7) | S | P0 | Legal |
| 6 | BL-13 | Fix app→web handoff context loss | 3% of escalations lose context (RC4) | S | P1 | Eng |
| 7 | BL-08 | 6-month retention + PII redaction check | Privacy (RC6) | S | P1 | Eng Lead |
| 8 | BL-14 | Load test at 2× peak | Release criterion RC5 | S | P1 | Eng |
| 9 | BL-02 | QA analyst + daily audit workflow (funded) | Keeps accuracy visible and improving | S | P1 | Support Ops |
| 10 | BL-11 | HEART dashboard + weekly exec update | Lets leadership govern the rollout | S | P1 | PM |
| 11 | BL-09 | Run-cost model + cost controls | Protects the net savings case | S | P1 | PM |
| 12 | BL-05 | Policy content editing workflow for Support Ops | Removes a manual step; keeps content current | M | P1 | PM + Support Ops |
| 13 | BL-04 | Spanish language support | ~14% of chat volume; fairness | L | P1 (post-GA) | PM |
| 14 | BL-15 | Exchanges / size swaps | Next-biggest intent after returns (~9% of contacts) | L | P2 | PM |
| 15 | BL-12 | Rule-based approval for $200–$500 refunds | More savings, but financial risk; revisit with GA data | M | P2 (parked) | PM |
