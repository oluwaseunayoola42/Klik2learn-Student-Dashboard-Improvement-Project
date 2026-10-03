# Data

The data used in this analysis belongs to Klik2learn and contains information about adult learners, many from refugee and migrant backgrounds. It is **not included** in this repository.

To run the notebook, add a file at `data/Weekly Breakdown Merged.xlsx` with a sheet named `merged_data` and the same columns as the original export:

- `User ID`, `First Name`, `Last Name`, `Attempt ID` (removed on load)
- `Mid-term Exam CEFR Level`, `Reading`, `Listening`, `Writing`, `Speaking`
- `Final CEFR Level`, `Reading 2`, `Listening 2`, `Writing 2`, `Speaking 2`
- For weeks 1 to 10 and strands `a0`, `a1`, `a2`, `b1_2`, `numeracy`:
  `Week{n}_{strand}_activities_completed_week` and `Week{n}_{strand}_activities_completed_total`

Files in this folder are ignored by git (see `.gitignore`).
