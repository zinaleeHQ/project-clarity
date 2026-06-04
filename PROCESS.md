# PROCESS.md — How I Built This Project

*By Zina Lee, Enterprise Product Manager*

---

## Why This Project Exists

Project Horizon answered the prioritization question. But a WSJF scorecard doesn’t tell you how to change the behavior of 2,000 clinicians across 200 sites. That’s a different problem — and one that many PMs underestimate.

I’ve seen this pattern in complex operational environments: the technology gets deployed, the metrics move in the right direction for 85% of cases, and then the last 15% becomes everyone’s headache because no one standardized the exception process. You can’t fix that with another sprint. You fix it with process discipline.

This project demonstrates that I understand the difference between a product problem and a process problem — and that I know which toolkit to reach for when the answer isn’t another feature.

---

## The Strategic Decisions I Made

### Why DMAIC Over a Generic Process Map

I could have built a simple before/after swimlane diagram. It would have been faster and more visually immediate. I chose DMAIC for two reasons:

**1. It’s a complete problem-solving structure, not just a documentation exercise.** A swimlane shows what the process looks like. DMAIC forces you to measure it, analyze root causes, design the improvement, AND design how you sustain it. The Control phase — the rollout plan — is where most process improvement projects fail. Including it here shows I know where the work actually ends.

**2. DMAIC aligns with the preferred qualifications in the target job description.** Lean Six Sigma is explicitly listed. Using DMAIC in a portfolio artifact signals methodology fluency in a way that a certification bullet point on a resume cannot.

### Why the Constraint-First Approach (Again)

Same principle as Project Horizon: I built the process constraints document before writing the analysis prompt. The 2-click friction cap, the EMR neutrality requirement, the zero-training-budget constraint — these are design requirements, not narrative context. The future-state workflow has to satisfy them before it can be considered valid.

The zero-training-budget constraint is the most consequential one. In a distributed organization with 2,000+ clinicians across hundreds of partner hospitals, you cannot deliver live training at scale. This means every improvement must be self-evident from the workflow itself. You can’t rely on people reading an email or attending a webinar. This single constraint shapes the future-state SOP more than any other design principle.

### Why Five Archetypes Instead of a Generic Clinician Profile

Process improvement fails when it’s designed for the average user and deployed to everyone. A high-volume urban academic center hospitalist has fundamentally different workflow pressures than a rural critical access clinician covering three sites. A new hire has different failure modes than an 18-year veteran.

Building five distinct archetypes before running the analysis forces both me and the AI to ask: does this improvement actually work for all of them, or just for the median case? Any future-state design that only satisfies three out of five archetypes is a partial fix with a predictable adoption failure rate at the sites that don’t fit the median.

### Why Waste Classification Must Precede Redesign

The process analysis prompt is architected so the AI cannot propose a future state until the waste analysis is complete. This is deliberate. The most common failure mode in process redesign is jumping to solutions before diagnosing root causes — producing a workflow that looks cleaner but doesn’t actually address the structural problems driving waste.

For example: the obvious fix for the modifier code lookup problem (Step 05, 2.4 min average) is to embed a reference list in the Commure screen. But the waste analysis reveals that the deeper problem isn’t the absence of a reference — it’s that clinicians don’t trust Commure’s AI-suggested code enough to accept it without independent verification (Archetype 5). A reference list doesn’t fix a trust problem. A confidence score display does. You only arrive at that solution through the analysis, not the shortcut.

---

## How I Directed the AI

### What the AI Did
- Generated the 14-step current-state workflow narrative based on scenario parameters and known Commure/EMR integration patterns
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

## What I’d Do Differently With Real Data

**1. Direct observation before interviews.** The friction inventory is built from archetype assumptions. In a real engagement, I would spend time in clinical environments observing the actual workflow before designing the interview instrument. What people say they do and what they actually do are often different — especially for workarounds that have become habitual.

**2. Time-motion study.** The 8.4-minute average time-on-task is estimated from the scenario. Real measurement would use time-motion study data — either direct observation or timestamp analysis from the EMR audit log.

**3. Constraint validation with clinicians.** The 2-click friction cap sounds like a reasonable design constraint. But clinicians might tell you the real problem isn’t the number of clicks — it’s the cognitive load of deciding which modifier to select. Those are different problems with different solutions. Constraints should be validated with users before redesign begins, not just assumed from prior analysis.

---

*This document reflects my actual decision-making process in building this project.*
*[Back to README](./README.md)*