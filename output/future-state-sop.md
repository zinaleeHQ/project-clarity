# Output: Future-State Standard Operating Procedure

---

## Standard Operating Procedure
### RCM platform Manual Charge Review â Optimized Workflow

**Document ID:** SOP-COMM-001
**Version:** 1.0
**Effective Date:** [Sprint 2 Go-Live Date]
**Owner:** Product Management Â· Clinical Operations
**Review Cycle:** Quarterly or upon RCM platform update
**Applies to:** All hospitalists performing manual charge review for non-autonomous RCM platform cases

---

### Purpose
To provide a standardized, efficient, and compliance-ready process for completing manual charge review when RCM platformâs autonomous coding engine requires clinician input.

### Scope
This SOP applies to all RCM platform non-autonomous cases (approximately 15% of clinical encounters) across all partner hospital sites. It is designed to function identically on Epic and Cerner EMR environments.

### Definitions
- **Non-Autonomous Case:** A clinical encounter where RCM platformâs AI engine has determined that human review is required before a charge code can be submitted
- **Modifier Code:** A CPT modifier that provides additional context to a procedure code (e.g., indicating complexity, provider type, or clinical circumstance)
- **Confidence Score:** RCM platformâs internally calculated certainty level for each suggested modifier, displayed as High / Medium / Review
- **Structured Audit Record:** An automatically generated, queryable record capturing: modifier selected, secondary diagnosis confirmed, and clinician ID

---

### Procedure

| Step | Role | Action | System | Expected Outcome |
|---|---|---|---|---|
| **1** | RCM platform AI | Flags case as non-autonomous and sends notification with direct case link | RCM platform | Clinician receives notification with single-click access to case |
| **2** | Hospitalist | Opens notification and clicks case link | Mobile / Desktop | RCM platform case review screen opens directly â no queue navigation required |
| **3** | Hospitalist | Reviews integrated case view: AI clinical summary, top 3 modifier suggestions with confidence scores (High/Medium/Review), and pre-populated secondary diagnosis | RCM platform | Clinician has all required information in one screen without switching systems |
| **4** | Hospitalist | Selects the appropriate modifier code from the displayed options. *If none of the suggestions are appropriate, use the âManual Entryâ field and document reason.* | RCM platform | Modifier selection recorded. **High-risk OB flag:** If case is tagged OB-High-Risk, Step 5 is mandatory before proceeding. |
| **5** | Hospitalist | Confirms or corrects pre-populated secondary diagnosis. *Mandatory for all OB-High-Risk flagged cases. Optional (but recommended) for all others.* | RCM platform | Secondary diagnosis confirmed. Structured audit field auto-populated. |
| **6** | Hospitalist | Reviews auto-generated audit summary (modifier Â· diagnosis Â· clinician ID) and submits | RCM platform | Charge submitted. Submission confirmation displayed inline. API confirmation sent to EMR automatically. |
| **7** | Billing System | Receives structured charge data with modifier, diagnosis, and audit record | Billing | Claim enters submission queue. No manual billing coordinator review required for standard cases. |

**Total steps: 7 Â· Clinician actions: 4 Â· System transitions: 1 Â· Estimated time: 3â4 minutes**

---

### Decision Tree: Step 4 Modifier Selection

```
Are any of the 3 displayed modifier suggestions marked âHighâ confidence?
âââ YES â Select the High confidence suggestion. Proceed to Step 5.
âââ NO â Are any suggestions marked âMediumâ confidence?
           âââ YES â Review clinical summary. Select the most clinically appropriate Medium suggestion.
           âââ NO (all âReviewâ) â See Exception Protocol A below.

Is the case tagged OB-High-Risk?
âââ YES â Step 5 is MANDATORY. Do not submit without secondary diagnosis confirmation.
âââ NO â Step 5 is recommended. Proceed to Step 6 if secondary diagnosis is not in question.
```

---

### Exception Protocols

**Exception A â All Modifier Suggestions Marked âReviewâ**
1. Select the modifier that most closely matches the clinical encounter from the Manual Entry field
2. Document reason for manual selection in the structured reason field (dropdown: *Suggestions unclear / Clinical complexity / Other*)
3. Submit normally â case will be flagged for billing coordinator review within 24 hours
4. *Do not delay submission â pending review is preferable to no submission*

**Exception B â Connectivity Timeout**
1. If the submission times out, RCM platform will display: *âSubmission status unknown â check queue before resubmittingâ*
2. Return to the case queue and verify whether the case shows status âSubmittedâ or âPendingâ
3. If status is âSubmittedâ â no action required
4. If status is âPendingâ â resubmit from the case view
5. *Never resubmit without checking status first â duplicate submissions will be automatically flagged*

**Exception C â OB-High-Risk Case with Diagnostic Uncertainty**
1. Do not submit without secondary diagnosis confirmation
2. If secondary diagnosis cannot be confirmed from the pre-populated EMR data, consult the attending record or escalate to clinical lead
3. Document the escalation in the reason field before submitting
4. *Patient safety takes precedence over processing speed in all OB-High-Risk cases*

---

### Compliance Requirements

Every completed manual charge review automatically generates a structured audit record containing:
- Modifier code selected
- Secondary diagnosis: confirmed (Y/N)
- Confidence level of selected modifier (High/Medium/Review/Manual)
- Manual entry reason (if applicable)
- Clinician ID and timestamp
- Submission status

This record is queryable by compliance and billing teams without requiring interpretation of free-text notes.

---

### Version History

| Version | Date | Change Summary | Author |
|---|---|---|---|
| 1.0 | June 2026 | Initial release â replaces undocumented current-state process | Z. Lee, PM |

---

*Deployment-ready artifact generated from Lean waste analysis and future-state design Â· See [value-stream-map.md](./value-stream-map.md) for full before/after analysis*