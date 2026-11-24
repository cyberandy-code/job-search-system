---
name: log-application
description: Record a submitted job application with its exact resume and job description. Use when the person says "submitted", "I applied to X", or runs /log-application. Also use to update an application's stage or outcome when a recruiter replies.
---

# Log an application

Claude never submits applications. This skill records what the person submitted so they can prepare for a screening call and so trends can be analyzed later.

## When they say they submitted

1. Confirm which role and which resume file they sent. If they changed anything (a different resume, a cover letter, a referral, a salary entered, a written answer), ask for it.
2. In the Google Drive folder `Job Applications`, create a subfolder named `YYYY-MM-DD Company - Role`. Put in it:
   - The exact PDF they submitted.
   - A document `Job description - Company - Role` with the posting URL, team, location, pay, the full responsibilities and qualifications (note if the text is paraphrased rather than verbatim), any written answers they submitted, and short prep notes: the gaps an interviewer will probe and the experience that bridges each one.
3. Add a row at the top of the Applications tab: date applied, company, role, lane, fit, salary entered, referral, channel (for example Greenhouse, Workday, LinkedIn), links to the job description and resume files, Furthest stage = Applied, Outcome = In process, and notes.
4. Set the role's Status in the Pipeline tab to Submitted.
5. Read the new row back to confirm it landed, then tell them in one or two sentences what was saved and where.

## When there is news

When a recruiter reaches out, an assessment arrives, or a rejection comes in (they tell you, or you find it in Gmail):
- Update Furthest stage (Recruiter screen, Assessment, Interview, Final round, Offer) and Outcome with the date.
- Add a link to the email and a short note on what happened.
- For a screen or interview, open the application's job description document and offer a short prep brief from it.

Never change the Pipeline tab's Your call column or delete rows the person wrote.
