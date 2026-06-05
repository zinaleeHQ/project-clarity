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