# Executive Stakeholder Demo & Productization Workshop

**Product:** *Returns & Orders Assistant (ROA)*, a customer-facing AI chat assistant for **Northwind Outfitters** (a fictional online retailer)
**Decision sought:** Should ROA move from pilot to a productized release?
**Recommendation:** 🟡 **Launch with conditions.** See [Executive Summary](05-executive-summary.md).

> ⚠️ **Note on data:** Northwind Outfitters and its pilot are a fictional scenario made up for this lab. Every metric, quote and feedback entry is **sample data**, and is marked that way where it appears. Replace it with your own project's evidence before you present.

---

## How to review (≈15 minutes)

| Order | Artifact | What it answers | Time |
|---|---|---|---|
| 1 | [05 – Executive Summary](05-executive-summary.md) | One page: value, evidence, risks, recommendation | 2 min |
| 2 | [01 – Demo Script & Deck Outline](01-demo-script.md) | What we showed in the 7-minute demo, and why | 4 min |
| 3 | [02 – Demo Recording / Presentation Artifact](02-demo-recording.md) | Link to the recording and slides | 7 min (optional) |
| 4 | [03 – Stakeholder Feedback Log](03-stakeholder-feedback-log.md) | Questions, objections and decisions, with each one turned into an action | 3 min |
| 5 | [04 – Productization Plan](04-productization-plan.md) | Launch scope, release criteria, adoption, support, operations, risks, backlog | 5 min |

**If you only have 2 minutes**, read the Executive Summary.

## Repository structure

```
.
├── README.md                        ← you are here
├── 01-demo-script.md                ← 7-minute executive demo script + slide outline
├── 02-demo-recording.md             ← recording link, slide link, run-of-show
├── 03-stakeholder-feedback-log.md   ← captured feedback → actions → owners
├── 04-productization-plan.md        ← full launch / adoption / ops plan
└── 05-executive-summary.md          ← one-page recommendation
```

## Frameworks used and where

| Framework | Used for | Where |
|---|---|---|
| [Scrum Guide: Sprint Review](https://scrumguides.org/scrum-guide.html) | A working session where stakeholders inspect the outcome and adapt the backlog, not a status report | Demo structure; feedback goes straight into the backlog |
| [SAFe System Demo](https://framework.scaledagile.com/system-demo/) | Demo the *integrated* end-to-end system with real data, not isolated features | Demo shows a live, integrated workflow (chat → order API → carrier API → human handoff) |
| [Google HEART](https://research.google/pubs/measuring-the-user-experience-on-a-large-scale-user-centered-metrics-for-web-applications/) | Goals → Signals → Metrics for user experience at scale | Adoption metrics in the Productization Plan §6 |
| [Prosci ADKAR](https://www.prosci.com/methodology/adkar) | Change management for the internal people affected (support agents, team leads) | Onboarding & change plan in the Productization Plan §5 |
| [Aha! Product Launch Checklist](https://www.aha.io/roadmapping/guide/release-management/what-is-a-good-product-launch-checklist) | Cross-functional launch-readiness checklist | Release readiness checklist in the Productization Plan §3 |

## Status legend used throughout

- ✅ **Complete:** built, tested and running in the pilot
- 🟡 **Incomplete:** partly built, or built but not yet at the target
- 🔴 **Risky:** works, but has a known failure mode or exposure
- 🖐️ **Manual:** a person still does this step behind the scenes
