# Strategy Memo: Scaling the Enterprise AI Assistant from Pilot to Product

**To:** Executive Steering Committee
**From:** AI Product & Transformation Office
**Date:** November 12, 2026
**Subject:** Stakeholder, adoption and productization strategy for enterprise rollout

---

## Executive Summary

The AI Assistant pilot (about 400 users across Finance Operations, Customer Service and Sales Support, running 12 weeks) has shown it works technically. Task cycle time fell and early users rate it well. Adoption, though, is uneven: weekly active use is strong in Customer Service and weak in Finance, where the workflows were never redesigned around the tool. Security sign-off is conditional, and no one owns funding beyond the pilot.

The problem is not the technology. It is ownership, governance and change management. We recommend three moves:

1. **Treat the assistant as an internal product.** Give it a named product owner, a defined core offering and a showback funding model.
2. **Make governance an enabler, not a gate.** Co-design a tiered data and use-case policy with IT Security, so low-risk use cases go live in days rather than months.
3. **Run adoption as a measured change program.** Use a single scorecard reviewed monthly, with go/no-go thresholds that decide each expansion wave.

If we approve this, the 90-day plan below moves us from 400 pilot users to roughly 2,500 governed users in three business units, with value tracked against a baseline.

*Planning assumptions: pilot figures are illustrative and should be replaced with actual telemetry before the review.*

---

## 1. Stakeholder Map

Stakeholders were assessed on influence (ability to block or accelerate) and interest (how much the outcome affects them), using PMI's salience-based stakeholder analysis.

| Stakeholder | Influence | Interest | Expected benefits | Key concerns | Likely resistance | Strategy |
|---|---|---|---|---|---|---|
| Executive sponsor (COO) | High | High | Measurable ROI, productivity story for the board | Spending without proven value | Low; will withdraw support if ROI stays vague | **Manage closely** |
| CFO / Finance leadership | High | Medium | Cost avoidance, predictable spend | Unbounded usage costs, soft ROI claims | Medium: may block funding | **Keep satisfied** with hard-dollar metrics |
| CIO / IT Platform | High | High | Standard, reusable platform; fewer shadow-AI tools | Support burden, integration debt | Medium: "not another platform to run" | **Manage closely**: co-own the architecture |
| CISO / Security, Privacy & Legal | High | Medium | Controlled AI usage, audit trail | Data leakage, model risk, regulatory exposure | **High**: can halt the rollout | **Keep satisfied**: co-design the policy early |
| Business unit heads | Medium–High | High | Throughput, better service levels | Disruption to targets during transition | Medium: passive non-adoption | **Manage closely**: shared targets |
| Frontline managers | Medium | High | Less rework, faster onboarding of staff | Time lost to training, team performance dips | Medium–High: the "middle layer" stall | **Keep informed + equip** as change agents |
| Frontline users | Low (individually), High (collectively) | High | Less tedious work, faster answers | Job security, accuracy, extra steps | **High**: workarounds, low use | **Involve**: champions, feedback loops |
| HR & works council / employee reps | Medium | Medium | Responsible workforce transition | Role changes, monitoring of staff | Medium | **Consult** on usage-data policy |
| Product & engineering leaders | Medium | High | Reusable operating model and patterns | Scope creep, bespoke requests | Low | **Partner**: own the roadmap |
| Vendor / model provider | Low | High | Account expansion | Contract terms, data restrictions | Low | **Monitor** through vendor management |

**Highest-risk relationships:** Security (they can veto) and frontline managers (they can quietly stall adoption). Both get dedicated engagement below.

---

## 2. Engagement Plan

| Stakeholder | Communication approach | Owner | Cadence | Escalation path | Success indicators |
|---|---|---|---|---|---|
| Executive sponsor & steering committee | Scorecard review; decisions log | Product Owner | Monthly (biweekly in the first 90 days) | Direct to COO | Expansion decisions made on time; funding approved |
| CFO / Finance | Value realization report, cost-per-user trend | Product Owner + FP&A partner | Monthly | Steering committee | Showback model accepted; FY27 budget line approved |
| CIO / IT | Architecture review board; joint backlog | Platform Lead | Biweekly | CIO → Steering committee | Platform runbook signed off; incidents below SLA threshold |
| CISO, Privacy, Legal | AI risk working group; co-authored policy | Governance Lead | Weekly until policy signed, then monthly | CISO → Steering committee | Tiered policy approved by day 30; zero critical findings |
| BU heads | Business case per unit; adoption targets in their own OKRs | Change Lead | Monthly | BU head → Sponsor | Targets accepted; named BU adoption lead |
| Frontline managers | Manager toolkit, team huddle scripts, dashboards | Change Lead | Biweekly | BU adoption lead | ≥80% of managers trained; team usage trending up |
| Frontline users | Champions network, in-tool tips, open office hours, "you said, we did" updates | Champions Lead | Weekly | Champion → Product backlog triage | Satisfaction ≥4.0/5; feedback closed within 10 days |
| HR & employee reps | Consultation on role impact and usage-data handling | HR Business Partner | Monthly | CHRO | Agreed usage-data charter; no formal grievances |
| Product & engineering | Sprint reviews, roadmap planning | Product Owner | Biweekly | CIO | Roadmap delivered at ≥80% predictability |

**Escalation principle:** resolve issues at the lowest level within five business days. Anything blocking a go/no-go gate goes straight to the steering committee, which meets on demand within 72 hours.

**Narrative:** Following Kotter's model, every message carries one consistent "why now": *give our people back time for higher-value work, safely.* Leadership communications state openly that the assistant augments roles. Any workforce changes go through HR consultation, not through the tool rollout.

---

## 3. Change and Adoption Scorecard

The scorecard combines Prosci's three levels of change metrics: organizational performance, individual performance and change management performance. It is reviewed monthly, and each expansion wave needs the **gate** thresholds met.

| Dimension | Metric | Data source | Pilot baseline* | 90-day target | Gate threshold |
|---|---|---|---|---|---|
| **Readiness** | % of target BU staff scoring "ready" (awareness + desire) | Pre-launch pulse survey | 52% | 70% | ≥65% before a BU launches |
| **Training** | % of users who completed the core course (45 min) before getting access | LMS | 61% | 90% | ≥85% |
| **Activation** | % of provisioned users with a first meaningful session within 14 days | Product telemetry | 58% | 80% | ≥75% |
| **Usage** | Weekly active users ÷ provisioned users | Telemetry | 41% | 60% | ≥55% |
| **Feature adoption** | % of WAU using ≥2 core workflows (summarize, draft, search) | Telemetry | 28% | 50% | ≥40% |
| **Proficiency** | % passing a scenario-based skills check; output acceptance rate | Assessment + telemetry | 45% / 62% | 70% / 75% | ≥60% / ≥70% |
| **Satisfaction** | User CSAT (1–5) and eNPS-style "would recommend" | In-tool survey | 3.8 / +12 | 4.2 / +30 | ≥4.0 |
| **Support volume** | Tickets per 100 active users per month; % resolved at tier 1 | ITSM | 9.5 / 55% | ≤5 / 75% | ≤7 |
| **Process compliance** | % of usage within approved use cases; policy incidents | DLP logs, audit | 94% / 2 | 99% / 0 critical | 0 critical incidents |
| **Realized business value** | Hours saved per user per week (validated sample); cycle-time change on target processes; $ value vs. run cost | Time studies, process KPIs, FP&A | 1.6 h; −18% | 2.5 h; −25%; ROI ≥2:1 run-rate | Value ≥ run cost by end of wave 1 |

\*Illustrative baselines; replace them with actual pilot data.

**How to read the scorecard.** Leading indicators (readiness, training, activation) predict lagging ones (usage, proficiency, value). If usage lags while training is high, the workflow needs redesign, not more training. That is the Finance pilot's issue today. Value claims are validated through controlled time studies, not self-reported surveys alone, so they hold up with the CFO.

---

## 4. Productization Strategy

**Target users.** The primary users are knowledge workers in high-volume, text-heavy processes: service agents, finance analysts and sales support. Secondary users are managers who need summaries and reporting. Builders (citizen developers) come later, through a governed extension layer.

**Value proposition.** *"Trusted answers and first drafts inside the tools you already use, so you spend less time searching and rewriting and more time on judgment work, inside company guardrails."*

**MVP / core offering (v1.0).**
- Secure chat assistant grounded in approved enterprise knowledge sources
- Three certified workflows: document summarization, guided drafting (emails, case notes) and policy/knowledge search with citations
- Integration with the collaboration suite and the CRM
- An admin console covering access, usage analytics and audit logs

**Service boundaries.**

| In scope (platform team provides) | Out of scope (BU or later roadmap) |
|---|---|
| Core assistant, certified workflows, approved connectors | Bespoke BU-specific models or fine-tuning |
| Identity, access, logging, DLP controls | Autonomous agents acting on systems of record (until v2 governance) |
| Standard onboarding, training, tier-2/3 support | BU process redesign (BU owns it, with change-team support) |
| Use-case intake and risk tiering | Any use of customer PII outside an approved tier |

**Onboarding.** Each BU joins through a repeatable "launch kit": readiness survey, then manager briefing, then training, then access provisioning, then a 30-day hypercare period with embedded champions (1 per 25 users). Access is granted only after training is complete.

**Support model.** Tier 0 covers in-tool help and a prompt library. Tier 1 is the service desk, using scripted runbooks. Tier 2 is the platform team. Tier 3 is the vendor. Champions collect feedback, which is triaged weekly into the product backlog.

**Governance.**
- An AI Risk Working Group (Security, Privacy, Legal, Product) maintains a **three-tier use-case policy**. Tier 1 (internal, low-risk) is self-service. Tier 2 (confidential data) needs a lightweight review within 10 days. Tier 3 (customer-impacting or regulated) needs a full assessment.
- Quarterly model and output quality reviews, plus a published responsible-use standard.
- A usage-data charter agreed with HR: telemetry is used for product improvement, not individual performance management.

**Funding / pricing logic.** Year 1 is centrally funded. That covers the platform, governance and the core team, at roughly the cost of the pilot run-rate scaled to 2,500 users. From Year 2, the model moves to **showback, then chargeback** on a per-active-user rate. Active users are what we charge on, which rewards adoption and avoids paying for unused licenses. Premium workflows or extra connectors are funded by the requesting BU. Expansion is approved only when validated value is at least twice the run cost.

**Roadmap.**

| Horizon | Release | Focus |
|---|---|---|
| Now (0–3 months) | v1.0 Core | Harden the MVP, tiered governance, launch kit, wave 1 (3 BUs) |
| Next (3–9 months) | v1.5 Scale | 3 more certified workflows, ERP connector, self-service Tier 1 use-case intake, chargeback pilot |
| Later (9–18 months) | v2.0 Platform | Governed extension layer for builders, supervised agentic workflows, multi-language support |

**Operational risks and mitigations.**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Data leakage or policy breach | Medium | High | DLP controls, tiered policy, red-team testing before each wave |
| Inaccurate outputs erode trust | Medium | High | Grounded answers with citations, feedback loop, quality reviews |
| Usage costs outrun value | Medium | Medium | Usage caps, cost dashboard, value gate before each wave |
| Middle-manager stall | High | Medium | Manager toolkit, adoption targets in BU OKRs |
| Vendor lock-in or price changes | Low | High | Abstraction layer, contract exit terms, second-source evaluation |
| Platform team overloaded by bespoke requests | High | Medium | Clear service boundaries, intake prioritization by value score |

---

## 5. Prioritized 90-Day Action Plan

| # | Priority action | Owner | Days | Output / exit criterion |
|---|---|---|---|---|
| **Days 1–30: Mobilize and govern** |||||
| 1 | Appoint a Product Owner; charter the steering committee and decision rights | COO | 1–10 | Signed charter, RACI |
| 2 | Co-author and approve the three-tier AI use-case policy and usage-data charter | Governance Lead + CISO + HR | 1–30 | Policy approved; Security sign-off made unconditional |
| 3 | Establish the scorecard baseline from pilot telemetry; run a time study in Finance and Customer Service | Product Analyst + FP&A | 5–30 | Validated baseline; live dashboard |
| 4 | Diagnose the Finance adoption gap; redesign 2 workflows with users | Change Lead + Finance BU lead | 10–30 | Redesigned workflows; retest plan |
| **Days 31–60: Productize and prepare** |||||
| 5 | Freeze the v1.0 scope; complete hardening, admin console and support runbooks | Platform Lead | 31–60 | Production-readiness review passed |
| 6 | Build the launch kit and train managers in the wave 1 BUs | Change Lead | 31–55 | ≥80% of managers trained |
| 7 | Recruit and enable the champions network (1 per 25 users) | Champions Lead | 35–60 | ~100 champions active |
| 8 | Get the showback model and FY27 funding approved | Product Owner + CFO office | 40–60 | Funding decision recorded |
| **Days 61–90: Scale wave 1 and prove value** |||||
| 9 | Go/no-go gate review against scorecard thresholds | Steering committee | 61–65 | Documented decision |
| 10 | Launch wave 1 (about 2,100 new users across 3 BUs) with 30-day hypercare | Product Owner | 65–90 | Activation ≥75% |
| 11 | Publish the first value realization report and "you said, we did" update | Product Owner | 85–90 | Report to the steering committee |
| 12 | Approve the v1.5 roadmap and wave 2 criteria | Steering committee | 88–90 | Roadmap and wave 2 plan approved |

**Decisions requested today:**
1. Approve the internal-product operating model and name a Product Owner.
2. Mandate the joint Security–Product governance working group with a 30-day deadline.
3. Approve Year 1 central funding, with expansion tied to the scorecard value gate.

---

### References
- PMI, *Stakeholder Analysis: A Pivotal Practice of Successful Projects*
- Prosci, *Metrics for Measuring Change Management*
- Kotter, *The 8-Step Process for Leading Change*
- Harvard DCE, *What Does the Product Management Lifecycle Look Like?*
- Atlassian, *Product Development Lifecycle*
