# Data: Process Redesign Constraints

**Purpose:** Defines the non-negotiable boundaries for the future-state workflow design. These are loaded into the process analysis prompt as structured logic gates â not narrative context.

---

## The Eight Guardrails

| # | Constraint | Rule | Rationale |
|---|---|---|---|
| 1 | **Clinical Safety First** | No process step may introduce ambiguity into charge code selection for high-risk obstetric events (OB hemorrhage, pre-eclampsia, emergency C-section). These cases must always trigger mandatory secondary verification regardless of efficiency impact. | Patient safety is non-negotiable and overrides every other design principle. |
| 2 | **The 2-Click Friction Cap** | The future-state workflow cannot add more than two user actions vs. the current baseline total. It may reduce actions but cannot exceed baseline. | Inherited from Project Horizon constraint matrix. Protects clinician cognitive load in high-acuity environments. |
| 3 | **EMR Neutrality** | The future-state SOP must function identically in Epic and Cerner environments. No process step may be EMR-specific. | Float clinicians and multi-site operators cannot manage parallel workflows. Consistency requires EMR-agnostic design. |
| 4 | **Zero Training Budget** | Change management must be achievable through embedded workflow guidance alone. No live training sessions, webinars, or required reading may be assumed. | 2,000+ distributed clinicians across 200+ partner sites make centralized training logistically impossible. |
| 5 | **RCM platform API Boundary** | The future-state workflow may optimize the data *surrounding* RCM platformâs output but cannot modify RCM platformâs core AI coding logic or model parameters. | Same vendor constraint as Project Horizon â only the data translation and display layer is in scope. |
| 6 | **Duplicate Entry Elimination** | The future-state workflow must eliminate the duplicate charge logging step present at 60% of sites. If site-level EMR requirements cannot be reconciled at the platform level, the SOP must include an explicit exception protocol. | Duplicate entry is the most-cited waste by clinicians. Leaving it unresolved undermines adoption. |
| 7 | **Compliance Audit Trail** | Every manual charge entry must generate a structured decision record: modifier code selected, secondary diagnosis verified (yes/no), and clinician ID. Free-text documentation is insufficient. | HIPAA and billing audit requirements. Unstructured notes cannot be queried at scale. |
| 8 | **Rural Connectivity Resilience** | The future-state workflow must handle intermittent connectivity gracefully. If a submission times out, the clinician must receive a clear status confirmation and the case must not be lost or duplicated. | Rural site clinicians (Archetype 2) represent a significant failure mode in the current workflow. |

---

*Loaded as structured logic gates in the process analysis prompt Â· See [process-analysis-prompt.md](../prompts/process-analysis-prompt.md)*