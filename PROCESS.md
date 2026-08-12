# The PROCESS — How I Built This Project

*Zina Lee, Product Manager*

---

## Why This Project Exists

Horizon answered the prioritization question. But a WSJF scorecard doesn't tell you how to actually change what 2,000 clinicians across 200 sites are doing day to day — that's a different problem, and it's one a lot of PMs underestimate, mostly because it doesn't look like a PM problem at first glance.

I've watched this pattern play out in complex operational environments more than once: a new system deploys, the metrics improve for the 85% of straightforward cases, and then the remaining 15% quietly becomes everyone's permanent headache because nobody standardized what happens at the edges. You don't fix that with another sprint. You fix it with process discipline — which is a genuinely different skill than product delivery, even though both live under "PM" on a resume.

If you haven't read [the README](./README.md) yet, start there. This page goes deeper into the same reasoning, including two implementation gaps that only get a passing mention over there.

---

## The Strategic Decisions I Made

### Why DMAIC Over a Simple Before/After Map

A swimlane diagram would have been faster to build and more immediately readable. I chose DMAIC (Define, Measure, Analyze, Improve, Control) instead because it's a complete problem-solving structure, not just a documentation exercise — a swimlane shows you what the process looks like, but DMAIC forces you to measure it, diagnose the actual root cause, design the fix, and then design how the fix survives contact with reality. That last part, the Control phase, is where most process improvement work quietly goes to die, and including it here is the point, not an afterthought. It also happens to align closely with language a lot of process-improvement job postings already use — not the reason I chose it, but a nice side benefit of choosing the more rigorous option anyway.

### Why the Constraints Came Before the Prompt, Again

Same instinct as Horizon: the process constraints document got built before the analysis prompt did. The 2-click friction cap, EMR neutrality, the zero-training-budget rule — these are design requirements the future-state workflow has to satisfy to even be considered valid, not narrative color to set the mood.

The training-budget constraint ended up mattering more than any of the others. You cannot deliver live training at scale to 2,000+ clinicians across hundreds of partner sites — that's just an arithmetic fact of the org's structure. Which means every improvement has to be self-evident from the workflow itself. Nobody can rely on an email getting read or a webinar getting attended. That single constraint shaped the future-state SOP more than any other design principle in the project.

### Why Five Archetypes, Not One Generic Clinician

A high-volume urban academic hospitalist and a rural provider covering three sites for one weekend a month are dealing with fundamentally different pressures. And a veteran's failure mode isn't confusion — it's calculated distrust, earned across two decades of EHR vendors promising 'less work, less clicks' and delivering neither. That's a different problem to design for than a new hire who just doesn't know the workflow yet.

Building five distinct archetypes before running the analysis forces a specific, uncomfortable question at every step: does this fix actually work for all five, or just for whoever sits at the median? A redesign that satisfies three archetypes out of five isn't 60% done. It's a fix with a predictable adoption failure rate baked into the two sites that don't fit the profile it was built around.

### Why Waste Classification Has to Come First

The prompt is architected so the AI physically cannot propose a future state until the waste analysis is complete. That's deliberate, for the same reason DMAIC exists at all: the most common failure in process redesign is skipping straight to a fix before actually diagnosing what's driving the waste, and ending up with something that looks cleaner without solving the real problem underneath it.

---

## How I Directed the AI

The AI generated the 14-step current-state workflow narrative from scenario parameters and known platform/EMR integration patterns, applied the Lean 8 Wastes classification once I'd supplied the framework and archetype data, built the future-state SOP structure against the constraints I'd already defined, and formatted the rollout phasing based on change-management parameters I specified.

What I owned: choosing DMAIC as the governing framework in the first place, building the five archetype profiles and their specific friction patterns, setting all eight process constraints and their actual values, deciding this was a process problem rather than a product problem (a distinction that matters more than it sounds like it should), making EMR neutrality and the training-budget rule hard constraints rather than soft preferences, and the architectural call that waste classification has to precede redesign in the prompt's structure, not just in theory.

---

## Two More Gaps the Live Run Surfaced

The README covers the vendor feature dependency — the clearest example of a technically correct output that still isn't actually deployable. Two more gaps showed up in the same run, worth documenting because they're a different kind of catch.

**The duplicate EMR entry exception resolves on paper and creates 200+ open questions in practice.** The SOP handles the ambiguity with a clean instruction: ask your billing coordinator once, then follow whatever they say. That's technically correct and completely useless at scale — across 200+ partner sites, that instruction means 200+ site-level rules that someone still has to go surface, validate, and write down before the SOP can actually be applied consistently. The AI documented the exception protocol correctly. Executing it is a PM-owned data collection task, not something that resolves itself: one message to billing leads at every partner site, asking for a single yes/no on whether duplicate EMR logging is required there, a 30-day deadline, and the responses codified into a site-rules table that lives alongside the SOP. That converts 200+ ambiguous situations into one document anyone can actually look up.

**Archetype 5 isn't a training problem — it's rational skepticism wearing the label "resistant."** Calling this archetype "resistant" misframes what's actually happening. Skepticism toward new clinical technology claims is the professional default for experienced hospitalists, not a personality quirk belonging to a difficult minority. Eighteen years of EMR rollouts that promised efficiency and delivered documentation burden earns that skepticism honestly. A rollout plan built for willing adopters, with a special-handling track bolted on for the skeptics, has the actual ratio backwards — skeptics are the norm here, not the exception. The right adoption strategy identifies two or three respected, high-volume hospitalists per region willing to run the new workflow first and report their real numbers, backed by video documentation instead of live training, and it leads with peer-reported data over institutional mandate. Give skeptics something to evaluate on its merits, not something to comply with on schedule — and be honest that the old process stays faster right up until the new one is demonstrably faster in practice, not before.

---

## What I'd Do Differently With Real Data

Direct observation would come before interviews in a real engagement — the friction inventory here is built from archetype assumptions, and what people say they do in an interview and what they actually do at their desk are frequently two different things, especially for workarounds that have become habitual enough to feel invisible to the person doing them.

The 8.4-minute average time-on-task is a scenario estimate, not measured data. A real version of this project pulls that number from an actual time-motion study — direct observation or EMR audit log timestamps, not an assumption dressed up as a baseline.

And the constraints themselves deserve validation with actual clinicians before redesign starts, not after. The 2-click cap sounds like a reasonable design rule on its face, but clinicians might tell you the real problem was never the click count — it's the cognitive load of deciding *which* modifier to pick in the first place. Those are different problems requiring different fixes, and you only find out which one you're actually solving by asking the people doing the work, not by assuming the earlier analysis already covered it.

---

*This document reflects my actual decision-making process in building this project.*

*[Back to README](./README.md)*
