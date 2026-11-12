# 05 – Executive Summary: Returns & Orders Assistant

## Recommendation: 🟡 LAUNCH WITH CONDITIONS
Phased launch starting **Jan 12** (5% → 25% → 50% → 100%). Moving past 25% traffic requires the conditions below to be met.

> Sample data for the fictional Northwind Outfitters scenario.

---

### The problem
62% of support contacts are "where is my order?" or "how do I return this?" Customers wait a median of **4 h 10 min** by email for answers our systems already have. Volume grows ~18% a year while headcount stays flat.

### The product
An AI chat assistant that **resolves order-status and standard-return requests end to end**: it verifies identity, checks the order and policy, and issues the return label. Everything else goes to a human agent along with the full conversation.

### Evidence (6-week pilot, 5% of traffic, 8,412 conversations)

| Metric | Target | Result |
|---|---|---|
| Containment (in-scope) | ≥ 35% | ✅ **41%** |
| CSAT (contained chats) | ≥ 4.2 | ✅ **4.3** (human chat: 4.1) |
| Time to resolution | < 3 min | ✅ **1 m 50 s** (email: 4 h+) |
| Answer accuracy (audited) | ≥ 99% | 🟡 **98.2%** |
| Handoff keeps context | 100% | 🟡 **97%** |

### Value
**≈ $410K a year gross / ≈ $350K net** after ≈ $58K run cost, at 35% containment and full traffic. Sensitivity range: $293K–$527K gross. *(Assumption: $2.25 saved per contained contact, 520K in-scope contacts a year.)*

### Why not "ready to launch"?
| | Gap | Fix | Gate |
|---|---|---|---|
| 1 | Accuracy 98.2%; errors mostly on exchange-policy edge cases | Exchanges go to humans; retrieval fixes; re-audit | ≥ 99% before passing 25% |
| 2 | Carrier API limit could throttle labels at peak | Queue + retry; higher limit | Load test at 2× peak |
| 3 | Not yet operationally ready (on-call, agent training, Legal disclosure sign-off) | Runbook + game day; ADKAR training plan; Legal review | All closed before Jan 12 |

### Why not "not ready"?
The core workflow works with real integrations and beats the human baseline on speed and satisfaction. The remaining gaps are **bounded, owned and scheduled**. A kill switch can roll traffic back within 15 minutes.

### Decisions made in the workshop
1. ✅ Phased launch with conditions approved (VP CX)
2. ✅ 1 QA analyst funded for 90 days (≈ $22K)
3. ✅ Support Ops owns policy content; Engineering owns the platform

### Top 5 next actions (all launch-blocking)
| Action | Owner | Due |
|---|---|---|
| Raise accuracy to ≥ 99% | Eng Lead | Before 25% gate |
| Carrier API queue/retry + load test | Eng Director | Jan 9 |
| On-call, runbook, kill-switch game day | Eng Director | Jan 9 |
| Train + certify ≥ 90% of Tier-1 agents | Support Ops | Jan 9 |
| Legal sign-off on AI disclosure | Legal | Dec 1 |

**Success at 90 days** (Google HEART): CSAT ≥ 4.2 · containment ≥ 35% · repeat contact ≤ 8% · accuracy ≥ 99% · net savings on track for ≥ $350K a year.

Details: [Productization Plan](04-productization-plan.md) · [Feedback Log](03-stakeholder-feedback-log.md) · [Demo Script](01-demo-script.md)
