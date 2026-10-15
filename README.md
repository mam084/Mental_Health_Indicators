# Time-Series Modeling of Mental Health Indicators in the U.S. (2020–2024)

How did reported anxiety and depression change across the United States during and after the COVID-19 pandemic, who was most affected, and can the trend be forecast? This team project analyzes CDC Household Pulse Survey data from 2020 to 2024, clusters states by their symptom trajectories, and compares forecasting approaches.

*Team project by Ethan Porter, A.J. Silberstein, Matthew Epstein, Yousuf Golding, and Matthew Mitchell (June 2024).*

**[Full report (PDF)](Mental_Health_Indicator_Report.pdf)** · **[Notebook: exploration and state clustering](Mental_Health_Indicator_Notebook.ipynb)**

## Findings

- **Forecasting:** a Prophet model trained on 2020–2022 and tested on 2023 reached an RMSE of about **3.8** percentage points, beating a Bayesian updating model (RMSE about 6.4) by capturing seasonality and trend.
- **Age:** reported symptom rates fall steadily with age. A linear fit of symptom rate on age group has R² ≈ 0.84, with adults 18–29 reporting the highest rates and adults 60+ the lowest.
- **Disparities:** transgender respondents and respondents reporting two or more races showed consistently elevated rates.
- **Over time:** symptom rates peaked during the pandemic and partially declined from 2021 onward.
- **States:** clustering states by level (k-means), by trajectory shape (dynamic time warping), and by correlation of their monthly series (MDS) groups states with similar pandemic experiences.

## Data

CDC / NCHS [*Indicators of Anxiety or Depression Based on Reported Frequency of Symptoms During Last 7 Days*](https://data.cdc.gov/NCHS/Indicators-of-Anxiety-or-Depression-Based-on-Repor/8pt5-q6wp), collected through the Household Pulse Survey with the U.S. Census Bureau. It reports the share of adults with symptoms of anxiety and/or depressive disorder, nationally and by state, age, sex, gender identity, sexual orientation, race and ethnicity, education, and disability status.

Download the CSV from the link above and save it as `Depression_Symptoms.csv` next to the notebook.

## What's in this repository

| File | Contents |
|---|---|
| `Mental_Health_Indicator_Report.pdf` | Full report: data, exploratory analysis, Bayesian, Prophet, and regression models, and results |
| `Mental_Health_Indicator_Notebook.ipynb` | National and demographic trends, plus three approaches to clustering states |

## Run the notebook

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy tslearn jupyter
jupyter notebook Mental_Health_Indicator_Notebook.ipynb
```

## Limitations and next steps

- The survey is self-reported and its sampling changed across collection phases, so short-term movements partly reflect methodology.
- Forecasts use the series alone. Economic indicators, unemployment, and the timing of policy changes could improve them.
