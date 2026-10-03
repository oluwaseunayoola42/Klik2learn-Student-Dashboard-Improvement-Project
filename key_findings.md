# Key Findings

Sample: **36 learners**, ten weeks of activity, Mid-Term and Final assessments (4 skills, 12 points in total).

The findings are split into two groups, because one of them depends on the activity total that I corrected after the original analysis (see [methodology_and_limitations.md](methodology_and_limitations.md)).

## A. Findings about progress (not affected by the correction)

### 1. Most learners improved, but the answer depends on how "improvement" is measured

| Measure | Improved | No change | Declined |
|---|---|---|---|
| Points (Final minus Mid-Term) | 29 (81%) | 6 (17%) | 1 (3%) |
| CEFR band | 26 (72%) | 10 (28%) | 0 |

On the CEFR measure, 25 learners moved up one band and 1 moved up two. The nine-point gap between the two measures is learners who gained points but not enough to change band. Neither measure is wrong, but conclusions depend on which one is used.

### 2. Average gain was meaningful

The mean score rose from 5.50 to 7.64 out of 12, a gain of 2.14 points. The percentage gain (65% on average) is skewed by learners who started with very low scores, and it can only be calculated for the 34 learners with a non-zero Mid-Term score. Points are the safer figure to quote.

![Improvement distribution](figures/improvement_distribution.png)
![CEFR band change](figures/cefr_band_change.png)

### 3. The data cannot say why learners improved

There is no comparison group. Gains could come from the platform, tutor support, classroom teaching, or simply more practice over time.

## B. Findings about engagement (re-verify after re-running the notebook)

### 4. Cohort activity peaked in Week 1 and did not return

Reading the weekly chart, activity fell by almost half between Week 1 and Week 2, partly recovered in Week 3, and then stayed between roughly 30% and 50% of the Week 1 level. In terms of individual learners, 13 of 36 (36%) did their most active week in Week 1, and nobody peaked in Week 9 or 10.

The internship's earlier progress report described engagement as building over three weeks before declining. The re-run does not support that, and the data should take precedence over the narrative.

![Cohort activity by week](figures/weekly_activity_trend.png)

### 5. Activity was only weakly related to outcomes

In the original analysis, total activity correlated with exam outcomes at r = 0.12 to 0.30:

| Outcome | r |
|---|---|
| Final CEFR level | 0.296 |
| Mid-Term CEFR level | 0.185 |
| Mid-Term total | 0.155 |
| Final total | 0.116 |

None approached the conventional 0.5 for a moderate relationship. By contrast, Mid-Term and Final CEFR levels correlated at 0.83, so the assessment data is consistent, and the weak link is unlikely to be caused by poor outcome data.

Two things to check on the re-run: the original did not correlate activity with *improvement* directly (the notebook now does), and the original activity total included cumulative columns.

### 6. The most active learners were not the biggest improvers

Only 2 learners appeared in both the top-10 improvers and the top-10 most active. Activity ranged from about 80 to nearly 7,900 across learners (original metric), a gap of nearly 100 times, but outcomes sit on a 12-point scale and did not spread out in the same way.

### 7. A simple model could not use activity to predict who improves

A cross-validated logistic regression reached a balanced accuracy of about 0.63 with a very wide spread between folds (standard deviation about 0.22). A baseline that always predicts "improved" is right 81% of the time, so raw accuracy is misleading, and balanced accuracy of 0.63 on 36 learners is not reliable evidence of predictive power. The coefficient on activity was close to zero.

## What this means

1. The programme appears to work for most learners.
2. Activity counts are a **usage** measure, not a progress measure.
3. Status flags and "you have not engaged" emails should not be presented as academic-risk alerts.
4. A predictive early-warning tool would need richer data (tutor contact, live-session attendance, learner-reported barriers) and a larger sample.

Next: [dashboard_recommendations.md](dashboard_recommendations.md)
