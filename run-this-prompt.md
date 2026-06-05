# Run This Prompt — Project Clarity

**Project:** Clinical Workflow Standardization (AI-Assisted Lean DMAI C Analysis)
**Framework:** Lean DMAI C · 8 Wastes Classification · Value Stream Mapping
**What you'll produce:** A future-state Standard Operating Procedure for the manual charge entry workflow

---

## How to Use This File

This file is self-contained. Copy everything in the **PROMPT** section below and paste it directly into any capable AI assistant (Claude, ChatGPT, Gemini). All data is embedded — no additional files needed.

The AI will work through four sequential phases:
1. Waste Classification — diagnose before prescribing
2. Root Cause Analysis — structural causes, not surface symptoms
3. Future-State Design — redesign with constraint validation
4. SOP Generation — deployment-ready Standard Operating Procedure

**After Phase 1 and Phase 2 are complete, the AI will pause and ask your permission before proceeding to design and generation.** That pause is intentional — it's where your PM judgment matters most.

---

## PROMPT (copy everything from here to the end of this file)

---

# Prompt: AI-Assisted Lean Process Analysis Engine

**Version:** 1.0
**Framework:** Lean DMAI C · 8 Wastes Classification · Value Stream Mapping

---

## Prompt Architecture Overview

This prompt executes in four sequential phases. **Phases must not be skipped or merged.** The output of each phase is the required input to the next.

1. **Phase 1 — Waste Classification:** Diagnose before prescribing
2. **Phase 2 — Root Cause Analysis:** Identify structural causes, not surface symptoms
3. **Phase 3 — Future-State Design:** Redesign with constraint validation
4. **Phase 4 — SOP Generation:** Produce the deployment-ready artifact

---

## 🔡 SYSTEM CONTEXT

You are a Lean process improvement assistant supporting a Product Manager at a multi-site healthcare operations organization. You have been given:

- A current-state workflow document (14 steps with time-on-task data)
- A clinician friction inventory (5 archetypes with waste-mapped complaints)
- A process redesign constraint matrix (8 hard guardrails)

Your role is to apply the Lean DMAI C framework to analyze the current workflow and generate a future-state Standard Operating Procedure that eliminates identified waste while satisfying every constraint.

**Critical behavioral rules:**
- Do not propose a future-state redesign until Phase 1 and Phase 2 are complete
- Do not violate any constraint, even if doing so would produce greater efficiency gains
- Every future-state step must be justified by the waste analysis that preceded it
- If a constraint and an efficiency improvement are in conflict, the constraint wins — flag the conflict explicitly
- The future-state SOP must be deployable without training — a clinician who has never seen it must be able to follow it correctly on first read

---

## 📄 INPUT DATA SOURCES

**INPUT_A: Current-State Workflow**
```
# Data: Current-State Manual Charge Entry Workflow

**Process:** RCM platform Non-Autonomous Case — Manual Charge Entry
**Scope:** Applies to ~15% of all clinical encounters
**Affected users:** 2,000+ distributed hospitalists across 200+ partner sites
**Current average time-on-task:** 8.4 minutes per case (no rework) / 10.2+ min with rework
**Status:** Undocumented — this workflow has never been formally standardized

> This document represents the reconstructed current-state workflow based on clinician feedback across 5 site archetypes. Because no formal SOP exists, this is the *de facto* process — what most clinicians actually do.

---

## The 14-Step Current-State Workflow

| Step | Action | Role | System | Avg Time | Value Classification |
|---|---|---|---|---|---|
| **01** | Clinical encounter concludes — RCM platform flags case as requiring manual review | RCM platform AI | RCM platform | 0 min | Required NVA |
| **02** | Clinician receives manual review notification (email or in-app — varies by site) | Hospitalist | RCM platform / EMR | 0.3 min | Required NVA |
| **03** | Clinician navigates to RCM platform manual review queue | Hospitalist | RCM platform | 0.8 min | **NVA — Motion** |
| **04** | Clinician opens flagged case and reviews AI-generated clinical documentation summary | Hospitalist | RCM platform | 1.2 min | Value-Added |
| **05** | Clinician navigates to a separate screen/tab to look up correct CPT/ICD-10 modifier code | Hospitalist | EMR or External Ref | 2.4 min | **NVA — Waiting / Motion** |
| **06** | Clinician returns to RCM platform and manually enters the modifier code | Hospitalist | RCM platform | 0.6 min | Required NVA |
| **07** | RCM platform prompts for secondary diagnosis confirmation — clinician navigates back to EMR to verify | Hospitalist | EMR | 1.1 min | **NVA — Motion** |
| **08** | Clinician returns to RCM platform and confirms or corrects secondary diagnosis | Hospitalist | RCM platform | 0.4 min | Value-Added |
| **09** | Clinician submits charge in RCM platform | Hospitalist | RCM platform | 0.3 min | Value-Added |
| **10** | Clinician separately logs the charge entry in the hospital EMR (required at 60% of sites) | Hospitalist | EMR | 0.8 min | **NVA — Extra Processing** |
| **11** | Clinician documents the manual review decision in a free-text notes field (no standard format) | Hospitalist | RCM platform | 0.6 min | Required NVA |
| **12** | Billing coordinator receives submission and manually checks modifier alignment | Billing Coord | Billing System | 0.4 min | **NVA — Defect Prevention** |
| **13** | *If modifier mismatch:* billing coordinator contacts clinician for correction (24–48hr delay) | Billing Coord | Email / Phone | 1.8 min | **NVA — Defect / Rework** |
| **14** | Charge queued for claim submission | Billing System | Billing System | 0 min | Required NVA |

**No-rework total: 8.4 min · With rework loop (Step 13): 10.2+ min**

---

## Value Classification Summary

| Classification | Steps | % of Workflow |
|---|---|---|
| Value-Added | 04, 08, 09 | 21% |
| Required Non-Value-Added | 01, 02, 06, 11, 14 | 36% |
| Pure Waste (Eliminatable) | 03, 05, 07, 10, 12, 13 | 43% |

> **43% of this workflow is pure waste.** The future-state design targets elimination of all six waste steps.

---

## Decision Points Where Clinicians Currently Improvise

| Decision Point | Variation Observed | Root Cause |
|---|---|---|
| Step 05 — Finding the right modifier | External app / call billing / recall from memory | No embedded modifier reference in RCM platform |
| Step 07 — Secondary diagnosis verification | Full EMR chart / RCM platform summary / skip entirely | No standardized verification protocol |
| Step 10 — Duplicate EMR entry | Always / never / site-dependent | No clear guidance on site-level requirements |
| Step 11 — Free-text documentation | One sentence to a full paragraph | No template, no character guidance, no enforcement |

---

## System Handoff Map (Current State)

```
RCM platform Platform ⇄ Hospital EMR (Epic or Cerner)
        ↓
   Billing System
        ↓
 Insurance Claim Submission
```

**3 system transitions per case.** Each transition adds navigation time and creates an opportunity for context loss and error.

---

*Source: Reconstructed from simulated clinician interview data · See [friction-inventory.md](./friction-inventory.md) for archetype detail*
```

**INPUT_B: Friction Inventory**
```
# Data: Clinician Friction Inventory

**Purpose:** Structured voice-of-customer data across five representative clinician archetypes. Primary input to the Lean waste classification analysis.
**Method (simulated):** 30-minute structured interviews with workflow observation.

---

## Archetype 1: High-Volume Urban Academic Center Hospitalist

**Profile:** Large academic medical center · 50+ monthly RCM platform manual cases · Epic EMR · On-site billing coordinator · 8 years experience · 14 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | “I spend more time looking up modifier codes than reviewing the actual clinical documentation. There’s no reference built into the screen.” | Waiting |
| 2 | “I jump between RCM platform and Epic constantly. By the time I get back I’ve lost my train of thought on the case.” | Motion |
| 3 | “I log the charge in RCM platform and then log it again in Epic. Nobody can tell me why I have to do both.” | Extra Processing |
| 4 | “The free-text documentation field has no guidance. I write a sentence. My colleague writes a paragraph. Billing calls both of us.” | Defects |

---

## Archetype 2: Low-Volume Rural Critical Access Clinician

**Profile:** Critical access hospital · 8–12 monthly RCM platform manual cases · Cerner EMR · No dedicated billing coordinator · 12 years experience · 6 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | “I only do manual cases a few times a week. Every time I feel like I’m relearning the process from scratch.” | Non-Utilized Talent |
| 2 | “When RCM platform times out because of our internet connection, the case disappears. I have to start over.” | Defects |
| 3 | “I called billing three times last month to ask what modifier to use. They’re in a different time zone. I wait hours for a callback.” | Waiting |
| 4 | “The screen layout is different on Cerner than what I saw in training. I don’t know if I’m doing it right.” | Extra Processing |

---

## Archetype 3: Float Clinician Covering Multiple Sites

**Profile:** Covers 4 partner hospitals · Mixed Epic/Cerner environments · 20–25 monthly RCM platform manual cases · 5 years experience · 10 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | “Each hospital has a slightly different workflow. I can never remember which sites require the duplicate EMR entry.” | Motion |
| 2 | “I’ve had charges rejected at three different sites for three different reasons. There’s no consistency in what billing expects.” | Defects |
| 3 | “I waste time at the start of every manual case reminding myself which system I’m in and what the local rules are.” | Waiting |
| 4 | “Nobody told me about the updated RCM platform interface until I saw it on someone else’s screen at a different site.” | Non-Utilized Talent |

---

## Archetype 4: New Hire Within 90 Days of Onboarding

**Profile:** Mid-size community hospital · 15–20 monthly RCM platform manual cases · Epic EMR · 6 weeks using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | “Onboarding covered how RCM platform works in general but not what to do when it sends a case back to me.” | Non-Utilized Talent |
| 2 | “I asked my supervisor. Then a colleague. Completely different approaches. I still don’t know which is right.” | Defects |
| 3 | “I’m slower than everyone else because I’m still figuring out the steps. I feel like I’m holding up the team.” | Waiting |
| 4 | “I’ve submitted the same charge twice by accident because I wasn’t sure if the first submission went through.” | Extra Processing |

---

## Archetype 5: Senior Hospitalist Resistant to Workflow Changes

**Profile:** Regional medical center · 30+ monthly RCM platform manual cases · Epic EMR · Informal team lead · 18 years experience · 16 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | “The old process took me 4 minutes. This one takes 8. A computer is telling me I’m coding wrong after 18 years.” | Non-Utilized Talent |
| 2 | “I have my own reference sheet that works better than anything in the system. Why can’t they just build that into the screen?” | Extra Processing |
| 3 | “Every time there’s an update something moves. I have to relearn where to click. It’s disruptive.” | Motion |
| 4 | “I don’t trust the AI summary enough to skip reading the full chart. So I’m doing more work than before RCM platform.” | Waiting |

---

## Cross-Archetype Summary

| Waste Type | Archetypes Affected | Relative Frequency |
|---|---|---|
| **Waiting** | 1, 2, 3, 5 | Every manual case |
| **Motion** | 1, 3, 5 | Every manual case |
| **Defects** | 1, 2, 3, 4 | ~22% of manual cases |
| **Extra Processing** | 1, 2, 4, 5 | ~60% of cases |
| **Non-Utilized Talent** | 2, 3, 4, 5 | Episodic but high-cost |

> **Non-Utilized Talent is the highest-cost waste type.** Using skilled clinicians for low-value administrative navigation tasks is expensive even when it’s infrequent. Clinician time is the most constrained and costly resource in this system.

---

*Source: Simulated interview data constructed for portfolio purposes · See [PROCESS.md](../PROCESS.md) for archetype design rationale*
```

**INPUT_C: Process Constraints**
```
# Data: Process Redesign Constraints

**Purpose:** Defines the non-negotiable boundaries for the future-state workflow design. These are loaded into the process analysis prompt as structured logic gates — not narrative context.

---

## The Eight Guardrails

| # | Constraint | Rule | Rationale |
|---|---|---|---|
| 1 | **Clinical Safety First** | No process step may introduce ambiguity into charge code selection for high-risk obstetric events (OB hemorrhage, pre-eclampsia, emergency C-section). These cases must always trigger mandatory secondary verification regardless of efficiency impact. | Patient safety is non-negotiable and overrides every other design principle. |
| 2 | **The 2-Click Friction Cap** | The future-state workflow cannot add more than two user actions vs. the current baseline total. It may reduce actions but cannot exceed baseline. | Inherited from Project Horizon constraint matrix. Protects clinician cognitive load in high-acuity environments. |
| 3 | **EMR Neutrality** | The future-state SOP must function identically in Epic and Cerner environments. No process step may be EMR-specific. | Float clinicians and multi-site operators cannot manage parallel workflows. Consistency requires EMR-agnostic design. |
| 4 | **Zero Training Budget** | Change management must be achievable through embedded workflow guidance alone. No live training sessions, webinars, or required reading may be assumed. | 2,000+ distributed clinicians across 200+ partner sites make centralized training logistically impossible. |
| 5 | **RCM platform API Boundary** | The future-state workflow may optimize the data *surrounding* RCM platform’s output but cannot modify RCM platform’s core AI coding logic or model parameters. | Same vendor constraint as Project Horizon — only the data translation and display layer is in scope. |
| 6 | **Duplicate Entry Elimination** | The future-state workflow must eliminate the duplicate charge logging step present at 60% of sites. If site-level EMR requirements cannot be reconciled at the platform level, the SOP must include an explicit exception protocol. | Duplicate entry is the most-cited waste by clinicians. Leaving it unresolved undermines adoption. |
| 7 | **Compliance Audit Trail** | Every manual charge entry must generate a structured decision record: modifier code selected, secondary diagnosis verified (yes/no), and clinician ID. Free-text documentation is insufficient. | HIPAA and billing audit requirements. Unstructured notes cannot be queried at scale. |
| 8 | **Rural Connectivity Resilience** | The future-state workflow must handle intermittent connectivity gracefully. If a submission times out, the clinician must receive a clear status confirmation and the case must not be lost or duplicated. | Rural site clinicians (Archetype 2) represent a significant failure mode in the current workflow. |

---

*Loaded as structured logic gates in the process analysis prompt · See [process-analysis-prompt.md](../prompts/process-analysis-prompt.md)*
```

---

## 🔴 PHASE 1: WASTE CLASSIFICATION (Measure + Analyze)

### The Lean 8 Wastes Framework
For each step in the current-state workflow AND each friction complaint in the inventory, classify against the following waste types:

| Waste | Definition | Healthcare Example |
|---|---|---|
| **Defects** | Work that requires rework, correction, or causes downstream failure | Incorrect modifier code triggering claim rejection |
| **Overproduction** | Doing more than what is needed, sooner than needed | Generating documentation no one reads |
| **Waiting** | Idle time while waiting for the next step, information, or system response | Clinician waiting for modifier code lookup result |
| **Non-Utilized Talent** | Using skilled people for low-value tasks below their competency level | Physician doing administrative data entry |
| **Transportation** | Unnecessary movement of information between systems or people | Charge data moving through 3 systems unnecessarily |
| **Inventory** | Unprocessed work accumulating | Claims stuck in modifier review queue |
| **Motion** | Unnecessary movement within a process | Navigating between 3 screens to complete one task |
| **Extra Processing** | Doing more than the customer requires | Duplicate data entry in RCM platform and EMR |

### Phase 1 Output Requirements
Produce:
1. A waste classification table mapping every current-state step to its primary waste type
2. A cross-archetype waste frequency analysis (which waste types affect which archetypes)
3. A ranked list of waste types by total time impact (minutes per case)
4. A list of steps that can be **eliminated entirely** vs. steps that must be **redesigned**

**Do not proceed to Phase 2 until Phase 1 output is complete.**

---

## 🎠 PHASE 2: ROOT CAUSE ANALYSIS

For each waste type identified in Phase 1, identify the structural root cause — the underlying system or process failure that generates the waste.

### Root Cause Instruction
- Do not accept the surface symptom as the root cause
- Ask "why does this waste exist?" at least twice before naming the root cause
- Distinguish between causes that can be addressed within the RCM platform API boundary and those that require changes outside scope
- Flag any root causes that affect multiple waste types (these are high-leverage intervention points)

### Phase 2 Output Requirements
Produce:
1. A root cause summary table: Waste Type → Surface Symptom → Root Cause → In-Scope (Y/N)
2. A list of high-leverage intervention points (root causes affecting ≥2 waste types)
3. A clear statement of what the future-state design must solve for, ranked by impact

**Do not proceed to Phase 3 until Phase 2 output is complete.**

---

**⏸️ PAUSE HERE.** Before proceeding to Phase 3, summarize what you've found in Phases 1 and 2 and ask: "I've completed the waste analysis and root cause identification. Would you like me to proceed to Phase 3 (Future-State Design) and Phase 4 (SOP Generation)?"

Wait for confirmation before continuing.

---

## 🎢 PHASE 3: FUTURE-STATE DESIGN

### Design Instructions
Using the waste analysis and root cause findings, design a future-state workflow that:
1. Eliminates all steps classified as pure waste in Phase 1
2. Redesigns Required NVA steps to minimize time-on-task
3. Preserves all Value-Added steps
4. Satisfies every constraint in INPUT_C

### Constraint Validation Step
Before finalizing the future-state design, validate each proposed step against the 8 guardrails:

| Check | Question |
|---|---|
| Clinical Safety | Does this step maintain mandatory verification for high-risk OB cases? |
| 2-Click Cap | Does this step's action count stay within the baseline + 2 limit? |
| EMR Neutrality | Does this step work identically on Epic and Cerner? |
| Zero Training | Can a first-time user follow this step correctly without instruction? |
| RCM platform Boundary | Does this step stay within the RCM platform API data layer? |
| Duplicate Entry | Does this step eliminate or explicitly resolve duplicate EMR entry? |
| Audit Trail | Does this step generate a structured, queryable decision record? |
| Connectivity | Does this step handle a timeout or connectivity failure gracefully? |

If any step fails a constraint check: redesign the step before proceeding. Do not ship a violation.

### Phase 3 Output Requirements
Produce:
1. The future-state workflow as a numbered step table (matching format of INPUT_A)
2. A before/after comparison table (steps, decision points, system transitions, time estimates)
3. A log of any constraint conflicts encountered and how they were resolved

**Do not proceed to Phase 4 until Phase 3 output has passed all constraint checks.**

---

## 🔵 PHASE 4: SOP GENERATION

### SOP Requirements
Generate a deployment-ready Standard Operating Procedure using the following structure:

```
## Standard Operating Procedure
### [Process Title]

**Document ID:** [SOP-COMM-001]
**Version:** 1.0
**Effective Date:** [Date]
**Owner:** Product Management · Clinical Operations
**Review Cycle:** Quarterly

---

**Purpose:** [One sentence]
**Scope:** [Who this applies to and under what conditions]
**Definitions:** [Any terms requiring clarification]

---

**Procedure:**
[Numbered steps with role, action, system, and expected outcome per step]

---

**Decision Tree:**
[Embedded logic for the key decision point(s)]

---

**Exception Protocols:**
[High-risk OB case handling]
[Connectivity timeout handling]
[Modifier uncertainty handling]

---

**Compliance Requirements:**
[Audit trail fields required per case]

---

**Version History:**
[Version · Date · Change Summary · Author]
```

### SOP Quality Checklist
Before finalizing:
- [ ] Every step has a role, action, system, and expected outcome
- [ ] Decision tree covers all branch conditions
- [ ] Exception protocols address all 3 required scenarios
- [ ] Audit trail fields are structured (not free-text)
- [ ] SOP is self-explanatory without training materials
- [ ] Version control header is complete

---

*Prompt Version 1.0 · Framework: Lean DMAI C · Built June 2026*
*See [PROCESS.md](./PROCESS.md) for design decisions behind this prompt architecture.*
