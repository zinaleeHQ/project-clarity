# Output: Value Stream Map — Current State vs. Future State

**Process:** RCM platform Non-Autonomous Case — Manual Charge Entry
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
| Total steps | 8 | **−43%** |
| Value-added steps | 3 (37%) | Same steps, higher % |
| Pure waste steps | 0 | **−100%** |
| Required NVA steps | 5 (63%) | Reduced time per step |
| System transitions | 1 | **−67%** |
| Decision points requiring navigation | 1 | **−75%** |
| Avg time per case | 3.1 min | **−63%** |
| Projected modifier error rate | ~8% | **−64%** |
| Duplicate entry burden | 0% | **−100%** |

---

## Step-by-Step Comparison

### Current State (14 steps)
```
[01] RCM platform flags case → [02] Notification received → [03] Navigate to queue*
→ [04] Review AI summary → [05] Navigate to modifier lookup* → [06] Enter modifier
→ [07] Navigate to EMR for secondary dx* → [08] Confirm secondary dx
→ [09] Submit charge → [10] Duplicate EMR log* → [11] Free-text documentation*
→ [12] Billing modifier check* → [13] Rework loop (22% of cases)* → [14] Claim queue

* = Pure waste step
```

### Future State (8 steps)
```
[01] RCM platform flags case + surfaces inline: AI summary + top 3 modifier suggestions
     with confidence scores + secondary dx pre-populated from EMR
→ [02] Notification received with direct deep-link to case review screen
→ [03] Clinician reviews integrated view: summary + modifiers + secondary dx in one screen
→ [04] Clinician selects or confirms modifier (with high-risk OB flag if applicable)
→ [05] Clinician confirms secondary diagnosis (mandatory for flagged cases)
→ [06] Structured audit record auto-generated: modifier selected + dx confirmed + clinician ID
→ [07] Single-action charge submission — confirmation status displayed inline
→ [08] Charge queued for claim submission — API confirmation sent to EMR (no duplicate entry)
```

---

## How Each Waste Step Was Eliminated

| Eliminated Step | Solution | Constraint Satisfied |
|---|---|---|
| Step 03 — Navigate to queue | Deep-link in notification takes clinician directly to case | Zero Training (obvious), 2-Click Cap |
| Step 05 — External modifier lookup | Top 3 AI-suggested modifiers with confidence scores displayed inline | RCM platform API boundary (display layer only) |
| Step 07 — Navigate to EMR for secondary dx | Secondary dx pre-populated from EMR via existing API | RCM platform API boundary, EMR Neutrality |
| Step 10 — Duplicate EMR entry | API confirmation sent to EMR on submission — no manual entry | Duplicate Entry Elimination, EMR Neutrality |
| Step 11 — Free-text documentation | Replaced with structured confirmation fields (auto-generated audit record) | Compliance Audit Trail |
| Steps 12+13 — Billing rework loop | Structured modifier selection + confidence scoring reduces error rate from 22% to ~8% | Revenue Preservation |

---

## Constraint Conflict Log

One constraint conflict was identified and resolved during the design phase:

**Conflict:** The zero-training-budget constraint requires the modifier suggestion display to be self-explanatory. However, displaying confidence scores requires clinicians to understand what a confidence score means — which could be considered a training dependency.

**Resolution:** Confidence scores are displayed as a visual indicator (High / Medium / Review) rather than a percentage, with color coding. No interpretation training required. The label “Review” implies the clinician should verify — without requiring explanation of the underlying probability calculation.

---

*Output generated from waste analysis · See [future-state-sop.md](./future-state-sop.md) for the deployment-ready procedure*