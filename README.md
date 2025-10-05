
## Population by single-year age (India, 2011) — short student report

I used the Census 2011 table `DDW-0000C-13.xls` (Population by single-year age, residence, sex).

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
- Census of India 2011 — table `DDW-0000C-13.xls` (downloaded from data.gov.in).

Notes
- This is an exploratory student analysis; numbers are based on the provided table and binned by single-year ages. The Colab notebook reproduces the steps if you prefer an interactive run.

Dataset details (additional resource)
- Title: Population in single year age by Residence and Sex - India and States
- Details: fields include State Code, District Code, Area Name, Age, Total Persons, Total Males, Total Females, Rural Persons, Rural Males, Rural Females, Urban Persons, Urban Males and Urban Females at India, States/UTs and District level.
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
  - The line plot and weighted histogram show a clear population concentration in the younger ages with a notable peak at age 10 (≈30.5M). This suggests a large cohort of children in 2011 and is consistent with a high birth rate in preceding years.

- Median age around mid-20s
  - The CDF and cumulative sums show the approximate median around age 24, indicating that half the population was younger than mid-20s in 2011 — consistent with a young population structure.

- More males overall, but age-dependent variation
  - The overall sex ratio is higher than 100 (≈106), indicating more males than females in the population in 2011. The `sex_ratio_by_age.png` plot shows how this ratio varies by age: some ages (notably around older ages) have fewer males (lower ratios), while some adult ages show higher male-dominant ratios.
  - The scatter plot of total males vs total females by age lies near the 1:1 line for many ages but with visible deviations. The observations file lists ages with the largest deviations from the mean sex ratio: ages such as 51 show high male concentration, while some very old ages (e.g., 90, 99) show male scarcity likely reflecting male mortality at advanced ages.

- Rural versus urban distributions
  - The box and violin plots compare rural and urban population distributions across ages. Rural totals are larger and show greater spread, and the totals show ~69% rural share in 2011 (consistent with India being majority rural at that time).

- Population pyramid shape
  - The pyramid plot visualizes the broad base and tapering high ages; it aligns with a high-fertility, young-age-structured population.

Limitations and notes
- Age bins are single-year; calculation of median age here is approximate and based on binned data — a more precise median requires microdata or finer granularity.
- Some small data-cleaning assumptions were made (matching `Area Name == 'India'`; numeric coercion). If you want state-level or district-level analyses the script can be adapted by changing the selection criteria.
---

My brief summary

I cleaned the India-level rows from `DDW-0000C-13.xls`, saved the cleaned CSV (`outputs/india_age_national.csv`), and produced the plots in `plots/` (line, scatter, box/violin, histogram/CDF, sex-ratio, pyramid). Key takeaways: total ≈ 1.206B; median age ≈ 24; peak single-year age = 10; overall sex ratio ≈ 106 males per 100 females; and ~69% rural. I included a Colab notebook to reproduce the analysis interactively.
