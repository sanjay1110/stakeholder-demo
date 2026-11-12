# 01 – Executive Demo Script & Deck Outline

**Length:** 7 minutes demo + 15 minutes workshop | **Audience:** VP Customer Experience (sponsor), CFO delegate, Head of Support Operations, Legal/Privacy lead, Engineering Director
**Format:** Live product in the staging environment, with a recorded backup ([02](02-demo-recording.md))
**Demo principle:** *Show the one workflow that creates most of the value, using real integrations. Don't tour every feature.* (SAFe System Demo; Scrum Sprint Review)

> All metrics are **sample pilot data** for this lab scenario.

---

## Run of show

| Time | Slide / Screen | Purpose |
|---|---|---|
| 0:00–1:00 | Slides 1–2 | Problem, users, goal, value |
| 1:00–1:30 | Slide 3 | What you're about to see, and the decision we need |
| 1:30–4:30 | **Live product** | One core workflow, plus one failure/escalation path |
| 4:30–6:00 | Slides 4–5 | Evidence, plus what is complete / incomplete / risky / manual |
| 6:00–7:00 | Slide 6 | Recommendation and the asks |
| 7:00–22:00 | Slide 7 | Productization workshop (facilitated) |

---

## Slide 1 – The problem (0:00–0:30)

**On slide:**
- **62%** of support contacts are "Where is my order?" or "How do I return this?"
- Median first response time is **4 h 10 min** by email and **9 min** in live-chat queues at peak
- Contact volume grows **~18% a year**; support headcount is flat

**Say:**
> "Most of what our customers contact us about is two questions: where's my order, and how do I return it. They wait hours for answers that are already in our systems. Our support team spends most of its day copying tracking numbers instead of solving the hard problems."

## Slide 2 – Users, goal, measurable value (0:30–1:00)

**On slide:**

| | |
|---|---|
| **Primary users** | Online customers with an existing order (web and app chat) |
| **Secondary users** | Tier-1 support agents, who receive escalations with full context |
| **Product goal** | Resolve order-status and standard-return requests instantly and accurately, and hand everything else to a human with context |
| **Target value** | Contain **≥35%** of in-scope conversations · CSAT **≥ 4.2/5** · save **≈ $410K a year** in handling cost at full traffic |

**Value math (assumption, shown in the appendix):** 520K in-scope contacts a year × 35% containment × $2.25 saved per contact ≈ **$410K**.

## Slide 3 – What you'll see and the decision we need (1:00–1:30)

**Say:**
> "I'll show you one real conversation, end to end, against our live order and carrier systems. Then I'll show you what happens when the assistant *shouldn't* answer. At the end I'll ask you for one decision: do we launch to all customers in January with the conditions on slide 6?"

---

## Live demo (1:30–4:30)

### Scenario A: the happy path (≈ 2 min)
Persona: **Maya**, who ordered boots 6 days ago. They've arrived and don't fit.

| Step | Action in product | Point to make | Status |
|---|---|---|---|
| 1 | Maya opens chat and types *"my boots don't fit, can I send them back?"* | Natural language, no menu tree | ✅ |
| 2 | Assistant verifies her identity with email + order number | Identity check before any account data is shown | ✅ |
| 3 | Assistant pulls the order, confirms the item is inside the 30-day window, and explains the policy in one sentence | Answer is **grounded** in the order system and the policy doc, with the source shown | ✅ |
| 4 | Maya picks "Refund"; the assistant generates a prepaid return label via the carrier API | **Real action**, not just an answer; this is where the cost saving comes from | ✅ (🔴 carrier API rate limit, see slide 5) |
| 5 | Confirmation email arrives in Maya's inbox (shown on a second screen) | Full loop closed in **~90 seconds** compared with the 4-hour email baseline | ✅ |

### Scenario B: the safe failure (≈ 1 min)
Maya asks: *"The other pair arrived damaged, I want a refund and compensation for the hassle."*

| Step | Action | Point to make | Status |
|---|---|---|---|
| 1 | Assistant recognizes damage + compensation as **out of policy scope** | Knows its limits; doesn't make up policy | ✅ |
| 2 | Hands off to a live agent; the agent console shows the transcript, order and intent summary | Customer never repeats herself | ✅ |
| 3 | (Narrate) Refunds over $200 are approved by a team lead today | Explain this honestly | 🖐️ Manual |

**Presenter fallback:** If staging fails, switch to the recording at timestamp 1:30 ([02](02-demo-recording.md)) and keep narrating. Don't troubleshoot live.

---

## Slide 4 – Evidence from the pilot (4:30–5:15)

6-week pilot · 5% of chat traffic · **8,412 conversations** *(sample data)*

| Metric | Target | Pilot result | |
|---|---|---|---|
| Containment (in-scope intents) | ≥ 35% | **41%** | ✅ |
| CSAT (contained conversations) | ≥ 4.2 | **4.3** (human chat baseline 4.1) | ✅ |
| Median time to resolution | < 3 min | **1 min 50 s** | ✅ |
| Answer accuracy (audited sample, n = 500) | ≥ 99% | **98.2%** | 🟡 |
| Escalation with full context | 100% | **97%** (3% lost context on app→web switch) | 🟡 |
| Spanish-language conversations | Supported | Not yet supported | 🟡 |

## Slide 5 – Readiness: honest status (5:15–6:00)

| ✅ Complete | 🟡 Incomplete | 🔴 Risky | 🖐️ Still manual |
|---|---|---|---|
| Order status & tracking | Spanish language | 1.8% inaccurate answers (mostly exchange policy edge cases) | Refund approval over $200 |
| Standard returns + label generation | Exchanges (size swap) | Carrier API rate limit at peak traffic | Weekly policy-doc refresh into the knowledge base |
| Identity verification | Accessibility audit (WCAG 2.2 AA) | Holiday-peak load not yet tested at 100% traffic | Daily QA review of 50 transcripts |
| Human handoff with context | Analytics dashboard (partial) | | |

## Slide 6 – Recommendation and the asks (6:00–7:00)

**Recommendation: 🟡 Launch with conditions.** Phased general availability (GA) starting **Jan 12**, after the holiday code freeze.

**Conditions (all must be met before we pass 25% of traffic):**
1. Answer accuracy ≥ 99% on a fresh 500-conversation audit
2. Carrier API capacity raised or a queue/retry in place; load test passed at 2× forecast peak
3. App→web handoff bug fixed (context kept in 100% of a 200-conversation test)

**Asks today:**
1. **Decision:** approve phased launch with these conditions
2. **Funding:** 1 additional QA analyst for 90 days (≈ $22K)
3. **Owner:** Support Operations to own policy-content updates after launch

## Slide 7 – Workshop: what must be true before release? (7:00–22:00)

Facilitation (Sprint Review style: *inspect the increment, adapt the backlog*):

1. **(3 min) Gut check:** each stakeholder rates readiness 1–5 and names their single biggest concern
2. **(6 min) Go through the 🟡/🔴/🖐️ items:** for each one, is it *launch-blocking*, *launch-with-mitigation*, or *post-launch*?
3. **(4 min) Confirm metrics:** do the HEART metrics and targets ([04 §6](04-productization-plan.md#6-adoption--success-metrics-google-heart)) reflect what you'd judge success on?
4. **(2 min) Decision and owners:** record the decision and assign owners in the [feedback log](03-stakeholder-feedback-log.md)

**Scribe rule:** every question, objection or idea gets a row in the feedback log *in the room*, with a type (Question / Objection / Decision / Idea / Action) and an owner.

---

## Appendix slides (only if asked)

- **A1 – Value model:** 520K in-scope contacts × 35% containment × $2.25 fully loaded cost saved per contact. Sensitivity: at 25% containment, ≈ $293K; at 45%, ≈ $527K.
- **A2 – Architecture:** chat widget → orchestration service → LLM with retrieval over the policy knowledge base → tool calls (Order API, Carrier API, CRM) → agent console handoff
- **A3 – Guardrails:** identity check before any account data; no free-form refund promises; PII redaction in logs; topic allow-list; confidence-based escalation
- **A4 – Accuracy audit method:** stratified random sample by intent; two reviewers; disagreements settled by a team lead
