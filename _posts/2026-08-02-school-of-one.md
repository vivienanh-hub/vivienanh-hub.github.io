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

## The public layer

The private repo holds my personal data — memory files, session journals, career materials. This is the system design, stripped of personal content and forkable.

**[school-of-one on GitHub](https://github.com/vivienanh-hub/school-of-one)**

Install Claude Code, fork the repo, bring your own goals. The school is yours to enrol in.
