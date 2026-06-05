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