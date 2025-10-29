# Passing-or-Rushing-Who-Wins-Games-in-the-NFL

## Project Overview

In this project, I will look at how passing and rushing performance affect a team's chance of winning in the NFL. The goal is to find out if today's NFL is really a "passing league" or if running the ball still matters a lot.

## Project Details

* **Project Title:** Passing or Rushing: Who Wins Games in the NFL?
* **Data Sources:**
    * `nfl_data_py` (API): Official NFL play-by-play and team data
    * Pro-Football-Reference.com: Advanced and historical stats
    * Kaggle NFL Team Stats Dataset: Extra datasets for older seasons
* **Data Enrichment (New Measures):**
    * **Passing Efficiency Index (PEI):** $\frac{\text{Passing yards}}{\text{Passing attempts}}$ (Measures how efficient a team passes)
    * **Rushing Efficiency Index (REI):** $\frac{\text{Rushing yards}}{\text{Rush attempts}}$ (Measures how efficient a team runs)
    * **Offensive Balance Ratio (OBR):** $\frac{\text{Pass attempts}}{\text{Pass attempts + Rush attempts}}$ (Shows team preference)
    * **Turnover Impact Score (TIS):** $\text{Takeaways} – \text{Giveaways}$
    * **Scoring Efficiency (SE):** $\frac{\text{Points}}{\text{Total yards}}$
* **Analysis Plan:**
    * **Data Collection & Cleaning:** Get data from 2022-2024 seasons, merge datasets, and handle missing values.
    * **Visualization:** Scatter plots (PEI vs Wins, REI vs Wins), Boxplots (pass-heavy vs run-heavy teams), Correlation heatmap.
    * **Statistical Analysis:** Correlation analysis and Regression model (predicts wins based on passing/rushing).
    * **Hypothesis Test:** $H_0$: Passing and rushing efficiency don't affect wins vs. $H_A$: At least one does.
* **Expected Outcomes:** Find which stats are most related to winning and see if the NFL favors passing now.
