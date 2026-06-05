# ð¶ Project Clarity: Clinical Workflow Optimization Blueprint

> **Standardizing AI-Assisted Charge Entry Across a Distributed Healthcare Workforce**

[![Methodology](https://img.shields.io/badge/Methodology-Lean%20%7C%20DMAIC-red?style=flat-square)]()
[![Domain](https://img.shields.io/badge/Domain-Clinical%20Operations%20%7C%20Change%20Management-teal?style=flat-square)]()
[![Status](https://img.shields.io/badge/Status-Portfolio%20Simulation-orange?style=flat-square)]()

---

## ð The Operational Challenge

Project Horizon identified three sprint-ready epics for a multi-site healthcare enterprise. Epic 2 â Clinician Workflow Optimization â earned its sprint slot through WSJF scoring. Now the harder question: what does optimization actually look like when 2,000+ clinicians across 200+ sites have each invented their own workaround?

The AI-assisted RCM platform successfully handles 85% of clinical charge entries. The remaining 15% require manual clinician intervention â but no standardized process exists for handling these cases. Every site has improvised. The result is inconsistent documentation, delayed claim submissions, a rising modifier error rate, and mounting clinician frustration with a platform that was supposed to reduce their administrative burden.

**This is not a technology problem. The technology works. This is a process problem.** And process problems require a different toolkit than product roadmaps.

This project documents an AI-assisted Lean DMAIC analysis of the manual charge entry workflow â from current-state mapping through future-state SOP generation â grounded in real operational constraints of a distributed clinical workforce.

---

## ð The DMAIC Framework Applied

| Phase | Question | Portfolio Artifact |
|---|---|---|
| **Define** | What is the problem and who does it affect? | Friction inventory Â· 5 clinician archetypes |
| **Measure** | Where exactly is the time and waste? | Current-state workflow Â· 14-step time-on-task map |
| **Analyze** | What are the root causes? | Lean 8 Wastes classification table |
| **Improve** | What does the optimized process look like? | Future-state SOP Â· Embedded decision tree |
| **Control** | How do we sustain the improvement? | Phased rollout plan Â· Adoption metrics framework |

---

## ð¥ The Data Inputs

Three structured inputs feed the AI analysis engine. See the `/data` folder for full source files.

### Current-State Workflow
A step-by-step documentation of the current manual charge entry process â 14 steps from clinical event to charge submission, including the four decision points where clinicians improvise and the system handoffs that generate the most friction and error.

### Friction Inventory
Structured feedback across five clinician archetypes, each representing a distinct site profile and experience level. Each archetype carries specific complaints pre-mapped to Lean waste categories â simulating structured discovery data a PM would collect through site visits and interviews.

### Process Constraints
Eight hard guardrails defining what the redesigned workflow can and cannot do â including the 2-click friction cap inherited from Project Horizon, EMR neutrality requirements (Epic and Cerner must work identically), a zero-training-budget change management constraint, and clinical safety non-negotiables for high-risk obstetric cases.

---

## ð¤ The AI Analysis Engine

The prompt in `/prompts/process-analysis-prompt.md` performs four sequential operations:

1. **Waste classification** â Maps every identified friction point to the Lean 8 Wastes framework before any redesign work begins
2. **Root cause analysis** â Identifies the structural causes of waste clusters, not just surface symptoms
3. **Future-state design** â Generates an optimized workflow that eliminates non-value-added steps while satisfying every process constraint
4. **SOP generation** â Produces a deployment-ready Standard Operating Procedure with embedded decision logic and exception handling for edge cases

Critically: the prompt cannot propose a future state until the waste analysis is complete. This enforces the Lean principle of diagnosing before solving.

---

## ð The Output: Before & After

### Waste Picture (Current State)

| Waste Type | Current-State Impact | Frequency |
|---|---|---|
| **Waiting** | Avg 2.4 min per case searching for correct modifier reference | Every manual case |
| **Motion** | Avg 1.8 min navigating between 3 system screens | Every manual case |
| **Defects** | 22% of manual cases result in incorrect modifier â claim rejection | Every 5th case |
| **Extra Processing** | Duplicate data entry in both RCM platform and EMR | 60% of cases |
| **Non-Utilized Talent** | Skilled clinicians performing low-value administrative navigation | Every manual case |

### Value Stream Comparison

| Metric | Current State | Future State | Improvement |
|---|---|---|---|
| Steps in workflow | 14 | 8 | â43% |
| Decision points requiring navigation | 4 | 1 | â75% |
| System screen transitions | 3 | 1 | â67% |
| Avg time per case | 8.4 min | 3.1 min | â63% |
| Projected modifier error rate | 22% | ~8% | â64% |

> **How the 2-click cap was honored:** The future-state workflow eliminates 6 steps entirely (Steps 03, 05, 07, 10, 11, 13 in current state). The 2 remaining non-value-added steps (notification acknowledgment and audit record confirmation) are retained because they satisfy the compliance audit trail constraint â not despite it.

---

## ð Repository Contents

```
project-clarity/
âââ README.md                              â This document
âââ PROCESS.md                             â PM decision log and AI methodology
âââ /data/
â   âââ current-state-workflow.md          â 14-step current process with time-on-task data
â   âââ friction-inventory.md              â 5 clinician archetypes + waste mapping
â   âââ process-constraints.md            â 8 guardrails for redesign
âââ /prompts/
â   âââ process-analysis-prompt.md        â The AI workflow analysis engine
âââ /output/
    âââ waste-analysis.md                  â Lean 8-wastes classification (full)
    âââ value-stream-map.md                â Current vs. future state VSM
    âââ future-state-sop.md                â Deployment-ready optimized SOP
    âââ rollout-plan.md                    â Phased change management plan (50 sites)
```

---

## â Project Manager Requirements

| Requirement | How This Project Demonstrates It |
|---|---|
| *âAnalyze current-state workflows and identify opportunities for efficiency gainsâ* | 14-step current-state map with time-on-task data and Lean waste classification |
| *âDesign and implement optimized workflows that improve scalability and user experienceâ* | Future-state SOP with 43% step reduction, EMR-neutral design, and embedded decision logic |
| *âCreate and maintain process documentation, SOPs, workflow diagrams, and governance standardsâ* | Deployment-ready SOP with version control header, exception protocols, and compliance audit trail |
| *âLead continuous improvement initiatives using structured process improvement methodologiesâ* | Full DMAIC framework applied end-to-end with measurable before/after outcome targets |
| *âConduct root-cause analysis and recommend data-driven solutionsâ* | Lean 8-wastes root cause analysis drives every redesign decision |

---

## â Project Manager Methodology Intervention

I have built a constraint into the prompt that prevents the AI from proposing a future state until the waste analysis is complete. I have designed a guardrail into the system: the AI can't skip the diagnostic step because the methodology requires diagnosis before solution.

## ð Portfolio Navigation

| Project | Question Answered | Methodology |
|---|---|---|
| [Project Horizon](https://github.com/zinaleeHQ/project-horizon) | What do we build and when? | SAFe Â· WSJF |
| **Project Clarity** (this repo) | How do we change how people work? | Lean Â· DMAIC |
| [Project Signal](https://github.com/zinaleeHQ/project-signal) | How do we keep every stakeholder aligned? | Stakeholder Intelligence Â· Audience Mapping |

[**â Back to Portfolio Overview**](https://github.com/zinaleeHQ)

---

*Portfolio simulation Â· All scenario details constructed from publicly available information Â· No proprietary data from any organization has been used Â· Built June 2026*
