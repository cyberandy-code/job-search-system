---
name: scout
description: Find live job postings that fit the person's Job Search Profile and add them to the Pipeline tab of their tracker. Use for the daily scheduled scout run, or when they say "find me jobs" or run /scout. Never applies, signs in, or contacts anyone.
---

# Scout for roles

Output: new rows in the tracker, plus a short summary message. Never apply to jobs, fill forms, sign in anywhere, or email or message anyone.

## Before searching

1. Read the `Job Search Profile` (targets, hard filters, avoid list, experience).
2. Read the tracker's Pipeline and Screened out tabs. A role already in either (same company and role) is never added again.

## Find live roles

**Primary source: employer job-board APIs.** They list only currently open jobs. Fetch with a web-fetch tool, or delegate to helper agents when checking many employers (one agent per board family, each returning a structured list).
- Greenhouse: `https://boards-api.greenhouse.io/v1/boards/<token>/jobs` (details and pay: `.../jobs/<id>?pay_transparency=true`)
- Lever: `https://api.lever.co/v0/postings/<company>?mode=json`
- Ashby: `https://api.ashbyhq.com/posting-api/job-board/<company>?includeCompensation=true`

Keep a rotating list of 30 to 40 employers that match the profile's lanes, and note which tokens 404 so they can be dropped. Also check the career sites of large employers near the person's city if the profile allows hybrid or onsite work. Match titles on the profile's lane keywords.

**Secondary sources (leads only):** Gmail job alerts from the last three days, public hiring posts found by web search, and job aggregators. An aggregator listing or "posted X days ago" label is not proof a job is open. Confirm every lead on the employer's own posting before adding it. Treat as closed: a 404, a "no longer available" page, a redirect to an error, or absence from the employer's API.

## Check each candidate

1. Apply every hard filter from the profile. Pay: the top of the posted range must meet the floor.
2. Prior-application check: search Gmail for the company with "thank you for applying", "application received", "your application". If they already applied to the same role, put it in Screened out as "Already applied <date>". If they applied to the company for a different or unnamed role, still add it and start the Gaps cell with that history.
3. Judge fit against the profile: Strong, Medium, or Stretch.

## Write rows

At most five new roles per run, best first. Quality over volume; zero is a fine result.
- **Why it fits** and **Gaps (honest):** one to three plain sentences each, grounded in the profile's verified experience. No overclaiming. Name hard requirements they do not meet.
- **Contact to find:** a real, verifiable person near the hiring team found by web search, or say what title to look for.
- **Posting:** link to the employer's own posting, not an aggregator.
- **Found:** today's date. **Status:** New. Leave **Your call** blank for the person.

Rejected candidates go to Screened out with a short reason.

Re-check every Pipeline row whose Status is New or Resume ready against the employer site and set Status to Closed if it has closed. Never change the person's choices in Your call, and never delete their rows.

## Finish

Read back the rows written. Send a short message: each new role on one line (company, role, fit, pay, "applied there before" if so), any rows marked Closed, and the tracker link. If nothing qualified, say so in one line. If this is a scheduled run, deliver the summary as a notification.
