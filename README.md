# AI-Assisted Job Search Workflow (Human-in-the-loop)

English | [中文](README.zh-CN.md)

> A job search process where AI handles breadth and record-keeping, and I make the judgement calls and submit every application myself.
> Tools: Claude (conversation + scheduled tasks), Gmail (job alert emails), Notion (job tracker / resume library / interview log).
> Target roles: Product Manager / Product Owner first, Business Analyst second; Sydney.

---

## Overview

```
 ① Positioning & master resume ──► ② Daily AI screening + scoring ──► ③ Human review ──► ④ Tailor & apply ──► ⑤ Follow-up & weekly review
            ▲                                  ▲                              │                                        │
            │                                  └────── screening rules ◄──────┘                                        │
            └───────────────────────────────── resume / direction adjustments ◄────────────────────────────────────────┘
```

Compared with my original four-step process, this version makes three improvements:

1. **Positioning before searching.** Target roles, salary range and hard exclusions are written down before any search starts, so the AI scores against clear criteria instead of "this looks close enough".
2. **Human review becomes rules.** Every time I keep or delete a role, I give a one-line reason. The AI turns those reasons into written screening rules, so precision improves the more the system is used.
3. **A closed loop.** Applications get follow-up reminders and a weekly review. Response rates by role type and resume version feed back into my direction and my resume.

---

## ① Positioning & master resume (one-off, updated as needed)

**What I do**
- Walk Claude through each past role: what I did, what I owned, and the measurable results.
- Confirm role priorities, salary expectations and acceptable contract types.

**What Claude does**
- Builds a **master resume (fact base)** holding every role, project and metric. All tailored versions are selected and rewritten from it; nothing new is invented.
- **Localises my overseas (China tech) resume for the Australian market:**
  - Two pages maximum, reverse-chronological, no photo, age or marital status.
  - Every bullet follows "action + scope + quantified result", e.g. "Cut the upload flow from 5 steps to 3, lifting daily UGC by 46%".
  - Adds one line of context for companies local recruiters may not know (company scale, product user base) so the experience reads at its true weight.
  - Australian English spelling (optimise, organisation, etc.) and a clear work rights statement (no sponsorship required) in the header.
  - Job titles and dates kept consistent across resume, LinkedIn and cover letters.
- Maintains **branch versions** per direction: PM/growth, community management, Chinese social media marketing, retail part-time, and so on.

**Output:** master resume plus branch versions, stored in the Notion resume library.

---

## ② Daily AI screening + scoring (automated, every morning)

**Sources**
| Source | How roles are collected | Picks per day |
|---|---|---|
| LinkedIn | LinkedIn Job Alert emails (subscribed for PM / PO / BA and related roles) | 10 |
| Seek / Indeed | Seek recommendation emails + Indeed search | 10 |

The two groups never overlap; each role appears only once.

**Hard filters (never picked)**
- Posted more than 2 weeks ago, or already taken down.
- Requires managing a team or direct reports.
- Deep machine learning, RAG or model fine-tuning engineering roles.
- Names specific tools I haven't used, or requires multiple years in banking, healthcare or automotive, or a professional licence.
- "PM in name only" roles that relay tasks or coordinate delivery without real business ownership.

**Scoring (modelled on an HR first-pass screen, out of 100)**
| Dimension | Weight | What it looks at |
|---|---|---|
| Background relevance | 35 | Overlap between core JD responsibilities and my experience (product growth, creator/community products, AI products, data-driven decisions) |
| Company growth | 20 | Company stage, funding/growth, team stability |
| Competitiveness | 25 | How well I meet the hard requirements, years of experience, any obvious gaps |
| Freshness | 20 | More recent postings and fewer applicants score higher |

Roles scoring below 65 are not added. **Quality over quantity:** if fewer than 10 roles qualify on a given day, only the qualifying ones are added.

**Written to the Notion job tracker**, each with: title, company, location, salary, link, posting date, source, match score, strengths, gaps and advice, recommended resume version, a one-line verdict, and status "To review".

---

## ③ Human review (about 10 minutes a day)

**What I do**
- Go through the day's "To review" roles and decide on each one:
  - **Want to apply** → change the status, or tell Claude in the chat.
  - **Not a fit** → delete it, with a one-line reason (e.g. "this is really delivery coordination", "needs 5 years in finance").

**What Claude does**
- Never recommends a deleted role again.
- **Turns my reasons into new screening rules** and adds them to the hard filters or scoring criteria. This is how prompt refinement improves screening precision in practice: not a vague "be more accurate", but every piece of feedback becoming an actionable rule.
- Tracks **precision** weekly (roles I keep ÷ roles recommended) to see whether rule changes are working.

---

## ④ Tailor materials & apply

**What I do**
- For a chosen role, paste the full JD to Claude (the AI can't open LinkedIn / Seek pages directly).
- Review and edit Claude's drafts, then **submit the application myself**.

**What Claude does**
- Breaks down the JD into keywords, hard requirements and implicit expectations, and maps them against the master resume as "covered / needs emphasis / genuine gap".
- Generates a tailored resume and cover letter from the master resume, only reordering and rewording existing facts, never inventing experience.
- Drafts answers to application questions (why this company, relevant examples), reusing refined story material.
- Saves the final versions to the resume library and links them to the role.

**Principle:** Claude never submits applications or sends emails on my behalf, and never asks for any account password.

---

## ⑤ Follow-up & weekly review

**Automatic record-keeping (Claude)**
- When I say "applied", Claude sets the status to "Applied" and records the date and resume version used.
- Reminds me to follow up after 7–10 days without a response (e.g. a LinkedIn message to the hiring contact).
- Once interviews start, logs rounds, prep notes and likely follow-up questions in the interview log.

**Weekly review (together)**
- This week: roles recommended, kept, applied, responses, interviews.
- Response rate by role type and resume version; directions or versions with low response rates are adjusted and fed back into steps ① and ②.

---

## Notion structure

| Database | Purpose |
|---|---|
| Job tracker | All roles; status: To review → Applied → Interviewing → Offer / Rejected |
| Resume library | Master resume, branch versions, and the tailored resume and cover letter for each role |
| Interview log | Interview rounds, questions, reflections |

---

## What I've had Claude do

- Mapped out my past experience, built the master resume, localised it for Australia, and maintained 8 branch versions (PM/growth, community management, brand reputation, Chinese digital communications, automotive community, short-video marketing, retail part-time, general).
- Built the Notion job-tracking system (job tracker, resume library, interview log), adding fields for posting date, source, recommended resume and one-line verdict.
- Set up a daily 7:52am (Sydney time) scheduled screening task: 10 LinkedIn + 10 Seek/Indeed roles, scored HR-style and added to the tracker.
- Continuously updated the screening rules from my feedback (only PM roles with real business ownership, only roles posted within 2 weeks and still open, delete and never re-suggest roles under 65 or with unmet hard requirements).
- Guided me through setting up my LinkedIn email and job alerts myself, so alert emails can be read automatically.
- Tailored resumes, cover letters and application answers for specific roles, and prepared interview follow-up questions.
- Recorded application progress and follow-up actions.

---

## Next improvements

- **Story bank:** keep frequently used STAR examples (e.g. the creator-tool upload flow redesign, the 0-to-1 AI property search product) in their own table, ready for applications and interviews.
- **Company watchlist:** for companies I especially want to join, check their careers pages regularly instead of waiting for alerts.
- **Closing skill gaps:** turn gaps that keep showing up in reviews (e.g. SEO, GA4) into a learning plan, and update the master resume once they're covered.
