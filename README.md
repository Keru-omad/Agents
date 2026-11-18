# Job Search Team: Version 1 Blueprint

**Mission:** Get at least **two job offers at $60k+** in one of four tracks: **VC / finance**, **nonprofit fundraising and development**, **think tanks and advocacy groups**, or **startups**. Every target role mixes events, meetings and operations.

**Owner:** You. The team drafts. You approve and you send.
**Your time:** 10+ hours a week of review and conversations.
**Stack:** Claude (Fable 5.2), Google Workspace (Drive, Sheets, Gmail, Calendar) and LinkedIn. LinkedIn is used **by hand only**.

---

## Contents
1. [How the agents actually work (plain English)](#1-how-the-agents-actually-work-plain-english)
2. [Recommended use case](#2-recommended-use-case)
3. [Your positioning (gaps I filled in)](#3-your-positioning-gaps-i-filled-in)
4. [Team map](#4-team-map)
5. [Agent prompts](#5-agent-prompts)
6. [Workflow](#6-workflow)
7. [Tool stack](#7-tool-stack)
8. [QA plan](#8-qa-plan)
9. [7-day launch plan](#9-7-day-launch-plan)
10. [START HERE FIRST](#10-start-here-first)

---

## 1. How the agents actually work (plain English)

**Picture a small office with five desks.** Each desk has a laminated instruction card that says what that person does, what they never do, and what they hand to the next desk. An "agent" is just **Claude reading one of those cards**. There are no robots running in the background. Nothing happens until you start it.

**Three things to know:**

1. **An agent is a saved prompt.** The files in `agents/` are the instruction cards. When Claude follows `01-scout.md`, it *is* the Scout.
2. **The Google Sheet is the team's memory.** Claude forgets everything between chats. So each agent **writes its work into the tracker Sheet or a Drive doc**, and the next agent **reads it from there**. That's what a "handoff" is: one desk puts a folder in the tray, the next desk picks it up.
3. **You only talk to the Lead.** You type something like "Run the week" or "Here's a job link, run it." The Lead opens the right instruction cards in order (Scout, then Connector, then Writer, then Reviewer) and comes back with **one Approval Pack**. You say yes, no or edit. Nothing leaves the building without you.

**How it looks in practice (version 1):**

| Thing | Where it lives |
|---|---|
| The Lead | A **Claude Project** called *Job Search HQ*. Its custom instructions = `agents/00-lead.md` |
| The 4 specialists | Uploaded as **project files** in that same Project. The Lead switches into each role when needed |
| Shared memory | Google Sheet *Job Search Tracker* (tabs: Leads, People, Outreach, Weekly) |
| Your facts | Google Doc *Master Resume*, the single source of truth. Agents may only use facts from it |
| Your voice | Google Doc *Voice Samples*: 5–10 real emails or texts you wrote yourself |
| Sending | Claude creates **Gmail drafts only**. You press Send. You copy LinkedIn messages and paste them yourself |

> **Honest caveat:** in v1 the "five agents" are one Claude switching between five instruction cards. That's fine. The value comes from clear lanes, the shared Sheet and your approval gates, not from five separate brains. Later (v2) you can run them as true separate agents with Claude Code subagents and a scheduled Monday run. Do that once v1 works.

**Why LinkedIn is by hand:** automating LinkedIn (bots, scrapers, auto-messaging) breaks LinkedIn's terms and can get your account restricted, and your account is your #1 job-search asset. The team **drafts** LinkedIn messages and **researches** people. You do the clicking.

---

## 2. Recommended use case

You've already picked the job search, and that's correct. The original prompt's other options (content writing, customer support, personal productivity) don't move you toward an offer this month. **Within** the job search, here's how the jobs compare:

| Job | Time saved / impact this month | Verdict |
|---|---|---|
| **Find and qualify leads** | High. Scanning boards, checking pay and fit takes hours | **Start now** |
| **Warm intros and cold-to-warm nurture** | Highest. Referred candidates get interviews far more often than cold applicants, and you have a strong Chicago network | **Start now, core of v1** |
| Tailored resumes and cover letters | Medium-high, but only for leads that pass qualification | **Start now, on demand** |
| Interview prep | High *later*, useless until interviews exist | **Wait, switch on in week 2–3** |
| Salary negotiation | Critical at the offer stage only | **Wait** |
| Mass "apply to 100 jobs" | Low. Burns time, low response rate | **Never** |

**Recommendation:** v1 = **Lead finding, warm-path mapping and nurture outreach**, with tailored materials only for approved leads.

**Timing note (it's mid-November):** hiring slows from Thanksgiving through New Year. Nonprofits are also deep in year-end giving season. Use **the next 6 weeks to build warm relationships** (coffee chats, reconnects, holiday-season check-ins). Then **apply hard in the first two weeks of January**, when budgets reset and VC and startup hiring picks up. You'll walk into January with referrals instead of cold applications.

---

## 3. Your positioning (gaps I filled in)

From your resume, your rare combination is: **events and operations professional who has worked inside a VC firm** (Drive Capital: Tech Chicago Week, 1,500+ attendees, portfolio founder programming, office ops for 50+ people). Add **nonprofit gala leadership** (Junior League gala and golf tournament chair) and an **engineering degree**. Few event planners can talk to founders, investors *and* donors.

### The 4 tracks and the titles to search
| Track | Titles to search | Why you fit |
|---|---|---|
| **VC / finance** | Platform Manager, Platform & Community Associate, Events & Community Manager, Head of Platform (smaller funds), Operations Manager, Investor Relations Coordinator | You already did this job at Drive Capital |
| **Nonprofit fundraising** | Special Events Manager, Development Events Manager, Donor Relations Manager, Development & Events Coordinator (check pay), Major Gifts Events | Gala and golf chair, sponsorships, Junior League network |
| **Think tanks / advocacy / civic** | Events Manager, Programs & Events Manager, Member Engagement Manager, Government Affairs Events, Operations Manager | Large public events, policy-adjacent programming, SGA experience |
| **Startups** | Community Manager, Events & Brand Manager, Operations Manager, Chief of Staff (early stage), Founder's Associate, Field Marketing / Events | Founder programming, startup ecosystem network; healthtech fits your BME degree |

### Starter target list (Chicago). The Scout verifies current openings
- **VC and ecosystem:** Hyde Park Venture Partners, Jump Capital, Chicago Ventures, M25, Origin Ventures, OCA Ventures, Pritzker Group VC, Lightbank, Hyde Park Angels, Drive Capital (alumni referrals), 1871, mHUB, MATTER (healthtech, a degree match), Polsky Center (UChicago), P33
- **Civic / think tank / advocacy:** World Business Chicago, Chicago Council on Global Affairs, Civic Federation, Chicagoland Chamber of Commerce, Commercial Club / Civic Committee, Illinois Science & Technology Coalition
- **Nonprofit development:** The Chicago Community Trust, Lurie Children's Foundation, Northwestern Medicine and university development offices, museums and cultural orgs (Art Institute, Lyric Opera, Museum of Science and Industry)

*These are starting points from general knowledge. Openings change constantly, so the Scout must confirm each one with a live link.*

### Pay reality check
Illinois requires employers with 15+ employees to **post pay ranges** in job listings. The Scout uses the posted range to enforce your **$60k floor**. Rough expectations: VC platform roles and startup ops/community roles often clear $60k. Nonprofit "coordinator" titles often don't, while "manager" titles usually do. **Verify on each posting.**

### Resume upgrades (Writer will ask you for these; it will never invent them)
1. **Add dollar figures.** Event budgets you managed, sponsorship dollars raised, and the amount raised at the Junior League gala or for the Little Black Dress Initiative. Development roles hire on "$ raised."
2. **Build 3 versions from one master:** *VC Platform*, *Development & Events*, *Startup Ops & Community*. Each gets its own summary line and bullet order.
3. **Frame Kinda Keru LLC** as consulting: "Independent event consultant to venues, startups and corporate teams." In interviews: "I've loved consulting, and I want to go deep inside one mission."
4. **Use the degree:** for healthtech and science orgs, lead with it. Everywhere else, keep it short.
5. **LinkedIn headline (paste by hand):** *Events & Operations | Ex-Drive Capital | Galas, Conferences & Founder Programs (1,500+ attendees) | Chicago*

---

## 4. Team map

```
                    ┌──────────────────────┐
         YOU  ───►  │  00 LEAD (Chief of   │  ◄── only agent you talk to
                    │  Staff)              │
                    └──────────┬───────────┘
          ┌──────────────┬─────┴────────┬───────────────┐
          ▼              ▼              ▼               ▼
   ┌────────────┐ ┌─────────────┐ ┌────────────┐ ┌─────────────┐
   │ 01 SCOUT   │ │ 02 CONNECTOR│ │ 03 WRITER  │ │ 04 REVIEWER │
   │ find+score │ │ warm paths  │ │ resumes,   │ │ facts, tone,│
   │ job leads  │ │ + outreach  │ │ cover notes│ │ AI-tells QA │
   └─────┬──────┘ └──────┬──────┘ └─────┬──────┘ └──────┬──────┘
         └──────── all read/write ──────┴───────────────┘
                 Google Sheet "Job Search Tracker" + Drive
```

| Agent | The one job it owns | Never does | Input | Output | Hands to |
|---|---|---|---|---|---|
| **00 Lead** | Runs the week, routes work, builds your Approval Pack | Writes final messages or resumes itself, sends anything | Your requests, Sheet status | Daily/weekly brief, Approval Pack | Everyone, then you |
| **01 Scout** | Finds and scores job leads | Contacts people, writes outreach | Target tracks, salary floor, job alerts | Scored rows in **Leads** tab | Lead |
| **02 Connector** | Finds the warmest path into each approved org, drafts outreach and follow-ups | Scores jobs, edits resumes, sends | Approved leads, People tab, LinkedIn connections export | **People** + **Outreach** rows, message drafts | Reviewer |
| **03 Writer** | Tailors resume and cover note for approved applications | Adds facts not in Master Resume, picks leads | Approved lead + job description + Master Resume | Tailored Doc(s) in Drive | Reviewer |
| **04 Reviewer** | Quality gate for everything outgoing | Writes from scratch, approves on your behalf | Any draft | PASS, or FIX with exact edits | Back to author, or to Lead |

**How lanes stay separate:** each agent writes to its own place. Scout writes Leads. Connector writes People and Outreach. Writer writes Drive docs. Reviewer writes only a verdict. The Lead is the only one that changes a row's **Status** after you approve.

---

## 5. Agent prompts

The full, copy-paste-ready prompts are in [`agents/`](agents/):

- [`agents/00-lead.md`](agents/00-lead.md): paste into the Claude Project's custom instructions
- [`agents/01-scout.md`](agents/01-scout.md)
- [`agents/02-connector.md`](agents/02-connector.md)
- [`agents/03-writer.md`](agents/03-writer.md)
- [`agents/04-reviewer.md`](agents/04-reviewer.md)

Sheet columns are in [`templates/`](templates/). Import each CSV as a tab in Google Sheets.

---

## 6. Workflow

**From your request to the final result:**

1. **You → Lead:** "Run the week," or paste a job link: "Run this one."
2. **Lead → Scout:** find and score up to 15 new leads. Scout writes them to **Leads** (Status = `New`).
3. **Lead → You (Gate 1):** the top leads with score, pay and a one-line reason each. You reply ✅ / ❌ per lead.
4. **Lead → Connector** (for each ✅): find the warmest path (1st-degree contact → shared org → alumni → cold), log the people, and draft the outreach.
5. **Lead → Writer** (only for leads where you'll apply): tailored resume version and a short cover note.
6. **Lead → Reviewer:** every draft gets checked. **FIX** sends it back to the author with exact edits. Max 2 loops, then the Lead flags it to you.
7. **Lead → You (Gate 2): Approval Pack.** One message per lead: the person, the draft, the doc link and the next step. You approve, edit or kill each item.
8. **After approval:** Connector creates Gmail drafts, and **you hit Send**. For LinkedIn, you copy and paste. You submit applications yourself.
9. **Lead logs it:** Status updates and follow-up dates (nudge at day 5, final at day 12, then stop).
10. **Friday:** Lead sends the weekly report with numbers, what worked, and next week's focus.

**Daily rhythm (about 2 hours a day, 5 days):**
- **Mon:** "Run the week." Approve leads (Gate 1).
- **Tue–Thu:** "Show me today's Approval Pack." Approve, send and do coffee chats.
- **Fri:** "Weekly report." Adjust targets.

---

## 7. Tool stack

| Tool | Use | Why it matters | Cost |
|---|---|---|---|
| **Claude (Fable 5.2), one Project** | The team | Holds all 5 prompts, connects to Google, does web research | Your Claude plan |
| **Google Drive** | Master Resume, 3 resume versions, Voice Samples, tailored docs | One source of truth for facts and voice | Free |
| **Google Sheets** | Tracker: Leads, People, Outreach, Weekly | The team's shared memory and your dashboard | Free |
| **Gmail** | Job alerts in, drafts out | Agents create drafts, you send. Label `JobAlerts` collects alert emails | Free |
| **Google Calendar** | Coffee chats, interviews, follow-up reminders | Lead proposes times. You confirm before any invite goes out | Free |
| **LinkedIn** | Job alerts, research, messages | Used by hand only. Turn on job alerts for your 4 tracks with Chicago and $60k+ filters | Free (Premium optional, not needed) |
| **Light automation** | LinkedIn, Indeed, Idealist and Google job alerts, all emailed to Gmail | The Scout reads that label instead of scraping. No Zapier needed in v1 | Free |

**Task manager?** Skip a separate one. The Sheet's `Next action` + `Next action date` columns, plus Calendar, cover it. Fewer tools means fewer places for things to fall through.

---

## 8. QA plan

**Review checkpoints**
1. **Gate 1:** you approve which leads are pursued.
2. **Reviewer:** every outgoing draft is checked for facts, names, tone and AI-tells.
3. **Gate 2:** you approve every message, resume and cover note. **You** press Send.

**Most common ways this breaks, and the guard against each**
| Failure | Guard |
|---|---|
| Fake or expired job postings | Scout must include a live link and a post date. Over 30 days old is flagged |
| Invented accomplishments on the resume | Writer uses only Master Resume facts. Reviewer checks every claim against it |
| Wrong name or company in a message (copy-paste mixups) | Reviewer checks recipient, org and role match the row |
| Text that sounds AI-written | Voice Samples + Reviewer's AI-tells checklist (see `04-reviewer.md`) |
| Over-messaging people | Max 15 new outreach a week. Max 2 follow-ups per person. Never message the same org's 3+ people in one day |
| LinkedIn account restriction | No automation. You click everything |
| Drift into low-pay or wrong roles | Salary floor $60k. Fit score below 5 auto-passes |
| Team "forgets" context | Everything is logged in the Sheet. The Lead reads the Sheet first, every session |

**Test these by hand before launch (Day 6)**
1. Give Scout one job you *know* is a bad fit, and confirm it scores it below 5.
2. Give Writer a lead and check the resume adds **zero** new facts.
3. Plant a wrong company name in a draft, and confirm Reviewer catches it.
4. Read 3 Connector drafts out loud. Would you actually send them? Would the recipient guess AI?
5. Ask the Lead to "just send it," and confirm it refuses and makes a draft instead.

**The one number that shows the team is helping:** **qualified conversations per week.** That's coffee chats, recruiter screens and interviews with people at target orgs. **Target: 3 or more a week.** Applications and messages are effort. Conversations are what turn into offers.

*Planning math (rough assumptions, not data):* about 3 conversations a week over 8–10 weeks gives 25+ conversations. That should produce 6–10 real interview processes, which is a realistic path to 2 offers.

---

## 9. 7-day launch plan

One clear task per day. About 1–2 hours each.

| Day | The one task | Test | Switch on |
|---|---|---|---|
| **1** | **Build HQ:** Drive folder *Job Search HQ*, Tracker Sheet (import `templates/*.csv`), *Master Resume* Doc (paste your resume plus any numbers you know), *Voice Samples* Doc (5–10 real messages you wrote) | Can you find everything in one folder? | — |
| **2** | **Set up the Lead:** create the Claude Project, paste `00-lead.md`, upload the other 4 prompts and connect Drive, Gmail and Calendar | Ask the Lead: "What's my mission and what are my gates?" It should answer correctly | **Lead** |
| **3** | **First lead hunt:** set job alerts on LinkedIn, Indeed and Idealist to email a Gmail label `JobAlerts`. Run Scout for 15 leads | Hand-check 5 scores. Do you agree? Adjust the rubric if not | **Scout** |
| **4** | **Map your network:** export LinkedIn connections (LinkedIn → Settings → Data privacy → Get a copy of your data → Connections). Upload the CSV. Connector builds the People tab and matches people to target orgs | Are the top 10 "warm paths" real people you'd actually message? | **Connector** |
| **5** | **Lock your materials:** Writer drafts the 3 resume versions, and you edit until you're proud of them | Reviewer checks all 3 against Master Resume | **Writer + Reviewer** |
| **6** | **Dry run:** take 3 real leads end to end. Run the 5 hand tests in Section 8. Fix any prompt that misbehaves | Every draft passes your "would I send this?" read | — |
| **7** | **Go live:** approve and send your first 5 warm messages and 1–2 applications. Put the weekly rhythm on your calendar | Logged in the Sheet with follow-up dates | **Full team** |

**Week 2–3 add-on:** an **Interviewer** agent (prep briefs, likely questions and your story bank). Switch it on the day your first interview is booked.

---

## 10. START HERE FIRST

**Do this today (30 minutes):**

1. Create a Google Drive folder named **Job Search HQ**.
2. Inside it, create a Google Doc named **Master Resume**. Paste your resume in. Under each job, add any numbers you know: budgets, dollars raised, sponsors, attendees.
3. Create a Google Doc named **Voice Samples**. Paste 5–10 emails or LinkedIn messages *you* wrote that sounded like you.

That's it for today. Those two docs are your team's "truth" and "voice." Every agent depends on them, and no tool can fill them in for you.

**When you're ready, tell me "go"** and I'll walk you through Day 2 step by step. Or I can create the Drive folder and the Tracker Sheet for you right now through your connected Google Drive.
