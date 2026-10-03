# Methodology, Corrections and Limitations

## Data

One internal Klik2learn export, "Weekly Breakdown Merged": **36 learners x 120 columns**.

- Per learner: weekly activities completed for **10 weeks x 5 strands** (A0, A1, A2, B1/2, Numeracy), both as a weekly count and a running cumulative total.
- Mid-Term and Final assessments: four skills each (Reading, Listening, Writing, Speaking), 12 points in total, plus a CEFR level for each assessment.

The data is not published here. See [../data/README.md](../data/README.md).

## Steps

1. **Anonymise.** Names and user IDs are dropped straight after loading and replaced with a sequential key (S01, S02, ...).
2. **De-duplicate** on User ID. One row in the source sheet carries a "DUP?" note in a free-text field; the notebook reports how many such rows exist so this can be checked rather than assumed.
3. **Outcomes.**
   - Mid-Term total and Final total (sum of four skills).
   - Improvement score = Final minus Mid-Term; improvement % only where the Mid-Term total is non-zero.
   - CEFR band change = Final CEFR level minus Mid-Term CEFR level.
4. **Engagement.** Total activity = sum of the **weekly-count** columns only, cross-checked against the Week 10 cumulative totals.
5. **Analysis.** Pearson and Spearman correlations of total activity with six outcomes, with n and p-values; a top-10 overlap check; and a repeated, stratified cross-validated logistic regression compared with a majority-class baseline, using balanced accuracy and ROC AUC.

## Corrections log

I reviewed the original notebook and found issues. They are listed here rather than hidden.

| # | Issue | Effect | Status |
|---|---|---|---|
| 1 | The activity total was built from every column whose name contained "week". That matched both `..._completed_week` (weekly counts) and `..._completed_total` (cumulative totals), so cumulative values were added on top of the weekly counts. | Activity totals were inflated and weighted toward learners who were active early. Activity-outcome correlations may change. | Fixed in the notebook. Needs re-running on the real data. |
| 2 | `avg_weekly_activity` was total activity divided by a constant, so it was perfectly correlated with the total (r = 1.0). | It looked like a second engagement measure but was not. In the model it duplicated a feature. | Removed. |
| 3 | Mid-Term totals were calculated with `sum(skipna=True)`, which returns 0 when every score is missing. | A learner who did not sit the Mid-Term shows a total of 0 and an inflated "improvement". | Notebook now counts recorded scores per learner and reports how many have none. A sensitivity check excluding them is recommended. |
| 4 | The original correlation table did not include improvement itself, although the research question is about improvement. | The headline result was about activity vs *levels*. | Notebook now correlates activity with improvement and CEFR band change. |
| 5 | An exploratory "Attention Span" metric considered only the first week. | Meaningless values. | Omitted from results (as already disclosed in the report). |

## What has been verified and what has not

- **Verified in the original outputs:** 36 learners; 29/6/1 improved/no change/declined; mean Mid-Term 5.50 and Final 7.64; CEFR band counts.
- **To re-verify after re-running:** every number that uses the activity total (correlations, top-10 overlap, activity range, weekly totals).
- The notebook has been tested end to end on synthetic data with the same column structure, so the code runs, but no result in this repository comes from that test data.

## Limitations

- **Small sample:** 36 learners. Correlation estimates are highly uncertain, and a larger sample could show a stronger or weaker relationship.
- **Correlational, one cohort:** nothing here shows what caused learners to improve, and there is no comparison group.
- **Narrow measure of engagement:** activity counts capture behaviour only, not motivation, understanding or support.
- **Pooled strands:** activity from five strands is combined into one number, which could hide strand-specific effects.
- **Self-paced programme:** there is no single "correct" level of activity.
- **Ceiling effect:** scores are capped at 12 points, which compresses differences between learners.
- **Different cohorts:** the report refers to a separate 24-learner cohort in an internal brief. The two should not be combined.

## Privacy and what is deliberately left out

- Learner names, IDs and e-mail addresses are never printed or stored in outputs.
- The report also breaks outcomes down by first language, age band and gender. Several groups contain one or two learners, so I have **not** published those breakdowns: in a group of one, a table row can identify a person.
- Only aggregate charts are included.
