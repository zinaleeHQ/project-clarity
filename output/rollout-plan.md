# Output: Phased Change Management Rollout Plan

**Scope:** 50 pilot sites across 3 deployment phases
**Timeline:** 6 weeks (aligned with Sprint 2â3 delivery window from Project Horizon)
**Constraint:** Zero training budget â all adoption must be achieved through embedded guidance

---

## Rollout Philosophy

This plan is designed around one principle: **the workflow change is the training.** In a distributed organization with 2,000+ clinicians across 200+ partner sites, you cannot train your way to adoption. You have to design your way to it.

Every phase is built around embedded guidance, workflow-level prompts, and real-time feedback rather than pre-deployment education. Clinicians encounter the new process, understand it immediately from the interface, and experience the efficiency improvement in their first case. That experience is the adoption mechanism.

---

## Pilot Site Selection Criteria

Pilot sites were selected to represent all five clinician archetypes and both EMR environments:

| Cohort | Sites | Archetype Focus | EMR | Selection Rationale |
|---|---|---|---|---|
| A | 10 sites | Archetypes 1 + 5 | Epic | High-volume, experienced users â will surface usability issues quickly |
| B | 20 sites | Archetypes 2 + 3 | Cerner + Mixed | Rural and float clinicians â tests EMR neutrality and connectivity resilience |
| C | 20 sites | Archetype 4 | Mixed | New hires â tests zero-training assumption under real onboarding conditions |

---

## Phase 1: Baseline & Site Preparation (Weeks 1â2)

**Goal:** Establish measurement baseline and prepare site coordinators before deployment

| Activity | Owner | Timing |
|---|---|---|
| Capture current-state time-on-task metrics from EMR audit logs (10 sites sample) | Data Engineer | Week 1 |
| Capture current modifier error rate from billing system (30-day baseline) | PM + Revenue Cycle | Week 1 |
| Brief Site Coordinators at 50 pilot sites via a single 15-minute recorded video (one-time exception to zero-training rule â coordinator only, not clinicians) | PM | Week 1â2 |
| Deploy updated RCM platform interface to staging environment for QA validation | Engineering | Week 2 |
| Confirm EMR API connection for automatic charge confirmation (eliminates duplicate entry) | Data Engineer | Week 2 |

**Phase 1 Gate:** Baseline metrics captured Â· Staging QA passed Â· Site coordinators briefed

---

## Phase 2: Pilot Deployment & Embedded Adoption (Weeks 3â4)

**Goal:** Deploy to 50 pilot sites and achieve adoption through the workflow itself

| Activity | Owner | Timing |
|---|---|---|
| Deploy updated RCM platform interface to all 50 pilot sites during FridayâSaturday maintenance window | Engineering | Week 3 |
| In-workflow first-use guide: on first manual case post-deployment, a 3-step tooltip sequence walks the clinician through what changed (dismissible, never reappears) | Product / Engineering | Week 3 |
| Passive feedback button: âWas this faster?â (Yes / No / Not Sure) embedded in submission confirmation screen | Product | Week 3 |
| Site coordinator daily exception log: captures any cases where clinicians escalate confusion or process failures | Site Coordinators | Weeks 3â4 |
| PM weekly review of exception log + feedback data â triage and resolve within 48 hours | PM | Weeks 3â4 |

**Phase 2 Gate:** 50 sites live Â· No critical defects in exception log Â· Feedback button response rate â¥30%

---

## Phase 3: Measurement, Refinement & Go/No-Go (Weeks 5â6)

**Goal:** Measure impact against baseline and make the enterprise rollout decision

| Activity | Owner | Timing |
|---|---|---|
| Time-on-task measurement: pull EMR audit log data for 50 pilot sites and compare against Week 1 baseline | Data Engineer | Week 5 |
| Modifier error rate measurement: pull billing rejection data for pilot sites (30-day post-deployment) | PM + Revenue Cycle | Week 5 |
| Clinician satisfaction pulse: 5-question survey to all pilot site hospitalists (delivered via RCM platform notification) | PM | Week 5 |
| Analyze exception log patterns: identify any archetype-specific failure modes not addressed by the current SOP | PM | Week 5 |
| SOP Version 1.1: incorporate any critical exception log findings as protocol updates | PM | Week 6 |
| Go/No-Go decision: present results against success criteria to Clinical Operations VP | PM | Week 6 |

**Phase 3 Gate â Enterprise Rollout Go Criteria:**
- [ ] Manual charge entry time reduced by â¥40% vs. baseline at â¥80% of pilot sites
- [ ] Modifier error rate reduced by â¥30% vs. baseline
- [ ] Clinician satisfaction: â¥70% rate the new workflow as faster or equivalent
- [ ] Zero patient safety incidents attributable to the workflow change
- [ ] No critical defects remaining open in the exception log

---

## Success Metrics Dashboard

| Metric | Baseline (Pre-Deployment) | Target (Post-Deployment) | Measurement Source |
|---|---|---|---|
| Avg time per manual case | 8.4 min | â¤4.5 min | EMR audit log timestamps |
| Modifier error rate | 22% | â¤15% | Billing rejection data |
| Duplicate entry incidents | 60% of cases | 0% | RCM platform submission log |
| Clinician satisfaction | Unknown | â¥70% positive | Pulse survey |
| Exception escalations | Undocumented | â¤5 per 1,000 cases | Site coordinator log |

---

*Rollout plan generated from future-state SOP and constraint matrix Â· Aligns with Sprint 2 delivery timeline from [Project Horizon](https://github.com/zinaleeHQ/project-horizon) sprint-roadmap*
*[Back to README](../README.md)*