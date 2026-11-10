# Project Clarity: Clinical Workflow Optimization Blueprint

**An AI-designed workflow cut time-on-task by 63% and would still have failed at scale — because its single biggest improvement depended on a vendor building a feature that doesn't exist yet, and nobody had started that conversation.**

This is the gap this project is actually about. Project Horizon decided *what* to build and *when*. This one asks a harder question: once you've decided to fix a workflow, how do you get 2,000 skeptical, experienced clinicians across 200 sites to actually use the fix — especially when the cleanest part of the redesign isn't something you control?

The scenario: an AI-assisted billing platform handles 85% of charge entries correctly. The other 15% require manual clinician intervention, and every site has quietly invented its own workaround for it — no shared process, inconsistent documentation, a rising modifier error rate, and mounting frustration with a tool that was supposed to reduce paperwork, not add a second undocumented job on top of it.

**[→ See the rest of the judgment calls in PROCESS.md](https://github.com/zinaleeHQ/project-clarity/blob/main/PROCESS.md)** — same kind of thinking, more of it, including why "resistant clinician" is the wrong way to describe the actual adoption problem.

> **Standardizing AI-Assisted Charge Entry Across a Distributed Healthcare Workforce**

[![Methodology](https://img.shields.io/badge/Methodology-Lean%20%7C%20DMAIC-red?style=flat-square)]()
[![Domain](https://img.shields.io/badge/Domain-Clinical%20Operations%20%7C%20Change%20Management-teal?style=flat-square)]()
[![Status](https://img.shields.io/badge/Status-Portfolio%20Simulation-orange?style=flat-square)]()

---

## ∴︎ Why This Matters Outside of Tech

Every distributed organization has a version of this problem: a central system works well most of the time, and the exceptions get handled by whoever's on shift, improvised, undocumented, different at every location. A retail chain calls it "how the Tuesday manager does returns versus the Friday one." A law firm calls it "how each paralegal formats a filing when the template doesn't quite fit." Healthcare calls it a charge entry workaround. Same structural problem, different letterhead.

What's underneath this project is a discipline built specifically for that gap — Lean process improvement, using a structure called DMAIC (Define, Measure, Analyze, Improve, Control) to make sure a fix actually gets diagnosed before it gets designed, and actually gets *sustained* after it ships instead of quietly reverting to the old workaround within a month. That last part is the piece most process fixes skip, and it's usually why they don't stick.

The technical scenario below is healthcare-specific. The underlying skill — separating "the technology is broken" from "the technology works fine but nobody standardized what happens at the edges" — is the same skill a legal firm's operations lead needs when every paralegal's workaround has become five different processes lumped under one name.

---

## The Operational Challenge

Horizon scored Clinician Workflow Optimization as a sprint-ready epic. This project is what "optimization" actually meant once the sprint started: 2,000+ clinicians, 200+ sites, and the 15% of charge entries the AI platform can't handle cleanly on its own — each site having quietly built its own answer to what happens next.

The technology isn't the problem here. It works. What's missing is standardization, and that's a different toolkit than a product roadmap — this project documents an AI-assisted Lean DMAIC analysis of the manual charge entry workflow, from current-state mapping through a deployable future-state procedure, built against the real operational constraints of a workforce that can't be pulled into a training room.

| Phase | Question | Portfolio Artifact |
|---|---|---|
| **Define** | What is the problem, and who does it affect? | Friction inventory · 5 clinician archetypes |
| **Measure** | Where exactly is the time and waste going? | Current-state workflow · 14-step time-on-task map |
| **Analyze** | What's actually causing it? | Lean 8 Wastes classification |
| **Improve** | What does the fixed process look like? | Future-state SOP · embedded decision tree |
| **Control** | How does the improvement survive contact with 200 sites? | Phased rollout plan · adoption metrics |

---

## ⎔︎ What Had to Be True Before Any Redesign Started

Three inputs shaped this analysis, and none of them look alike, which is deliberate — a friction inventory built from five uniform profiles would have missed the actual problem.

The current-state workflow is a 14-step map of the manual charge entry process, timed step by step, including the four points where clinicians and their staff are currently improvising and the handoffs generating the most error.

The friction inventory is where it gets specific: five clinician archetypes, not one generic "clinician" persona, because a high-volume urban hospitalist and a rural provider covering three sites for one weekend a month have almost nothing in common in terms of workflow pressure — and a veteran provider's skepticism about 18 years of EHR company broken promises of "less work, less clicks" doesn't look anything like a new hire's confusion. Designing for the median across those five means designing for none of them particularly well.

And eight process constraints govern what the redesign is allowed to do at all — a 2-click friction cap inherited from Horizon, EMR neutrality (Epic and Cerner have to work identically, not "close enough"), a genuinely hard zero-training-budget rule, and non-negotiable safety rules for high-risk cases. That training-budget constraint turned out to matter more than any other single design principle: you cannot deliver live training to 2,000 people across 200 sites, so every fix has to be self-evident from the workflow itself, or it doesn't survive contact with reality.

---

## ⚙︎ How the Analysis Engine Works

The prompt (`/prompts/process-analysis-prompt.md`) can't propose a future-state workflow until the waste classification is fully done — that ordering is deliberate, and it's the same principle Horizon used for constraint filtering. The most common failure in process redesign is jumping straight to a fix before diagnosing the actual cause, and you end up with a workflow that *looks* cleaner without addressing what was actually driving the waste.

Here's a concrete version of that trap: the obvious fix for the modifier code lookup problem (2.4 minutes per case, on average) is embedding a reference list directly in the platform screen. But the waste analysis surfaces something the obvious fix misses — the real issue isn't a missing reference, it's that clinicians don't trust the platform's AI-suggested code enough to accept it without checking it themselves. A reference list doesn't fix a trust problem. A visible confidence score does. You only get to that answer by doing the diagnosis first, not by skipping to the fix that looks right.

---

## The Output: Before and After

| Waste Type | Current-State Impact | Frequency |
|---|---|---|
| **Waiting** | Avg 2.4 min per case searching for the correct modifier | Every manual case |
| **Motion** | Avg 1.8 min navigating between 3 system screens | Every manual case |
| **Defects** | 22% of manual cases end in an incorrect modifier → claim rejection | Every 5th case |
| **Extra Processing** | Duplicate entry across both the platform and the EMR | 60% of cases |
| **Non-Utilized Talent** | Skilled clinicians doing low-value administrative navigation | Every manual case |

| Metric | Current State | Future State | Change |
|---|---|---|---|
| Steps in workflow | 14 | 8 | −43% |
| Decision points requiring navigation | 4 | 1 | −75% |
| System screen transitions | 3 | 1 | −67% |
| Avg time per case | 8.4 min | 3.1 min | −63% |
| Projected modifier error rate | 22% | ~8% | −64% |

The 2-click cap held throughout — six steps got eliminated outright, and the two that remain (notification acknowledgment, audit record confirmation) stayed specifically *because* they satisfy the compliance audit trail requirement, not in spite of it.

---

## Where PM Judgment Actually Had to Show Up

The prompt ran clean. Every constraint passed, the waste classification held up against the mock, and the future-state SOP is technically deployable exactly as written. If the only question were "does the prompt work," the answer's yes — but that's not actually the question that matters.

The single highest-leverage fix in the whole redesign — embedding the modifier reference directly in the review screen — isn't a configuration change a PM can just approve. **It requires the vendor to build a feature that doesn't exist on the roadmap.** (Cue the endless negotiation cycle.) 

The prompt treats it as in-scope because it technically stays within the API display layer, and on paper, that's true. But "technically in scope" and "the vendor will actually prioritize this" are two completely different conversations, and only one of them shows up in an output document. Before this SOP gets published as deployed, it needs a real ROI case attached — time saved × case volume × clinician cost per minute — submitted as a formal feature request, with a timeline commitment attached, not a hope. An SOP that depends on a feature that doesn't exist is a roadmap item wearing a deployment document's clothes.

Two smaller gaps are worth naming here too, though they get fuller treatment in PROCESS.md: the duplicate-EMR-entry exception resolves cleanly on paper but actually creates 200+ site-level rules someone still has to go collect and codify, and the archetype the output labels "resistant" isn't really resistant — it's rational skepticism from clinicians who've watched EMR promises break before, and a rollout built for willing adopters with a special track for skeptics has the ratio backwards.

---

## ↳︎ Repository Contents

```
project-clarity/
├── README.md                              ← This document
├── PROCESS.md                             ← PM decision log and AI methodology
├── /data/
│   ├── current-state-workflow.md          ← 14-step current process with time-on-task data
│   ├── friction-inventory.md              ← 5 clinician archetypes + waste mapping
│   └── process-constraints.md            ← 8 guardrails for redesign
├── /prompts/
│   └── process-analysis-prompt.md        ← The AI workflow analysis engine
└── /output/
    ├── waste-analysis.md                  ← Lean 8-wastes classification (full)
    ├── value-stream-map.md                ← Current vs. future state VSM
    ├── future-state-sop.md                ← Deployment-ready optimized SOP
    └── rollout-plan.md                    ← Phased change management plan (50 sites)
```

---

The constraint enforcement is worth naming directly here, since it's easy to miss in a repo listing: the prompt is structurally unable to skip diagnosis and jump to a fix. Waste classification has to complete before future-state design even starts. That's not a nice-to-have — it's the whole methodology, built into the architecture instead of left as a step someone could rush past under deadline pressure.

---

## Try This Yourself

There's a live page with a one-click **Copy Prompt** button — grabs the full prompt plus data, ready to paste into Claude, GPT-4, or Gemini.

›︎ [Open Project Clarity Prompt Copy page](https://zinaleeHQ.github.io/project-clarity/)

It pauses at a judgment checkpoint before the final phase, same as the others. That pause is the point.

---

## ↳︎ Portfolio Navigation

Project 2 of 4. Together, four projects tell one story.

| Project | Question Answered | Methodology |
|---|---|---|
| [Project Horizon](https://github.com/zinaleeHQ/project-horizon) | What do we build, and when? | SAFe · WSJF |
| **Project Clarity** (this repo) | How do we change how people actually work? | Lean · DMAIC |
| [Project Signal](https://github.com/zinaleeHQ/project-signal) | How do we keep every stakeholder aligned? | Stakeholder Intelligence · Audience Mapping |
| [Project Vista](https://github.com/zinaleeHQ/project-vista) | How do we give every stakeholder self-service visibility? | KPI Governance · Data Architecture |

[**← Back to Portfolio Overview**](https://github.com/zinaleeHQ/zinaleeHQ/)

---

*Portfolio case study · Built from publicly available information · No proprietary data used · June 2026*

---

