---
layout: post
title: I built myself a private school. It runs on AI.
subtitle: A curriculum, tutors who know me, exams I can't cheat on, and a system that improves itself over time.
date: 2026-08-02
tags: [AI, learning, productivity, product-management]
comments: true
---

Not a course. Not a Notion dashboard. A school — one that keeps a record of what I actually know, and doesn't let me be the one who decides whether I passed.

This is what I wanted. I couldn't find it, so I built it.

---

## The problem with self-directed learning

Most self-directed learning fails in the same place: you consume, you don't retain. You take a course, feel smart for a week, and three months later the knowledge is gone. The issue isn't effort. It's that nothing is watching your patterns, holding you accountable, or pushing back when you've drifted from your goals.

Good schools solve this. A good teacher knows where you're weak, adjusts the curriculum, gives you exams you can't skip, and tells you the uncomfortable truth about your progress. That's expensive when it comes from a human. It turns out it doesn't have to be.

---

## How the school works

The system lives in a GitHub repository. It runs on [Claude Code](https://claude.ai/code) — Anthropic's AI agent that can read files, remember context, and execute workflows. Every learning activity is a GitHub Issue. Every agent is a custom slash command I designed for a specific purpose.

![How school-of-one runs: a monthly horizon scan feeds the curriculum; curriculum, exams, and calibration form a repeating loop that feeds back into next month's plan; a quarterly goal review checks the whole loop from above; Sheldon and Snape run it day to day.](/assets/img/school-of-one-diagram.svg)

**The tutors.**
`/sheldon` is the head of the school — a systematic thinker who facilitates structured inquiry, routes you to the right learning mode, and won't let you stay comfortable with vague thinking.
`/snape` is the demanding life coach. He asks the questions you've been avoiding — about your goals, your real target, whether the work you're doing actually serves the direction you said you wanted to go.

The characters aren't decoration. A named character holds a stance the model won't drift out of. "Be rigorous with me" degrades into agreeableness after four exchanges; Snape doesn't, because every response has to stay in character, and the character's whole job is to be unimpressed.

**The curriculum.**
A learning plan sets the knowledge domains. A structured log records every session: source, takeaway, what I applied it to. Not a reading list — a receipt of actual learning.

**The exams.**
`/exam` is a Socratic knowledge test. It won't give you the answer. It will probe until it finds the edge of what you actually know versus what you think you know. The distinction matters.

**But you're grading yourself.**
This is the first objection everyone has, and it's the right one. The AI writes the exam, the AI marks it, and you decide whether to sit it at all. What stops you from re-rolling until you pass, or quietly skipping the week?

Four things — and it's worth being clear about where they stop working.

The verdict is produced by a separate judge sub-agent, not by the tutor running the conversation. The tutor's voice wraps the result; it can't change it. The verdict is one of exactly two words — Pass or Fail. "Partial," "close," "solid attempt" are banned outputs, because a hedge is how a failed exam gets recorded as a pass. On a fail, the next attempt's question is posed in the same response — the exam doesn't stop and politely ask whether you'd like to try again, because that's the moment you'd take the exit. And every attempt is a comment on a GitHub issue, so attempt three is visibly attempt three, permanently.

Where it stops working: nothing physically forces you to run `/exam` at all. That's what the automation layer is for — a cron job files the issue and a watcher runs the skill headlessly, so the exam shows up whether or not you were in the mood. But if you decide to ignore it, you can. The honest claim isn't that cheating is impossible. It's that cheating requires a deliberate act you can watch yourself commit, and it leaves a record.

**The pattern feedback.**
This is the part that makes it a school instead of a pile of tools: `/weekly-review` tracks every exam result against a Spaced Retrieval Schedule. Pass, and the re-test date pushes out two or three weeks. Miss, and it pulls back in to about a week. Every topic carries its own date, so a strong week on one subject can't paper over a weak one on another. Nothing decays quietly — the schedule itself is the evidence of what you actually know versus what you passed once and forgot.

**The pattern layer.**
Zoom out from any single topic and the system builds a memory of you over time — your learning style, your recurring blind spots, where you tend to skip the hard part. A monthly `/calibrate` run reads everything and updates the system itself — adjusting how the tutors respond, what the curriculum should prioritise, where the gaps have opened up.

**The horizon scan.**
Once a month, `/horizon-scan` looks outward — what's moving in the field, what's noise, what warrants real attention. The output is Act / Watch / Noise triage. You stay current without drowning in feeds.

**The goal review.**
Every quarter, `/goal-review` — led by Snape — asks whether your north star has drifted, whether the work you're doing reflects what you said you wanted, and whether the targets need to change. Schools have graduation requirements. This is the checkpoint.

---

## Who this is for

Any serious learner in a fast-moving field. I built it for PM work and AI product management specifically, but the architecture isn't domain-locked. The tutors, exam engine, pattern memory, and curriculum tracker apply to anything you're trying to learn at depth — not just consume.

It runs on Claude Code, so you'll want to be comfortable enough with GitHub to clone a repo and edit a markdown file. Time-wise, think an hour a week for the review and a couple of exams, half an hour a month for the scan.

The real prerequisite is that you take your own learning seriously enough to design a system for it. Most people don't. That's fine. But if you've ever felt that you're working hard and still not retaining, still not progressing, still not sure whether you're pointed in the right direction — this is what I built instead of accepting that.

---

## How you'd actually use it

Four steps, roughly:

1. **Fork it.** [school-of-one](https://github.com/vivienanh-hub/school-of-one) is the public skill library — copy the `.claude/commands/` folder into your own workspace repo, or just fork the whole thing and work inside it.
2. **Tell it who you are.** Fill in a `CLAUDE.md` and a short goal file — your current target, your three-year direction, the life the career is meant to fund. Every skill reads this before it answers, so this file is what makes the advice specific to you instead of generic.
3. **Start with `/sheldon`.** Ask it something you're actually stuck on — it routes you to `/learn`, `/exam`, or wherever the real work is.
4. **Wire up the schedule.** `/horizon-scan` monthly, `/weekly-review` weekly, `/goal-review` quarterly, `/calibrate` in between — none of that happens on its own unless something makes it. The repo ships a small `automation/` layer for this: a queue script per skill plus a watcher process, so a cron job creates the GitHub issue and the watcher runs the skill headlessly, no one at the keyboard. Technically optional. In practice it's the difference between a system you remember to use and one that runs whether you remember or not.

Full setup — folder structure, GitHub labels, the exact files to fill in — is in [INSTALL.md](https://github.com/vivienanh-hub/school-of-one/blob/main/INSTALL.md).

---

## A worked example: one quarter in the school

Mina is a product manager with five years in fintech. She wants to move into an AI PM role within the year and doesn't know where to start.

**Week 1 — she forks the repo and answers one hard question.**
Her goal file says: *Now Goal — AI PM role, fintech or B2B SaaS, within 12 months.* Then she opens with `/sheldon`: *"I want to become an AI PM. Where do I actually start?"* Sheldon doesn't hand her a reading list — he asks what she's already done with AI at work. Turns out: nothing, she's only used ChatGPT to draft emails. That becomes the real starting point, not the job title.

**Week 2 — the curriculum starts filling in.**
`/learn RAG and vector search`, then `/learn LLM evaluation design`. Each session logs a takeaway, not just a summary. Two weeks in, she has a working knowledge base instead of a stack of open browser tabs.

**Week 3 — the first exams, and the schedule starts tracking her, not just the topic.**
`/exam RAG` — no notes, no hiding behind "I read about it." She fails the first attempt and passes the second; that pass pushes RAG's re-test out three weeks. Same week, `/exam LLM evaluation design` — she fails it outright, and that topic's re-test pulls in to about a week. RAG doesn't move, because RAG isn't the shaky one. Two topics, two different signals, tracked separately instead of one vague "how's it going" feeling.

**Month 2 — the outside world shows up.**
Her first `/horizon-scan` flags that job descriptions in her target band now ask for "designing LLM evaluations," not just "AI-fluent." That routes straight into her learning plan — eval design moves from optional to priority. Then `/cv-job-match` runs her CV against three of those postings. It doesn't rewrite anything; it names what they ask for that her CV can't yet evidence. Between the two, the curriculum stops being a topic list and becomes a gap list.

**Month 3 — the system checks itself.**
Four straight weeks show a pattern: topics pass their first exam, then come back failed on the re-test a few weeks later. `/calibrate` reads that as recognition, not retention, and shortens the default first re-test window from three weeks to ten days — instead of letting the same gap resurface every month unnamed.

**Month 3, later — the first mock loop.**
`/interview` runs a scored round against a real posting. The score comes back lower than she expected — not for a wrong answer, but for one that named the right approach and stopped there: no metric, no threshold, nothing about what she'd do if the number came back bad. Fluent and unfalsifiable. Better to find that here than after a fourth application goes quiet. `/portfolio-capture` files the eval work she has actually done as a proof point, so the next CV pass has something concrete to point at.

**End of quarter — Snape.**
`/goal-review` asks the question she's been avoiding: has she actually applied to anything, or just kept studying? The answer reshapes her Now Goal for next quarter — less reading, more applying.

One person, one quarter, one full turn of the loop in the diagram above.

---

## The public layer

The private repo holds my personal data — memory files, session journals, career materials. This is the system design, stripped of personal content and forkable.

**[school-of-one on GitHub](https://github.com/vivienanh-hub/school-of-one)**

Install Claude Code, fork the repo, bring your own goals.

It won't make you learn faster. What it takes away is your ability to stay vague with yourself — the schedule knows which topics you've proved and which ones you've only read about, and it doesn't care how busy the week was. That's the entire point.
