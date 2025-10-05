
## Population by single-year age (India, 2001) — short report

This is a short student report for the Census 2001 table `DDW-0000C-13.xls` (Population by single-year age, residence, sex). I cleaned India-level rows, made plots, and wrote brief observations.

Files (important)
- `scripts/make_plots.py` — run this to recreate the CSV and plots
- `notebooks/colab_analysis.ipynb` — Colab-ready notebook (upload the Excel to Colab and run)
- `outputs/india_age_national.csv` — cleaned CSV (India-level)
- `plots/` — PNGs produced by the script

Quick run (local)
1) Create venv and install:

```powershell
python -m venv .venv
& '.venv/Scripts/Activate.ps1'
python -m pip install pandas openpyxl xlrd matplotlib numpy scipy statsmodels
```

2) Run:

```powershell
python scripts/make_plots.py
```

Key results (short)
- Total population (sum of single-year ages): 1,205,759,397
- Median age (approx): 24
- Peak single-year age: 10 (≈30,552,107 people)
- Overall sex ratio (males per 100 females): ≈106
- Rural vs Urban: ~69% rural, ~31% urban

Main plots and what they show
- Line plot (`line_population_by_age.png`): age distribution and peak at age 10
- Scatter (`scatter_males_vs_females.png`): male vs female counts by age; annotated fit and R²
- Box/Violin (`box_rural_vs_urban.png`, `violin_rural_vs_urban.png`): rural population is larger and more spread
- Histogram/CDF (`hist_population_by_age.png`, `cdf_population.png`): cumulative/weighted age distribution
- Sex ratio (`sex_ratio_by_age.png`) and population pyramid (`population_pyramid.png`) for age/sex structure

Data source
- Census of India 2001 — table `DDW-0000C-13.xls` (downloaded from data.gov.in). Cite the Census if you publish results.

Notes
- This is an exploratory student analysis; numbers are based on the provided table and binned by single-year ages. The Colab notebook reproduces the steps if you prefer an interactive run.

If you want, I can prepare a Git-ready bundle (`requirements.txt`, `.gitignore`) and an annotated Colab notebook for submission.

Dataset details (additional resource)
 - Title: Population in single year age by Residence and Sex - India and States
 - Details: Get details of State Code, District Code, Area Name, Age, Total Persons, Total Males, Total Females, Rural Persons, Rural Males, Rural Females, Urban Persons, Urban Males and Urban Females at India, States/UTs and District level.
 - Link: https://www.data.gov.in/resource/population-single-year-age-residence-and-sex-2011-india

Key numeric summaries (from the cleaned data)
- Rows with numeric ages (0–99): 100
- Total population (sum of single-year ages): 1,205,759,397
- Estimated median age (approx): 24
- Peak single-year age: Age 10 with 30,552,107 people
- Overall sex ratio (males per 100 females): ~106.06
- Rural total (sum of single-year ages): 830,427,936
- Urban total (sum of single-year ages): 375,331,461
- Rural share: ~68.87% | Urban share: ~31.13%

Detailed observations and interpretation
- Young-age bulge and peak at age ~10
   - The line plot and weighted histogram show a clear population concentration in the younger ages with a notable peak at age 10 (≈30.5M). This suggests a large cohort of children in 2001 and is consistent with a high birth rate in preceding years.

- Median age around mid-20s
   - The CDF and cumulative sums show the approximate median around age 24, indicating that half the population was younger than mid-20s in 2001 — consistent with a young population structure.

- More males overall, but age-dependent variation
   - The overall sex ratio is higher than 100 (≈106), indicating more males than females in the population in 2001. The `sex_ratio_by_age.png` plot shows how this ratio varies by age: some ages (notably around older ages) have fewer males (lower ratios), while some adult ages show higher male-dominant ratios.
   - The scatter plot of total males vs total females by age lies near the 1:1 line for many ages but with visible deviations. The observations file lists ages with the largest deviations from the mean sex ratio: ages such as 51 show high male concentration, while some very old ages (e.g., 90, 99) show male scarcity likely reflecting male mortality at advanced ages.

- Rural versus urban distributions
   - The box and violin plots compare rural and urban population distributions across ages. Rural totals are larger and show greater spread, and the totals show ~69% rural share in 2001 (consistent with India being majority rural at that time).

- Population pyramid shape
   - The pyramid plot visualizes the broad base and tapering high ages; it aligns with a high-fertility, young-age-structured population.

Limitations and notes
- The dataset is an official census table; if you publish this work, cite the Census of India and link to the original data on data.gov.in rather than embedding the raw Excel if licensing prevents redistribution.
- Age bins are single-year; calculation of median age here is approximate and based on binned data — a more precise median requires microdata or finer granularity.
- Some small data-cleaning assumptions were made (matching `Area Name == 'India'`; numeric coercion). If you want state-level or district-level analyses the script can be adapted by changing the selection criteria.

How to publish to GitHub (quick guide)
1. Create a new public repo on GitHub and clone it locally.
2. Add these files and commit:
    - `scripts/` (both `.py` scripts)
    - `outputs/` (CSV and observations.md) — optionally exclude large raw data
    - `plots/` (PNG images)
    - `README.md`, `GITHUB_NOTES.md`
3. Add a `.gitignore` and a small `requirements.txt` like:

```text
pandas
matplotlib
openpyxl
xlrd
numpy
scipy
```

4. Push to GitHub and paste the repo link where required.

Suggested next steps (optional)
- Convert `scripts/make_plots.py` into a Jupyter/Colab notebook with inline figures and narrative — helpful for submission and reproducibility.
- Add small statistical annotations (R² on scatter, confidence intervals on smoothed lines) and annotate peaks on the line plot.
- Extend analysis to state/district-level comparisons (cluster/stacked bar plots) or time-series if later census rounds are available.

References and citation
- Government of India. Census 2001. "Population in single year age by Residence and Sex, 2001 - INDIA". Retrieved via data.gov.in.

---

If you'd like, I can now:
- create a Colab notebook with the full analysis and embedded plots (ready to share)
- prepare the repo folder with `requirements.txt` and `.gitignore` and show the exact git commands to push to GitHub
- refine plots and add annotations and a small PDF/summary slide

Tell me which of these you'd like me to do next and I'll proceed.
