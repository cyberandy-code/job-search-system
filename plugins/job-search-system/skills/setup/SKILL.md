---
name: setup
description: First-run setup for the job search system. Use when someone installs the plugin, says "set up my job search", or has no job search profile yet. Reads their resume, interviews them about targets and rules, connects their apps, and creates the profile, tracker and daily scout.
---

# Set up the job search system

The goal is a working system in one sitting: a profile Claude can judge roles against, a tracker, a folder for application records, and a daily scout. Work through the steps in order. Ask questions in small batches (three to five at a time, multiple choice where possible), never one long form.

## 1. Read the resume

Ask the person to upload their current resume (PDF or Word). Read it fully. Draft, for them to confirm or correct:
- A one-paragraph career summary in plain words.
- Each role: employer, title, dates, location, and two or three concrete accomplishments taken from the resume.
- Credentials, certifications, memberships, and education.

Never add facts that are not in the resume or that the person did not say. Mark anything uncertain as a question.

## 2. Interview for targets and rules

Cover these, then write the answers back as a summary for them to confirm:

**Targets**
- Primary lane (the kind of role they most want) and two to four acceptable adjacent lanes.
- Seniority: titles and levels that fit, and what is too junior or too senior.
- Roles and industries to avoid (for example staffing-agency contracts, hands-on coding roles).

**Hard filters**
- Location: fully remote in their country, and/or hybrid or onsite near a named city.
- Base pay floor. Rule: the top of a posted range must meet the floor; if pay is not posted, include only when the level clearly implies it.
- Employer health (for example: solid or growing companies only).

**Honesty guardrails**
- Things the resume must never claim, and exact wording for sensitive items (titles, clearances, internships, skills they want kept off the skills list).
- Skills they hold at working level only.

**Resume format**
- One page or two. Date alignment (left or right). Section order. Whether to include a summary.
- File naming pattern (default: Lastname_Resume_MonDDYYYY).

**Application defaults**
- Work authorization, sponsorship, location answer, how they want demographic questions answered, whether to write cover letters only when asked, salary-field approach.

## 3. Connect apps

Installing the plugin does not connect anything, so walk them through it. Check which connectors are already available in the session before asking.
- **Gmail** (required): finds job alerts, application confirmations, rejections and interview requests. Read-only use; the system never sends email.
- **Google Drive** (recommended): stores the PDF sent and the job description for every application.
- **Claude Docs / Claude Sheets** (recommended): hosts the tracker. If it is not available, use a Google Sheet in their Drive instead.

If a connector is missing, tell them where to add it in their Claude settings and continue with what works. Never ask for passwords.

## 4. Create the profile

Write `Job Search Profile` (markdown) containing everything from steps 1 and 2, in these sections: Summary, Experience (verified facts), Credentials, Targets, Hard filters, Avoid, Honesty guardrails, Resume format, Application defaults. Save it where future sessions can read it: the Claude project they are working in if there is one, otherwise a Google Drive folder named `Job Search System`. Every other skill reads this file first.

## 5. Create the tracker

Create a spreadsheet named `Job Pipeline Tracker` with four tabs and header rows:
- **Pipeline:** Your call | Company | Role | Fit | Base pay | Location | Why it fits | Gaps (honest) | Contact to find | Posting | Found | Status
- **Screened out:** Company | Role | Why skipped | Posting | Checked
- **Applications:** Date applied | Company | Role | Lane | Fit | Salary entered | Referral | Channel | Job description | Resume sent | Furthest stage | Outcome | Outcome date | Notes | Confirmation email | Outcome email
- **Application answers:** Field | Answer | Notes (fill from step 2's application defaults)

Add dropdowns: Your call (Yes, No, Maybe, Already applied); Status (New, Resume ready, Submitted, Skipped, Closed); Fit (Strong, Medium, Stretch); Furthest stage (Applied, Recruiter screen, Assessment, Interview, Final round, Offer); Outcome (No response, In process, Rejected, Closed by employer, Withdrawn, Offer declined, Offer accepted).

Create a Google Drive folder `Job Applications` for per-application records.

## 6. Backfill past applications (optional)

Offer to read their Gmail for past application confirmations and outcomes and fill the Applications tab. For large histories, delegate the email reading to a helper agent and have it return structured rows. Match outcomes to applications by company and role; flag uncertain matches in Notes. Never guess a role that no email names.

## 7. Schedule the daily scout

If scheduled tasks are available in this session, offer to create a weekday morning task whose prompt runs the `scout` skill against the profile and tracker. Pick a time that suits them and confirm it. If scheduled tasks are not available, tell them to run `/scout` each morning.

## 8. Hand off

Show a short summary: what was created and where, which connectors are connected, when the scout runs, and the daily loop:
1. Scout adds roles to Pipeline.
2. They mark Yes or No.
3. `/tailor-resume` for each Yes.
4. They apply, then say "submitted" (or run `/log-application`).
5. Run `/analyze` after 20 to 30 new applications.
