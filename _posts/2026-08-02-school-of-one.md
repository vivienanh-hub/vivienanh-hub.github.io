---
layout: post
title: I built myself a private school. It runs on AI.
subtitle: A curriculum, tutors who know me, exams I can't cheat on, and a system that improves itself over time.
date: 2026-08-02
tags: [AI, learning, productivity, product-management]
comments: true
---

Not a course. Not a Notion dashboard. A school — with a curriculum, a tutor who knows me, exams I can't cheat on, and a system that watches my patterns and gets better at teaching me over time.

This is what I wanted. I couldn't find it, so I built it.

---

## The problem with self-directed learning

Most self-directed learning fails in the same place: you consume, you don't retain. You take a course, feel smart for a week, and three months later the knowledge is gone. The issue isn't effort. It's that nothing is watching your patterns, holding you accountable, or pushing back when you've drifted from your goals.

Good schools solve this. A good teacher knows where you're weak, adjusts the curriculum, gives you exams you can't skip, and tells you the uncomfortable truth about your progress. That's expensive when it comes from a human. It turns out it doesn't have to.

---

## How the school works

The system lives in a GitHub repository. It runs on [Claude Code](https://claude.ai/code) — Anthropic's AI agent that can read files, remember context, and execute workflows. Every learning activity is a GitHub Issue. Every agent is a custom slash command I designed for a specific purpose.

![How school-of-one runs: a monthly horizon scan feeds the curriculum; curriculum, exams, and calibration form a repeating loop that feeds back into next month's plan; a quarterly goal review checks the whole loop from above; Sheldon and Snape run it day to day.](/assets/img/school-of-one-diagram.svg)

**The tutors.**
`/sheldon` is the head of the school — a systematic thinker who facilitates structured inquiry, routes you to the right learning mode, and won't let you stay comfortable with vague thinking.
`/snape` is the demanding life coach. He asks the questions you've been avoiding — about your goals, your real target, whether the work you're doing actually serves the direction you said you wanted to go.

<div class="term-card"><div class="term-header"><span class="term-dot red"></span><span class="term-dot yellow"></span><span class="term-dot green"></span><span class="term-label">sheldon + snape</span></div><div class="term-body" markdown="1">
<span class="prompt">$</span> **/sheldon** what does it mean to be an AI PM in 2026?

Before I answer — what have you actually *shipped* that used AI, versus what have you *read about*? Those are different questions, and most people answer the second one when asked the first.

<span class="prompt">$</span> **/snape**

You said this quarter was about landing a Senior PM interview loop. It's week 9. Show me the applications — not the plan, the applications.
</div></div>

**The curriculum.**
A learning plan sets the knowledge domains. A structured log records every session: source, takeaway, what I applied it to. Not a reading list — a receipt of actual learning.

<div class="term-card"><div class="term-header"><span class="term-dot red"></span><span class="term-dot yellow"></span><span class="term-dot green"></span><span class="term-label">learn</span></div><div class="term-body" markdown="1">
<span class="prompt">$</span> **/learn** RAG and vector search

<span class="muted">Source logged. Takeaway: retrieval swaps "the model already knows" for "the model can look it up" — changes what you evaluate. Applied to: added to learning-plan.md under AI Product Fundamentals.</span>
</div></div>

**The exams.**
`/exam` is a Socratic knowledge test. It won't give you the answer. It will probe until it finds the edge of what you actually know versus what you think you know. The distinction matters.

<div class="term-card"><div class="term-header"><span class="term-dot red"></span><span class="term-dot yellow"></span><span class="term-dot green"></span><span class="term-label">exam · RAG</span></div><div class="term-body" markdown="1">
<span class="prompt">$</span> **/exam** RAG

Sheldon: Explain the core architecture of a RAG system — the three main components — then tell me what problem RAG solves that a vanilla LLM cannot. No notes.

<span class="muted">Pass. The retrieval → context injection → generation loop is correctly described. Minor note: you didn't name vector similarity search explicitly.</span>

<span class="muted">Progress file updated. Retrieval rep scheduled: re-test in 3 weeks.</span>
</div></div>

**The pattern layer.**
The system builds a memory of you over time. It knows your learning style, your knowledge gaps, your recurring blind spots. A monthly `/calibrate` run reads everything and updates the system itself — adjusting how the tutors respond, what the curriculum should prioritise, where the gaps have opened up.

<div class="term-card"><div class="term-header"><span class="term-dot red"></span><span class="term-dot yellow"></span><span class="term-dot green"></span><span class="term-label">calibrate</span></div><div class="term-body" markdown="1">
<span class="prompt">$</span> **/calibrate**

<span class="muted">Reviewed 6 weeks of sessions. Pattern: exams pass on first attempt, but retrieval reps get skipped before they're due. Adjusting: exam.md now schedules the rep before the topic goes cold, not after.</span>
</div></div>

**The horizon scan.**
Once a month, `/horizon-scan` looks outward — what's moving in the field, what's noise, what warrants real attention. The output is Act / Watch / Noise triage. You stay current without drowning in feeds.

<div class="term-card"><div class="term-header"><span class="term-dot red"></span><span class="term-dot yellow"></span><span class="term-dot green"></span><span class="term-label">horizon-scan · 2026-06</span></div><div class="term-body" markdown="1">
<span class="prompt">$</span> **/horizon-scan**

**Act** — Evaluation literacy in JDs: two VP-level roles now list "designing LLM evaluations" as a requirement, not a nice-to-have. Routed to learning-plan.md, priority: high.

**Watch** — "AI product experience" in 60% of senior PM JDs sampled; framing still loose.

**Noise** — Prompt caching guides. Already commoditized.
</div></div>

**The goal review.**
Every quarter, `/goal-review` — led by Snape — asks whether your north star has drifted, whether the work you're doing reflects what you said you wanted, and whether the targets need to change. Schools have graduation requirements. This is the checkpoint.

<div class="term-card"><div class="term-header"><span class="term-dot red"></span><span class="term-dot yellow"></span><span class="term-dot green"></span><span class="term-label">goal-review · Q2</span></div><div class="term-body" markdown="1">
<span class="prompt">$</span> **/goal-review**

Snape: Your Now Goal says "Senior PM, AI-fluent." Your last six weeks say "learning AI, not applying it." Which one is actually true — and if it's the second, is the goal wrong, or is the behaviour wrong?
</div></div>

---

## Who this is for

Any serious learner in a fast-moving field. I built it for PM work and AI product management specifically, but the architecture isn't domain-locked. The tutors, exam engine, pattern memory, and curriculum tracker apply to anything you're trying to learn at depth — not just consume.

The prerequisite is that you take your own learning seriously enough to design a system for it. Most people don't. That's fine. But if you've ever felt that you're working hard and still not retaining, still not progressing, still not sure whether you're pointed in the right direction — this is what I built instead of accepting that.

---

## How you'd actually use it

Three steps, roughly:

1. **Fork it.** [school-of-one](https://github.com/vivienanh-hub/school-of-one) is the public skill library — copy the `.claude/commands/` folder into your own workspace repo, or just fork the whole thing and work inside it.
2. **Tell it who you are.** Fill in a `CLAUDE.md` and a short goal file — your current target, your three-year direction, the life the career is meant to fund. Every skill reads this before it answers, so this file is what makes the advice specific to you instead of generic.
3. **Start with `/sheldon`.** Ask it something you're actually stuck on — it routes you to `/learn`, `/exam`, or wherever the real work is. Once you're in motion, the rest runs on its own schedule: `/horizon-scan` monthly, `/goal-review` quarterly, `/calibrate` rereading your patterns in between.

Full setup — folder structure, GitHub labels, the exact files to fill in — is in [INSTALL.md](https://github.com/vivienanh-hub/school-of-one/blob/main/INSTALL.md).

---

## The public layer

The private repo holds my personal data — memory files, session journals, career materials. This is the system design, stripped of personal content and forkable.

**[school-of-one on GitHub](https://github.com/vivienanh-hub/school-of-one)**

Install Claude Code, fork the repo, bring your own goals. The school is yours to enrol in.
