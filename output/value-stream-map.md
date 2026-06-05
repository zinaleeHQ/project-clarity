# Output: Value Stream Map â Current State vs. Future State

**Process:** RCM platform Non-Autonomous Case â Manual Charge Entry
**Analysis basis:** Lean waste classification + root cause findings

---

## Current State Summary

| Metric | Value |
|---|---|
| Total steps | 14 |
| Value-added steps | 3 (21%) |
| Pure waste steps | 6 (43%) |
| Required NVA steps | 5 (36%) |
| System transitions | 3 |
| Decision points requiring navigation | 4 |
| Avg time per case (no rework) | 8.4 min |
| Avg time per case (with rework, 22% of cases) | 10.2 min |
| Modifier error rate | 22% |
| Duplicate entry burden | 60% of cases |

---

## Future State Summary

| Metric | Value | vs. Current State |
|---|---|---|
| Total steps | 8 | **â43%** |
| Value-added steps | 3 (37%) | Same steps, higher % |
| Pure waste steps | 0 | **â100%** |
| Required NVA steps | 5 (63%) | Reduced time per step |
| System transitions | 1 | **â67%** |
| Decision points requiring navigation | 1 | **â75%** |
| Avg time per case | 3.1 min | **â63%** |
| Projected modifier error rate | ~8% | **â64%** |
| Duplicate entry burden | 0% | **â100%** |

---

## Step-by-Step Comparison

### Current State (14 steps)
```
[01] RCM platform flags case â [02] Notification received â [03] Navigate to queue*
â [04] Review AI summary â [05] Navigate to modifier lookup* â [06] Enter modifier
â [07] Navigate to EMR for secondary dx* â [08] Confirm secondary dx
â [09] Submit charge â [10] Duplicate EMR log* â [11] Free-text documentation*
â [12] Billing modifier check* â [13] Rework loop (22% of cases)* â [14] Claim queue

* = Pure waste step
```

### Future State (8 steps)
```
[01] RCM platform flags case + surfaces inline: AI summary + top 3 modifier suggestions
     with confidence scores + secondary dx pre-populated from EMR
â [02] Notification received with direct deep-link to case review screen
â [03] Clinician reviews integrated view: summary + modifiers + secondary dx in one screen
â [04] Clinician selects or confirms modifier (with high-risk OB flag if applicable)
â [05] Clinician confirms secondary diagnosis (mandatory for flagged cases)
â [06] Structured audit record auto-generated: modifier selected + dx confirmed + clinician ID
â [07] Single-action charge submission â confirmation status displayed inline
â [08] Charge queued for claim submission â API confirmation sent to EMR (no duplicate entry)
```

---

## How Each Waste Step Was Eliminated

| Eliminated Step | Solution | Constraint Satisfied |
|---|---|---|
| Step 03 â Navigate to queue | Deep-link in notification takes clinician directly to case | Zero Training (obvious), 2-Click Cap |
| Step 05 â External modifier lookup | Top 3 AI-suggested modifiers with confidence scores displayed inline | RCM platform API boundary (display layer only) |
| Step 07 â Navigate to EMR for secondary dx | Secondary dx pre-populated from EMR via existing API | RCM platform API boundary, EMR Neutrality |
| Step 10 â Duplicate EMR entry | API confirmation sent to EMR on submission â no manual entry | Duplicate Entry Elimination, EMR Neutrality |
| Step 11 â Free-text documentation | Replaced with structured confirmation fields (auto-generated audit record) | Compliance Audit Trail |
| Steps 12+13 â Billing rework loop | Structured modifier selection + confidence scoring reduces error rate from 22% to ~8% | Revenue Preservation |

---

## Constraint Conflict Log

One constraint conflict was identified and resolved during the design phase:

**Conflict:** The zero-training-budget constraint requires the modifier suggestion display to be self-explanatory. However, displaying confidence scores requires clinicians to understand what a confidence score means â which could be considered a training dependency.

**Resolution:** Confidence scores are displayed as a visual indicator (High / Medium / Review) rather than a percentage, with color coding. No interpretation training required. The label âReviewâ implies the clinician should verify â without requiring explanation of the underlying probability calculation.

---

*Output generated from waste analysis Â· See [future-state-sop.md](./future-state-sop.md) for the deployment-ready procedure*