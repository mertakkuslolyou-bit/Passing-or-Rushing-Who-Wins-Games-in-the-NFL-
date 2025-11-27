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
* Data Collection, Exploratory Data Analysis, and Hypothesis Testing
1. Data Collection
For this project, I collected NFL data from the 2022–2024 regular seasons using the nfl_data_py API.
Sources Used:
nfl_data_py.import_pbp_data() → Play-by-play level data
nfl_data_py.import_schedules() → Game scores, home/away teams, win/loss
Collected Variables:
Passing yards, attempts
Rushing yards, attempts
Total points
Game IDs, team IDs
Win/loss outcomes
2. Exploratory Data Analysis (EDA)
After collecting the data, I performed several EDA steps to understand the structure and patterns.
Initial Exploration
Displayed the first rows using head()
Checked column counts (≈400 PBP features)
Filtered only regular season games
Feature Engineering
Created team-level game stats (aggregated per team per game)
Added custom performance metrics (PEI, REI, OBR)
Visual EDA
Scatter plots:
Passing Efficiency vs Win
Rushing Efficiency vs Win
Offensive Balance Ratio vs Win
Correlation matrix & heatmap
Insights from EDA
PEI shows a noticeable positive pattern with wins
REI shows almost no separation between winners/losers
OBR suggests pass-heavy offenses win more consistently
3. Hypothesis Testing
To statistically test whether passing or rushing performance impacts winning, I performed independent t-tests.
3.1 Passing Efficiency (PEI)
Test Result:
t-statistic: 17.20
p-value: 7.0 × 10⁻⁶¹
Conclusion:
Passing efficiency has a highly significant effect on winning.
3.2 Rushing Efficiency (REI)
Test Result:
t-statistic: 1.49
p-value: 0.136
Conclusion:
Rushing efficiency is not statistically significant.
Winning and losing teams rush similarly.
3.3 Offensive Balance Ratio (OBR)
Test Result:
t-statistic: –21.28
p-value: 7.5 × 10⁻⁸⁹
Conclusion:
Teams that pass more frequently are significantly more likely to win.
Final Summary
Passing efficiency (PEI) strongly correlates with winning.
Rushing efficiency (REI) is mostly irrelevant for predicting wins.
Pass-heavy teams (OBR) have a statistically significant advantage.
This supports the idea that today’s NFL is a passing league, and passing performance is the strongest predictor of game outcomes.
