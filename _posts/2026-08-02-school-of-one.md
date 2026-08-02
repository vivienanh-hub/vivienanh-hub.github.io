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

**The curriculum.**
A learning plan sets the knowledge domains. A structured log records every session: source, takeaway, what I applied it to. Not a reading list — a receipt of actual learning.

**The exams.**
`/exam` is a Socratic knowledge test. It won't give you the answer. It will probe until it finds the edge of what you actually know versus what you think you know. The distinction matters.

**The pattern layer.**
The system builds a memory of you over time. It knows your learning style, your knowledge gaps, your recurring blind spots. A monthly `/calibrate` run reads everything and updates the system itself — adjusting how the tutors respond, what the curriculum should prioritise, where the gaps have opened up.

**The horizon scan.**
Once a month, `/horizon-scan` looks outward — what's moving in the field, what's noise, what warrants real attention. The output is Act / Watch / Noise triage. You stay current without drowning in feeds.

**The goal review.**
Every quarter, `/goal-review` — led by Snape — asks whether your north star has drifted, whether the work you're doing reflects what you said you wanted, and whether the targets need to change. Schools have graduation requirements. This is the checkpoint.

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

## A worked example: becoming an AI PM

Mina is a product manager with five years in fintech. She wants to move into an AI PM role within the year and doesn't know where to start.

**Week 1 — she forks the repo and answers one hard question.**
Her goal file says: *Now Goal — AI PM role, fintech or B2B SaaS, within 12 months.* Then she opens with `/sheldon`: *"I want to become an AI PM. Where do I actually start?"* Sheldon doesn't hand her a reading list — he asks what she's already done with AI at work. Turns out: nothing, she's only used ChatGPT to draft emails. That becomes the real starting point, not the job title.

**Week 2 — the curriculum starts filling in.**
`/learn RAG and vector search`, then `/learn LLM evaluation design`. Each session logs a takeaway, not just a summary. Two weeks in, she has a working knowledge base instead of a stack of open browser tabs.

**Week 3 — the first exam.**
`/exam RAG` — no notes, no hiding behind "I read about it." She fails the first attempt and passes the second. The failed attempt turns out to be the more useful entry in her learning log.

**Month 2 — the outside world shows up.**
Her first `/horizon-scan` flags that two VP-level job descriptions now require "designing LLM evaluations," not just "AI-fluent." That signal routes straight into her learning plan — eval design moves from optional to priority.

**Month 3 — the system checks itself.**
`/calibrate` notices a pattern: she passes exams on the first attempt but skips the spaced-retrieval reps before they're due. The exam skill adjusts, scheduling reps earlier so they don't slide.

**End of quarter — Snape.**
`/goal-review` asks the question she's been avoiding: has she actually applied to anything, or just kept studying? The answer reshapes her Now Goal for next quarter — less reading, more applying.

That's the loop from the diagram above, run by one person, over one real quarter.

---

## The public layer

The private repo holds my personal data — memory files, session journals, career materials. This is the system design, stripped of personal content and forkable.

**[school-of-one on GitHub](https://github.com/vivienanh-hub/school-of-one)**

Install Claude Code, fork the repo, bring your own goals. The school is yours to enrol in.
