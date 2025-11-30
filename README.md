# U.S. Medical Insurance Costs — Summary

This notebook explores the "insurance.csv" dataset to identify patterns and drivers of medical insurance charges.  
Constraints: analysis is implemented only with core Python constructs (lists, dictionaries, functions, loops and control flow) — no external data libraries.

Goals
- Inspect data quality and distributions (age, sex, bmi, children, smoker, region, charges).
- Produce simple, interpretable summaries (group means, counts, top records).
- Perform focused checks that highlight interactions (e.g., smoker × BMI, age-specific ranges).
- Keep code educational and reproducible for beginners.


{ 
# Preprocessing & data-quality notes

- Convert types on read: age -> int, bmi -> float, children -> int, charges -> float.
- Check counts per group (sex, smoker, region, children) and common ages (e.g., 18–32 appear frequently).
- Guard all average calculations by checking group counts > 0 to avoid division-by-zero.

## Dataset variables

- age: integer
- sex: categorical (female / male)
- bmi: float
- children: integer
- smoker: categorical (yes / no)
- region: categorical (northeast / northwest / southeast / southwest)
- charges: float (medical insurance cost)

All analyses assume numeric fields are converted at import time.

## Findings — interpretation guidance

- Sex distribution: The dataset is roughly balanced by sex — report raw counts alongside any sex-based comparisons for clarity.
- Children: A large proportion have zero children, while groups with four or five children are rare; treat averages for these small groups as unstable.
- Top charges: Very high charges are mostly linked to smoking and high BMI — inspect each top-cost record (age, BMI, smoker status, children, region) to confirm drivers.
- Per-age variance: Some ages show wide BMI ranges; compute per-age min/max BMI and the associated charge differences to evaluate whether BMI variability relates to greater cost dispersion.
- Interaction effects: Smoking combined with obesity tends to produce the highest mean charges — always show subgroup counts (and consider medians) before drawing conclusions.

Detailed analysis results can be found on us-medical-insurance-costs.ipynb