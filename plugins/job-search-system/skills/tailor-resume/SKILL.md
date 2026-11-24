---
name: tailor-resume
description: Build an accurate, tailored resume for one job posting from the person's Job Search Profile. Use when they say "tailor my resume for X", mark a Pipeline role Yes, or run /tailor-resume. Gives an apply/skip call first, then builds a Word file and PDF.
---

# Tailor a resume to one posting

Accuracy beats polish. Every claim must trace to the profile, the original resume, or something the person said. A resume that overclaims costs more trust than it gains.

## 1. Apply or skip

Read the `Job Search Profile` and the posting (fetch the employer's page; keep a copy of the full text for the application record). Give a short, direct call covering:
- Lane fit against the profile's targets.
- Location and pay against hard filters.
- Seniority fit.
- Honest gaps: hard requirements they do not meet, and whether a screener is likely to count them strictly.
- A reminder to look for a warm contact or referral at the company.

If the call is skip, stop unless they want it anyway.

## 2. Choose and shape content

- Lead each role with the accomplishments that match the posting's actual themes. Reorder and trim; never invent.
- Use the posting's concepts where the person's real work matches them, but do not mirror its wording wholesale or stuff keywords.
- Respect every honesty guardrail and exact wording rule in the profile.
- Keep a summary only if the profile's format rules ask for one, two lines at most.
- Bullets start with a plain verb. No bold lead-ins. No em dashes. Short declarative sentences.

## 3. Build

- Follow the profile's resume format rules (page count, date alignment, section order, file naming).
- Build a .docx (for example with the `docx` skill or the Node `docx` library). For right-aligned dates, use a right tab stop at the margin, not a table, so applicant tracking systems read it cleanly.
- Convert to PDF and check the page count. Render the page to an image and look at it: fix overflow, widow lines (one or two words alone on a line), and large empty space at the bottom by rewording or trimming, then rebuild.
- Name the files by the profile's pattern, adding a company suffix when several are made the same day.

## 4. Deliver

Send both files. Then reply briefly:
- Two to four bullets on how it is aimed at this posting.
- What was left out and why, including the gaps an interviewer will probe.
- A numbered "check before you submit" list for anything uncertain.

Set the role's Status in the Pipeline tab to Resume ready.

When the person corrects anything, apply it immediately everywhere it appears and offer to add it to the profile's rules so future resumes follow it.
