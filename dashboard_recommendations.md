# Dashboard and Monitoring Recommendations

These follow from the finding that platform activity is only weakly related to academic progress ([key_findings.md](key_findings.md)). The aim is to keep what is valuable about the automation while removing the risk of acting on a misleading signal.

## Priorities at a glance

| # | Recommendation | Effort | Impact | When |
|---|---|---|---|---|
| 1 | Relabel status flags as usage metrics | Low | High | Now |
| 2 | Show assessment signals next to activity | Low-medium | High | Next |
| 3 | Replace "Inactive" with a graded measure | Medium | Medium | Next |
| 4 | Log outreach emails and what happens next | Low | High | Now |
| 5 | Student view: weekly progress, skills, next step | Medium | Medium | Later |
| 6 | Collect richer data for any future prediction | Medium-high | High (long term) | Later |
| 7 | Standardise weekly exports and naming | Low-medium | Medium | Next |

## 1. Relabel status flags as usage metrics

**What:** "Consistently Active", "Active in Weeks 1-5", "Active in Weeks 6-10" and "Inactive" describe platform *usage*. Present them that way, and keep them out of any "at risk" language.

**Why:** a green flag can create false reassurance, and a red one can trigger outreach to a learner who is progressing well.

## 2. Show assessment signals next to activity

**What:** on the tutor view, put each learner's Mid-Term result and weakest skill beside their activity, so staff can see all four combinations:

| | Low activity | High activity |
|---|---|---|
| **Strong assessment** | Probably fine: do not chase | Doing well |
| **Weak assessment** | Check in: low use and low result | Look closer: working hard without progress |

**Why:** the top-right and bottom-left cells are where one metric alone misleads. The data showed that heavy users were not reliably the biggest improvers.

## 3. Replace "Inactive" with a graded measure

**What:** use bands (for example none / low / medium / high weekly activity) or recent-activity indicators: days since last activity, consecutive inactive weeks, change from the learner's own earlier weeks.

**Why:** a learner's own trend is more informative than a fixed threshold. Cohort activity fell sharply after Week 1, so a fixed rule will label more and more learners "inactive" over time even when they are not struggling.

## 4. Log outreach emails and track what happens next

**What:** the system already logs a "Sent" flag. Add the date, the learner's activity in the following two weeks, and any reply or tutor contact.

**Why:** this turns the automation into something that can be evaluated. It also gives Klik2learn the beginnings of evidence on whether the emails help, which the current data cannot show.

## 5. Student-facing view

Keep it simple, with a small number of clear panels:

1. **My progress:** Mid-Term level to current level.
2. **My learning activity:** this week's activity against the learner's own target, and a weekly line chart.
3. **My skills:** activity across Reading, Writing, Listening and Speaking.
4. **My next step:** one clear action, for example "Complete a Speaking activity".

**Why:** students should see what they have done *and* what to do next. Show activity as encouragement, not as a score, given the weak link to results.

## 6. Collect richer data before building anything predictive

Candidates, in order of likely value:

- tutor contact and notes (recorded in a structured way);
- live-session attendance;
- a short check-in on barriers to study (time, device, connectivity, caring responsibilities);
- time spent per activity, not just completions.

Any future model should be tested on a larger sample and a longer period before it is used to decide who gets contacted.

## 7. Tidy the data pipeline

Standardise weekly export naming and keep weekly counts and cumulative totals clearly separated. In this project a mix-up between the two inflated an early activity total, which is exactly the kind of error that clean naming prevents.

## How to know it worked

- Fewer outreach emails sent to learners who then show normal progress.
- Share of enrolled learners who reach the Final assessment. Establish a baseline first: the analysed dataset only includes learners with results, so it cannot show how many started.
- Tutor time per week spent on manual reporting.
- Response rate to outreach, once logged.

## Assumptions and open questions

- These recommendations rest on one cohort of 36 learners. A larger sample could change the picture.
- The analysis did not test whether the emails themselves help. That needs its own evaluation.
