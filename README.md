# 🔶 Project Clarity: Clinical Workflow Optimization Blueprint

> **Standardizing AI-Assisted Charge Entry Across a Distributed Healthcare Workforce**

[![Methodology](https://img.shields.io/badge/Methodology-Lean%20%7C%20DMAIC-red?style=flat-square)]()
[![Domain](https://img.shields.io/badge/Domain-Clinical%20Operations%20%7C%20Change%20Management-teal?style=flat-square)]()
[![Status](https://img.shields.io/badge/Status-Portfolio%20Simulation-orange?style=flat-square)]()

---

## 📋 The Operational Challenge

Project Horizon identified three sprint-ready epics for a multi-site healthcare enterprise. Epic 2 — Clinician Workflow Optimization — earned its sprint slot through WSJF scoring. Now the harder question: what does optimization actually look like when 2,000+ clinicians across 200+ sites have each invented their own workaround?

The Commure autonomous coding engine successfully handles 85% of clinical charge entries. The remaining 15% require manual clinician intervention — but no standardized process exists for handling these cases. Every site has improvised. The result is inconsistent documentation, delayed claim submissions, a rising modifier error rate, and mounting clinician frustration with a platform that was supposed to reduce their administrative burden.

**This is not a technology problem. The technology works. This is a process problem.** And process problems require a different toolkit than product roadmaps.

This project documents an AI-assisted Lean DMAIC analysis of the manual charge entry workflow — from current-state mapping through future-state SOP generation — grounded in real operational constraints of a distributed clinical workforce.

---

## 🔍 The DMAIC Framework Applied

| Phase | Question | Portfolio Artifact |
|---|---|---|
| **Define** | What is the problem and who does it affect? | Friction inventory · 5 clinician archetypes |
| **Measure** | Where exactly is the time and waste? | Current-state workflow · 14-step time-on-task map |
| **Analyze** | What are the root causes? | Lean 8 Wastes classification table |
| **Improve** | What does the optimized process look like? | Future-state SOP · Embedded decision tree |
| **Control** | How do we sustain the improvement? | Phased rollout plan · Adoption metrics framework |

---

## 📥 The Data Inputs

Three structured inputs feed the AI analysis engine. See the `/data` folder for full source files.

### Current-State Workflow
A step-by-step documentation of the current manual charge entry process — 14 steps from clinical event to charge submission, including the four decision points where clinicians improvise and the system handoffs that generate the most friction and error.

### Friction Inventory
Structured feedback across five clinician archetypes, each representing a distinct site profile and experience level. Each archetype carries specific complaints pre-mapped to Lean waste categories — simulating structured discovery data a PM would collect through site visits and interviews.

### Process Constraints
Eight hard guardrails defining what the redesigned workflow can and cannot do — including the 2-click friction cap inherited from Project Horizon, EMR neutrality requirements (Epic and Cerner must work identically), a zero-training-budget change management constraint, and clinical safety non-negotiables for high-risk obstetric cases.

---

## 🤖 The AI Analysis Engine

The prompt in `/prompts/process-analysis-prompt.md` performs four sequential operations:

1. **Waste classification** — Maps every identified friction point to the Lean 8 Wastes framework before any redesign work begins
2. **Root cause analysis** — Identifies the structural causes of waste clusters, not just surface symptoms
3. **Future-state design** — Generates an optimized workflow that eliminates non-value-added steps while satisfying every process constraint
4. **SOP generation** — Produces a deployment-ready Standard Operating Procedure with embedded decision logic and exception handling for edge cases

Critically: the prompt cannot propose a future state until the waste analysis is complete. This enforces the Lean principle of diagnosing before solving.

---

## 📊 The Output: Before & After

### Waste Picture (Current State)

| Waste Type | Current-State Impact | Frequency |
|---|---|---|
| **Waiting** | Avg 2.4 min per case searching for correct modifier reference | Every manual case |
| **Motion** | Avg 1.8 min navigating between 3 system screens | Every manual case |
| **Defects** | 22% of manual cases result in incorrect modifier → claim rejection | Every 5th case |
| **Extra Processing** | Duplicate data entry in both Commure and EMR | 60% of cases |
| **Non-Utilized Talent** | Skilled clinicians performing low-value administrative navigation | Every manual case |

### Value Stream Comparison

| Metric | Current State | Future State | Improvement |
|---|---|---|---|
| Steps in workflow | 14 | 8 | −43% |
| Decision points requiring navigation | 4 | 1 | −75% |
| System screen transitions | 3 | 1 | −67% |
| Avg time per case | 8.4 min | 3.1 min | −63% |
| Projected modifier error rate | 22% | ~8% | −64% |

> **How the 2-click cap was honored:** The future-state workflow eliminates 6 steps entirely (Steps 03, 05, 07, 10, 11, 13 in current state). The 2 remaining non-value-added steps (notification acknowledgment and audit record confirmation) are retained because they satisfy the compliance audit trail constraint — not despite it.

---

## 📁 Repository Contents

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

## ✅ Project Manager Requirements

| Requirement | How This Project Demonstrates It |
|---|---|
| *“Analyze current-state workflows and identify opportunities for efficiency gains”* | 14-step current-state map with time-on-task data and Lean waste classification |
| *“Design and implement optimized workflows that improve scalability and user experience”* | Future-state SOP with 43% step reduction, EMR-neutral design, and embedded decision logic |
| *“Create and maintain process documentation, SOPs, workflow diagrams, and governance standards”* | Deployment-ready SOP with version control header, exception protocols, and compliance audit trail |
| *“Lead continuous improvement initiatives using structured process improvement methodologies”* | Full DMAIC framework applied end-to-end with measurable before/after outcome targets |
| *“Conduct root-cause analysis and recommend data-driven solutions”* | Lean 8-wastes root cause analysis drives every redesign decision |

---

## 🔗 Portfolio Navigation

| Project | Question Answered | Methodology |
|---|---|---|
| [Project Horizon](https://github.com/zinaleeHQ/project-horizon) | What do we build and when? | SAFe · WSJF |
| **Project Clarity** (this repo) | How do we change how people work? | Lean · DMAIC |
| [Project Signal](https://github.com/zinaleeHQ/project-signal) | How do we keep every stakeholder aligned? | Stakeholder Intelligence · Audience Mapping |

[**← Back to Portfolio Overview**](https://github.com/zinaleeHQ)

---

*Portfolio simulation · All scenario details constructed from publicly available information · No proprietary data from any organization has been used · Built June 2026*
