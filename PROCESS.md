# PROCESS.md — How I Built This Project

*By Zina Lee, Enterprise Product Manager*

---

## Why This Project Exists

Project Horizon answered the prioritization question. But a WSJF scorecard doesn't tell you how to change the behavior of 2,000 clinicians across 200 sites. That's a different problem — and one that many PMs underestimate.

I've seen this pattern in complex operational environments: the technology gets deployed, the metrics move in the right direction for 85% of cases, and then the last 15% becomes everyone's headache because no one standardized the exception process. You can't fix that with another sprint. You fix it with process discipline.

This project demonstrates that I understand the difference between a product problem and a process problem — and that I know which toolkit to reach for when the answer isn't another feature.

---

## The Strategic Decisions I Made

### Why DMAIC Over a Generic Process Map

I could have built a simple before/after swimlane diagram. It would have been faster and more visually immediate. I chose DMAIC for two reasons:

**1. It's a complete problem-solving structure, not just a documentation exercise.** A swimlane shows what the process looks like. DMAIC forces you to measure it, analyze root causes, design the improvement, AND design how you sustain it. The Control phase — the rollout plan — is where most process improvement projects fail. Including it here shows I know where the work actually ends.

**2. DMAIC aligns with the preferred qualifications in the target job description.** Lean Six Sigma is explicitly listed. Using DMAIC in a portfolio artifact signals methodology fluency in a way that a certification bullet point on a resume cannot.

### Why the Constraint-First Approach (Again)

Same principle as Project Horizon: I built the process constraints document before writing the analysis prompt. The 2-click friction cap, the EMR neutrality requirement, the zero-training-budget constraint — these are design requirements, not narrative context. The future-state workflow has to satisfy them before it can be considered valid.

The zero-training-budget constraint is the most consequential one. In a distributed organization with 2,000+ clinicians across hundreds of partner hospitals, you cannot deliver live training at scale. This means every improvement must be self-evident from the workflow itself. You can't rely on people reading an email or attending a webinar. This single constraint shapes the future-state SOP more than any other design principle.

### Why Five Archetypes Instead of a Generic Clinician Profile

Process improvement fails when it's designed for the average user and deployed to everyone. A high-volume urban academic center hospitalist has fundamentally different workflow pressures than a rural critical access clinician covering three sites. A new hire has different failure modes than an 18-year veteran.

Building five distinct archetypes before running the analysis forces both me and the AI to ask: does this improvement actually work for all of them, or just for the median case? Any future-state design that only satisfies three out of five archetypes is a partial fix with a predictable adoption failure rate at the sites that don't fit the median.

### Why Waste Classification Must Precede Redesign

The process analysis prompt is architected so the AI cannot propose a future state until the waste analysis is complete. This is deliberate. The most common failure mode in process redesign is jumping to solutions before diagnosing root causes — producing a workflow that looks cleaner but doesn't actually address the structural problems driving waste.

For example: the obvious fix for the modifier code lookup problem (Step 05, 2.4 min average) is to embed a reference list in the RCM platform screen. But the waste analysis reveals that the deeper problem isn't the absence of a reference — it's that clinicians don't trust RCM platform's AI-suggested code enough to accept it without independent verification (Archetype 5). A reference list doesn't fix a trust problem. A confidence score display does. You only arrive at that solution through the analysis, not the shortcut.

---

## How I Directed the AI

### What the AI Did
- Generated the 14-step current-state workflow narrative based on scenario parameters and known RCM platform/EMR integration patterns
- Applied the Lean 8 Wastes classification to each friction point once I provided the framework and archetype data
- Generated the future-state SOP structure based on the constraints I defined
- Formatted the rollout plan phasing based on change management parameters I specified

### What I Decided
- The choice of DMAIC as the governing framework
- The five archetype profiles and their specific friction patterns
- The eight process constraints and their specific values
- The determination that this is a process problem, not a product problem
- The decision to make EMR neutrality and zero-training-budget hard constraints
- The architectural rule that waste classification must precede redesign in the prompt
- The framing and narrative of every public-facing document

---

## What Happened When I Actually Ran It

The prompt ran cleanly. All eight constraints passed, the waste classification was consistent with the mock, and the future-state SOP is technically deployable as written. If the goal were to evaluate whether the prompt works, the answer is yes.

But a PM looking at this output doesn't stop there.

### The SOP is the easy part

The prompt produced a correct answer to a bounded problem: given this workflow, these friction points, and these constraints, generate a future-state SOP. It did that well. What it cannot do is deploy the SOP — and deployment is where the actual work lives.

Three implementation problems the output doesn't address:

**The embedded modifier reference panel requires a vendor product change.** The single highest-leverage fix in the future-state design — embedding modifier lookup directly in the RCM platform review screen — is not a configuration change. It requires the vendor to build a feature. The prompt assumes it's in scope because it stays within the API display layer. A PM knows that "technically in scope" and "vendor will prioritize this" are two different conversations, and only one of them shows up in an output document.

**The duplicate EMR entry exception is still 200+ open questions.** The SOP resolves the ambiguity with an instruction: ask your billing coordinator once, then follow that rule. Correct. But across 200+ partner sites, that's 200+ site-level rules that someone has to surface, validate, and codify before the SOP can be applied consistently. The AI documented the exception protocol. The PM has to execute it.

**Archetype 5 is an adoption problem, not a training problem.** The framing of "resistant clinician" is misleading — skepticism of clinical technology claims is the professional default for experienced hospitalists, not a personality trait of a difficult minority. Eighteen years of EMR implementations that promised efficiency and delivered documentation burden earns that skepticism. A rollout designed for willing adopters with a special-handling track for resistant ones will fail at scale, because it has the ratio backwards.

### What I Would Do Next

**On the vendor feature request:** Build the business case before the conversation. Time-on-task reduction × case volume × clinician cost per minute = a number the vendor's product team can take to their roadmap. Submit a formal feature request with that ROI attached, and establish a timeline commitment before publishing the SOP as fully deployed rather than in progress. An SOP that depends on a feature that doesn't exist yet is a roadmap item, not a deployment.

**On the duplicate EMR entry inventory:** This is a PM-owned data collection task, not a site-by-site project. Work through the billing coordinator network — one communication to billing leads at all partner sites, asking for a single yes/no response on whether their site requires duplicate EMR logging. Set a 30-day deadline. Codify the responses into a site rules table that lives alongside the SOP. This converts 200+ ambiguous situations into one document that every clinician can look up.

**On adoption:** The adoption strategy has to be built for skeptics, because skeptics are the norm. Eighteen years of EMR implementations that promised efficiency and delivered documentation burden is the starting position of most experienced clinicians — not an outlier. Identify two or three high-volume, respected hospitalists per region who are willing to run the new workflow and report their actual numbers. Give skeptics something to evaluate, not something to comply with. Peer reference over institutional mandate, demonstrated time data over projected time data, and an explicit acknowledgment that the old process was faster until the new one is proven faster in practice.

The prompt built the map. These three actions are how the PM gets 2,000 clinicians to use it.

---

## What I'd Do Differently With Real Data

**1. Direct observation before interviews.** The friction inventory is built from archetype assumptions. In a real engagement, I would spend time in clinical environments observing the actual workflow before designing the interview instrument. What people say they do and what they actually do are often different — especially for workarounds that have become habitual.

**2. Time-motion study.** The 8.4-minute average time-on-task is estimated from the scenario. Real measurement would use time-motion study data — either direct observation or timestamp analysis from the EMR audit log.

**3. Constraint validation with clinicians.** The 2-click friction cap sounds like a reasonable design constraint. But clinicians might tell you the real problem isn't the number of clicks — it's the cognitive load of deciding which modifier to select. Those are different problems with different solutions. Constraints should be validated with users before redesign begins, not just assumed from prior analysis.

---

*This document reflects my actual decision-making process in building this project.*
*[Back to README](./README.md)*