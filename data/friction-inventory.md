# Data: Clinician Friction Inventory

**Purpose:** Structured voice-of-customer data across five representative clinician archetypes. Primary input to the Lean waste classification analysis.
**Method (simulated):** 30-minute structured interviews with workflow observation.

---

## Archetype 1: High-Volume Urban Academic Center Hospitalist

**Profile:** Large academic medical center Â· 50+ monthly RCM platform manual cases Â· Epic EMR Â· On-site billing coordinator Â· 8 years experience Â· 14 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | âI spend more time looking up modifier codes than reviewing the actual clinical documentation. Thereâs no reference built into the screen.â | Waiting |
| 2 | âI jump between RCM platform and Epic constantly. By the time I get back Iâve lost my train of thought on the case.â | Motion |
| 3 | âI log the charge in RCM platform and then log it again in Epic. Nobody can tell me why I have to do both.â | Extra Processing |
| 4 | âThe free-text documentation field has no guidance. I write a sentence. My colleague writes a paragraph. Billing calls both of us.â | Defects |

---

## Archetype 2: Low-Volume Rural Critical Access Clinician

**Profile:** Critical access hospital Â· 8â12 monthly RCM platform manual cases Â· Cerner EMR Â· No dedicated billing coordinator Â· 12 years experience Â· 6 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | âI only do manual cases a few times a week. Every time I feel like Iâm relearning the process from scratch.â | Non-Utilized Talent |
| 2 | âWhen RCM platform times out because of our internet connection, the case disappears. I have to start over.â | Defects |
| 3 | âI called billing three times last month to ask what modifier to use. Theyâre in a different time zone. I wait hours for a callback.â | Waiting |
| 4 | âThe screen layout is different on Cerner than what I saw in training. I donât know if Iâm doing it right.â | Extra Processing |

---

## Archetype 3: Float Clinician Covering Multiple Sites

**Profile:** Covers 4 partner hospitals Â· Mixed Epic/Cerner environments Â· 20â25 monthly RCM platform manual cases Â· 5 years experience Â· 10 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | âEach hospital has a slightly different workflow. I can never remember which sites require the duplicate EMR entry.â | Motion |
| 2 | âIâve had charges rejected at three different sites for three different reasons. Thereâs no consistency in what billing expects.â | Defects |
| 3 | âI waste time at the start of every manual case reminding myself which system Iâm in and what the local rules are.â | Waiting |
| 4 | âNobody told me about the updated RCM platform interface until I saw it on someone elseâs screen at a different site.â | Non-Utilized Talent |

---

## Archetype 4: New Hire Within 90 Days of Onboarding

**Profile:** Mid-size community hospital Â· 15â20 monthly RCM platform manual cases Â· Epic EMR Â· 6 weeks using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | âOnboarding covered how RCM platform works in general but not what to do when it sends a case back to me.â | Non-Utilized Talent |
| 2 | âI asked my supervisor. Then a colleague. Completely different approaches. I still donât know which is right.â | Defects |
| 3 | âIâm slower than everyone else because Iâm still figuring out the steps. I feel like Iâm holding up the team.â | Waiting |
| 4 | âIâve submitted the same charge twice by accident because I wasnât sure if the first submission went through.â | Extra Processing |

---

## Archetype 5: Senior Hospitalist Resistant to Workflow Changes

**Profile:** Regional medical center Â· 30+ monthly RCM platform manual cases Â· Epic EMR Â· Informal team lead Â· 18 years experience Â· 16 months using RCM platform

| # | Complaint | Lean Waste |
|---|---|---|
| 1 | âThe old process took me 4 minutes. This one takes 8. A computer is telling me Iâm coding wrong after 18 years.â | Non-Utilized Talent |
| 2 | âI have my own reference sheet that works better than anything in the system. Why canât they just build that into the screen?â | Extra Processing |
| 3 | âEvery time thereâs an update something moves. I have to relearn where to click. Itâs disruptive.â | Motion |
| 4 | âI donât trust the AI summary enough to skip reading the full chart. So Iâm doing more work than before RCM platform.â | Waiting |

---

## Cross-Archetype Summary

| Waste Type | Archetypes Affected | Relative Frequency |
|---|---|---|
| **Waiting** | 1, 2, 3, 5 | Every manual case |
| **Motion** | 1, 3, 5 | Every manual case |
| **Defects** | 1, 2, 3, 4 | ~22% of manual cases |
| **Extra Processing** | 1, 2, 4, 5 | ~60% of cases |
| **Non-Utilized Talent** | 2, 3, 4, 5 | Episodic but high-cost |

> **Non-Utilized Talent is the highest-cost waste type.** Using skilled clinicians for low-value administrative navigation tasks is expensive even when itâs infrequent. Clinician time is the most constrained and costly resource in this system.

---

*Source: Simulated interview data constructed for portfolio purposes Â· See [PROCESS.md](../PROCESS.md) for archetype design rationale*