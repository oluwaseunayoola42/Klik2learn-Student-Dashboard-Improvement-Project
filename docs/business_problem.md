# Business Problem

## Background

Klik2learn is a small online ESOL (English for Speakers of Other Languages) provider. Most of its learners are adult migrants and refugees, and English is often their second, third or fourth language. For them, better English affects work, further study and day-to-day life.

Learners work through self-paced modules organised by CEFR band (A0, A1, A2, B1/2, plus a numeracy strand) and sit a Mid-Term and a Final assessment covering Reading, Listening, Writing and Speaking. The platform exports a weekly activity dataset for every learner.

The company is small, with limited staff. It wanted to move from manual spreadsheets to an automated way of spotting disengaged learners.

## What I built during the internship

Over eight weeks as a Business Analytics intern I built:

- Google Sheets and Apps Script reports that collect weekly activity per learner;
- status flags ("Inactive", "Active in Weeks 1-5", "Active in Weeks 6-10", "Consistently Active");
- an automated email to learners with no recorded activity, with a "Sent" log to avoid duplicates;
- Looker Studio dashboards.

Everything above treats activity as a stand-in for progress.

## The problem

Nobody had checked whether that assumption was true. If activity does not track progress, the system could:

- email learners who are keeping up despite low platform activity (for example, those with strong tutor or community support);
- show a green "Consistently Active" status for someone who is not improving;
- support unsupported claims if activity is reported to funders as evidence of learning.

The risk is higher than usual because these learners often face the added pressure of migration or displacement, so a wrong message costs more.

## Research question

> To what extent does weekly platform activity predict improvement in assessment performance among adult ESOL learners, and what does that mean for how the dashboard and automated emails should work?

Sub-questions:

1. How does cohort engagement change over the ten-week programme?
2. Is activity (total and weekly) related to improvement from Mid-Term to Final?
3. What should change in the monitoring tools as a result?

## Why it matters

- **For Klik2learn:** it decides who gets contacted each week, with very few staff to do it.
- **For the field:** most evidence on learning analytics comes from credit-bearing university courses, not self-paced adult ESOL.

## What the analysis could and could not do

It could test whether activity and outcomes move together in one cohort of 36 learners. It could not establish cause, because there is no comparison group and the programme includes tutor and classroom support that the data does not capture.

See [key_findings.md](key_findings.md) for results.
