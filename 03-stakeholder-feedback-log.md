# 03 – Stakeholder Feedback Log

**Session:** Executive demo + productization workshop | **Date:** `[YYYY-MM-DD]` | **Facilitator:** `[Name]` | **Scribe:** `[Name]`

> ⚠️ **Sample entries.** The rows below are illustrative, written for the fictional Northwind scenario to show the expected level of detail. Replace them with what is actually said in your session.

## Attendees

| Role | Name | Stake in the decision |
|---|---|---|
| VP Customer Experience (executive sponsor) | `[Name]` | Final go/no-go; owns CSAT targets |
| Finance (CFO delegate) | `[Name]` | Cost savings, ongoing run cost |
| Head of Support Operations | `[Name]` | Agent workflows, staffing, policy content |
| Legal / Privacy lead | `[Name]` | Data handling, AI disclosure, refund commitments |
| Engineering Director | `[Name]` | Scalability, on-call, technical risk |
| Product Manager (presenter) | `[Name]` | Roadmap, backlog |

## Readiness gut check (workshop step 1)

| Stakeholder | Score (1–5) | Biggest concern |
|---|---|---|
| VP CX | 4 | Wrong answers damaging trust during the January returns surge |
| Finance | 4 | Model and API run cost at 100% traffic |
| Support Ops | 3 | Agents not trained on the new handoff console |
| Legal / Privacy | 3 | AI disclosure wording; transcript retention |
| Engineering | 3 | Carrier API limit; no load test at full traffic yet |
| **Average** | **3.4** | → supports "launch with conditions," not unconditional launch |

## Feedback log

**Types:** Q = Question · O = Objection · D = Decision · I = Idea/Request · A = Action
**Priority:** P0 = launch-blocking · P1 = must fix before passing 25% traffic · P2 = post-launch

| # | Type | From | Feedback (summarized) | Response / outcome | Action → Backlog ID | Owner | Due | Priority | Status |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Q | Finance | What does it cost to run at 100% traffic? Does the $410K saving survive that? | Estimated run cost ≈ $58K/yr (model + hosting), so net ≈ $350K. Finance asked for this in writing. | Add run-cost model to plan → **BL-09** | PM | +1 wk | P1 | Open |
| 2 | O | VP CX | 98.2% accuracy isn't good enough for a refund-related flow. One wrong policy answer can go viral. | Agreed. Accuracy ≥ 99% made a **release criterion**. Exchange-policy questions escalate to humans until fixed. | **BL-01**, **BL-02** | Eng Lead | Before GA | P0 | In progress |
| 3 | O | Engineering | Carrier API limit (20 requests/sec) will throttle at holiday-level peaks. | Mitigation: queue + retry with "label emailed within 10 min" messaging; ask the carrier for a higher limit. | **BL-03** | Eng Director | Before GA | P0 | Open |
| 4 | Q | Legal | Do customers know they're talking to an AI? | Yes, the disclosure banner is shown at the start of chat. Legal to approve final wording. | Legal sign-off on wording → **BL-07** | Legal | +2 wk | P0 | Open |
| 5 | I | Legal | Shorten transcript retention from 12 to 6 months, and redact PII in stored logs. | Accepted. PII redaction is already in logs; retention change is a config change. | **BL-08** | Eng Lead | Before GA | P1 | Open |
| 6 | O | Support Ops | Agents haven't used the handoff console; a launch without training will hurt handle time. | Added an ADKAR-based enablement plan; training happens before GA, with champions per shift. | **BL-06** | Support Ops | Before GA | P0 | Open |
| 7 | I | VP CX | Spanish speakers are ~14% of chat. Can we include them at launch? | Not at GA. Spanish is the top post-launch item; Spanish chats go to bilingual agents for now. | **BL-04** | PM | GA + 6 wk | P1 | Planned |
| 8 | Q | Support Ops | Who updates the bot when the returns policy changes? | Today: engineering, manually, weekly (🖐️). Proposed: Support Ops owns content through a simple editing workflow. | **BL-05** | Support Ops + PM | GA + 4 wk | P1 | Open |
| 9 | I | Finance | Automate approval for $200–$500 refunds under rules, to unlock more savings. | Valuable but it adds financial risk. Parked until 60 days of GA data exist. | **BL-12** | PM | Revisit Q2 | P2 | Parked |
| 10 | O | Engineering | No one is on call for the assistant after hours. | Add it to the existing platform on-call rotation, with runbook and alerting. | **BL-10** | Eng Director | Before GA | P0 | Open |
| 11 | I | VP CX | Weekly one-page metrics update to the exec team during rollout. | Accepted. HEART dashboard + weekly email. | **BL-11** | PM | GA | P1 | Open |
| 12 | **D** | **VP CX (sponsor)** | **Decision: approve phased launch with conditions.** 5% → 25% → 50% → 100%, starting Jan 12. Moving past 25% requires all P0 items closed and the release criteria in the Productization Plan §3 met. | Recorded. Go/no-go check at each phase gate. | — | VP CX | Jan 12 | — | **Decided** |
| 13 | **D** | VP CX + Finance | **Decision:** fund 1 QA analyst for 90 days (≈ $22K). | Approved. | Hire/assign → BL-02 | Support Ops | +2 wk | — | **Decided** |
| 14 | **D** | All | **Decision:** Support Ops owns policy content after launch; Engineering owns the platform. | Recorded in the RACI ([04 §8](04-productization-plan.md#8-support--operations)). | BL-05 | — | — | — | **Decided** |

## Summary of outcomes

- **3 decisions** made (launch with conditions, QA funding, content ownership)
- **5 P0 launch blockers** identified: BL-01 accuracy, BL-03 carrier API, BL-06 agent training, BL-07 AI disclosure sign-off, BL-10 on-call
- **1 item parked** with a revisit date (BL-12 automated refunds)
- Every row maps to a backlog item in the [Productization Plan §10](04-productization-plan.md#10-prioritized-next-backlog)

## Follow-ups sent

- [ ] Recap email with decisions and owners sent to attendees within 24 h
- [ ] Run-cost model sent to Finance (row 1)
- [ ] Phase-gate review meetings booked
