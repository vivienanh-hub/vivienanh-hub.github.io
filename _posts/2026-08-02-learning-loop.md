---
layout: post
title: In order to help me learn, it had to understand me well
subtitle: A study system that plans my week, watches how I answer, and names the patterns I couldn't see in myself. Built with Claude Code, still being tuned.
date: 2026-08-02
tags: [AI, learning, productivity, product-management]
comments: true
---

I wanted a system to help me learn. And in order to help, it should understand me well.

I want it to understand my goals, my weaknesses, my strengths, and help me develop on those. Not a course, and not a reading list — those don't know anything about me. Something that knows where I'm going and what tends to stop me getting there.

## A week inside it

There's a long-term study plan, and from it I get an agenda every week.

It watches my movement every day through the week. Whether I worked on the assignment or not. How I answer. It assesses my answers, my thoughts, and my habits.

The weekly plan tells me exactly what to learn, and what I should test myself on. Then it asks a harder question: can I apply the knowledge to a practical scenario? Has what I studied or read actually become natural — has it become my knowledge?

That last distinction is the one the whole thing is built around. There's a difference between having read something and being able to use it, and I couldn't tell those apart on my own. So a topic I've passed an exam on sits at **studied, not applied** until I've spent it on a real product decision. Only then does it count as done.

The exams are closed-book, and I don't grade them myself. A separate judge sees the question, the marking notes, and my answer word for word — never the conversation that led up to it. The verdict is one of two words, Pass or Fail. "Partial" and "close" aren't allowed, because a hedge is how a failed exam gets filed as a pass.

![A topic moves from studied to studied-not-applied to complete, gated by a closed-book exam and then an applied exam, each graded by a separate judge with a binary Pass/Fail verdict.](/assets/img/learning-loop-ledger-flow.svg)

## Things I didn't know about myself

I've discovered many things I was unaware of before.

An avoidance pattern in disguise. Or that I correctly give the right category name and stop there, rather than going into the details.

Neither of those is something I could have told you about myself. Each individual instance looked reasonable. The system found them because it keeps a record: when a behaviour shows up across three or more sessions, it gets promoted from a session note into a named pattern with a row of its own, and the row tracks who noticed it — whether I caught it myself, whether a tutor named it for me, or whether I only found out when something went wrong. Here's a [fabricated example](https://github.com/vivienanh-hub/learning-loop/issues/2) of a weekly review catching that third occurrence and promoting it.

The tutors read that record before they say anything, which is why the advice isn't generic. One rule now tells the system to frame my learning deliverable as the artifact rather than the session, because the record showed I reliably finish sessions and don't produce artifacts. I didn't write that rule. The system proposed it and I approved it.

## Checking the goals, not just the progress

It goes beyond the weekly plan. A horizon scan helps me review my goals, and update what I should study, or update my knowledge.

That matters because everything else in the system only reads my own record, which is no use for noticing a goal has quietly gone stale. So once a month it looks outward instead — at how roles in my field are being described and what's shifting. Every signal gets one verdict, Noise or Watch or Act, and anything marked Act has to be routed somewhere concrete: a row in the study plan, a change to how I describe my work, or a question for the quarterly goal review.

![Four cadences: daily tracking, a weekly plan, a monthly outward scan, and a quarterly goal check — with what the monthly and quarterly cadences find routing back down into the weekly plan.](/assets/img/learning-loop-cadence.svg)

## A failure worth naming

The exam once graded me against a rubric it had invented on the spot — the topic had never actually been taught, so there was nothing real to grade against. That's the same failure mode as any AI judge with no grounded reference: it doesn't refuse, it confabulates a standard and grades you against that.

The fix was structural, not a patch. A topic with no lesson behind it now triggers teaching first, and a retrieval rep can't name a topic that was never taught.

## Who I think this is for

I think there are many self-taught learners, and lifelong learners, who would like virtual tutors that understand them well, keep them in check, and grow together with them. Who would like some discipline boost, and a learning system that keeps learning and improving.

If that's you, the repo is [on GitHub](https://github.com/vivienanh-hub/learning-loop) with setup in INSTALL.md. It's shaped around product management because that's my work, but nothing in the structure depends on the subject. Swap the study plan and it runs on anything.

Every session is a GitHub issue — the question in the body, labels for status and model, the verdict landing as a comment. Here's a [fabricated example](https://github.com/vivienanh-hub/learning-loop/issues/1) of one, closed-book exam included:

![A closed GitHub issue titled "[Exam] RAG — Attempt 1", labelled agent:status:done and model:sonnet, showing the exam question in the issue body, the answer and Pass verdict as comments below it.](/assets/img/learning-loop-issue-example.png)

## What isn't there yet

There's a dashboard for visualising progress that I'm working on. It isn't in this version.

And it's early — one person, a few months. Some of these loops have run only a handful of times, so I can tell you what the system does and what it has found, but not yet what it's worth over a year.
