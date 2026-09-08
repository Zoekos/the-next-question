# A worked example

What this looks like in practice, on a report with known problems.

The report in [`example/report.md`](example/report.md) is **synthetic** — invented for this purpose, with specific failures planted in it and specific parts deliberately made sound, so the review could be scored rather than admired. Everything below is the actual output from running the method over it.

---

## The situation

Lena is a senior researcher. She has just finished a churn study for a practice-management SaaS product: twelve interviews, three themes, four recommendations. It goes to the Q4 planning session on Tuesday, where two engineers get moved onto one thing or another.

She has the afternoon. She wants to know what someone would ask her in that room.

## What she does

Paste `SKILL.md` into Claude as a skill file, then:

> Review this report before it goes to a planning session on Tuesday. Follow the sixteen failure modes.

That's the whole prompt. The method carries the rest.

---

## What comes back

### First, it establishes what it's judging

> **What the artefact is.** A final report, going to a Q4 planning session on 14 October. Its audience is budget-holders, and it is the sole input to a live resource-reallocation decision — whether two engineers move off the reporting epic onto guided setup. Nothing in it gets a pass for being unfinished.

This matters. Run the same modes over rough working notes and half of them fire for no reason.

### Then the profile, by family

> **I · Wrong about who you learned from** — 1 exposed, 3 exposed, 2 unsure. The whole family is live.
> **II · Wrong about what you measured** — 4 ruled out, 5 ruled out, 6 not applicable. Clean.
> **III · Wrong about what it means** — 8 exposed, 9 exposed, 7 unsure.
> **IV · True but unfalsifiable** — 11 exposed, 12 unsure, 10 ruled out.
> **V · True but inert** — 13 exposed, 15 exposed, 16 exposed, 14 ruled out.

### Then the findings themselves

**Mode 1 · The Survivor Sample — exposed**

> "12 participants, drawn from our CRM: all currently on active Standard-tier subscriptions, all having logged in at least once in the previous 60 days." The research question is *why practices reduce seat counts or leave at renewal*. Nobody who reduced seats or left is in the sample.
>
> There are two coverage cuts, not one. The CRM cut removes the churned and the downgraded. The 60-day login filter then removes the dormant — who are the closest available proxy for the pre-churn state, and arguably the single most informative group for this question.
>
> **Go and get:** the CRM can count all three groups today. Six churned or downgraded practices would change the study's standing more than anything else on this list.

**Mode 13 · The Foregone Conclusion — exposed**

This is the one that would have cost her the meeting.

> "These map to the three pillars in the Practice Manager roadmap ... and to the four items already carried in the Q4 backlog." Four recommendations, four pre-existing backlog items.
>
> Worse: the decision rule agreed on 2 September made two of the recommendations **mutually exclusive** — if the driver is feature gaps, fund the reporting epic; if it is onboarding and habit, *stop the reporting epic* and move the engineers. The findings point at onboarding and habit. The report then recommends **both** branch outcomes, and never names which driver was dominant.
>
> **Go and get:** take the decision rule back to the decision-maker and state which branch the evidence triggers, before the session.

The report contradicted its own pre-agreed decision rule. Nobody had noticed — including the person who wrote the report *and* the person who planted the flaws.

**Mode 8 · The Borrowed Frame — exposed**

> The three themes are named Activation, Engagement, Expansion. The recommendations section states they map to the three roadmap pillars — and the fit is presented as a virtue rather than noticed as a risk.
>
> Is there one theme with no home in the organisation's vocabulary? Yes, exactly one, and what happened to it is the finding. The adviser material is the only section not carrying a pillar name, the only one in participants' framing, the only one with no denominator — and it sits outside the numbered theme structure entirely.

### And the modes it ruled out

This is the half that makes the rest worth reading.

> **4 · The Method's Shadow — ruled out.** Telemetry showed 8 of 12 never opened the template editor. An interview could not have produced that. *(An interview-only study fails this by construction — this one escapes it, which is worth saying out loud.)*
>
> **5 · The Rehearsed Answer — ruled out.** The load-bearing claim is anchored to logged behaviour, and where behaviour and self-report diverged the report flagged it as the finding rather than smoothing it.
>
> **10 · The Missing Decision Rule — ruled out, cleanly.** Dated, agreed with a named decision-maker before recruitment, three branches including a genuine "stop". Better than most studies manage.
>
> **14 · The Unowned Finding — ruled out.** Every recommendation carries a named individual and a decision date.
>
> **6 · The Prototype Effect — not applicable, declared.** No prototype, no task, no observed session. Stretched onto this material the mode produces a finding-shaped statement rather than a finding.

### Two it honestly couldn't settle

> Modes **2** and **7** need the transcripts, not just the report. Marked unsure, with what would settle them: session lengths and word counts by role, and a dissent census against the summary layer.

---

## What Lena does with it

Not sixteen fixes. Three, before Tuesday.

1. **Email the decision-maker** with the rule and which branch the evidence triggers. This is the difference between a report that informs a decision and one that gets nodded through.
2. **Add one line naming who the sample couldn't reach**, and the CRM count of them.
3. **Attach one cost-of-inaction number** to each recommendation, in seats or ARR.

Then a note in the report saying two modes remain open pending a transcript pass. Stating what you haven't checked is worth more than implying you checked everything.

---

## How well did it actually do?

Scored against the answer key: **six planted failures, six caught.** Four of the six deliberately-clean areas correctly ruled out; two marked unsure with honest reasoning rather than guessed. One mode correctly declared not applicable.

It also found two things the person who wrote the synthetic report had planted without noticing — the decision-rule contradiction, and a counter-case credited to one theme while quietly contradicting another.

And the honest limit, from an earlier run on a real government discovery: of sixteen verdicts, **eight were decided by the study's genre before the file was opened.** Those are the `(check)` modes. They are a competent checklist. The `(search)` modes are the ones that produce findings, and there are ten of them.

Expect roughly five real findings from a careful report. That is the honest expectation, and it is worth an afternoon.
