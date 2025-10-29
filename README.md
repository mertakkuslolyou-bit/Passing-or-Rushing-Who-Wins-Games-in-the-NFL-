# Passing-or-Rushing-Who-Wins-Games-in-the-NFL-
Project Title
Passing or Rushing: Who Wins Games in the NFL?
Project Overview
In this project, I will look at how passing and rushing performance affect a team’s chance of winning in the NFL.
There has always been a debate: do great passing teams or great rushing teams win more?
By using publicly available NFL data, I will compare both and try to see which one has a bigger impact on success.
The goal is to find out if today’s NFL is really a “passing league” or if running the ball still matters a lot.
Data Sources
nfl_data_py (API): Official NFL play-by-play and team data
Pro-Football-Reference.com: Advanced and historical stats
Kaggle NFL Team Stats Dataset: Extra datasets for older seasons
Data Enrichment
To make the data more useful, I’ll combine information from different sources and create new measures:
Metric	Formula	Purpose
Passing Efficiency Index (PEI)	Passing yards ÷ Pass attempts	Measures how efficient a team passes
Rushing Efficiency Index (REI)	Rushing yards ÷ Rush attempts	Measures how efficient a team runs
Offensive Balance Ratio (OBR)	Pass attempts ÷ (Pass + Rush attempts)	Shows whether a team prefers passing or rushing
Turnover Impact Score (TIS)	(Takeaways – Giveaways) ÷ Games	Shows how ball security affects wins
Scoring Efficiency (SE)	Points ÷ Total yards	Measures how well teams turn yards into points
Analysis Plan
Data Collection & Cleaning
Get data from 2022–2024 seasons
Merge datasets and handle missing values
Create new stats (PEI, REI, etc.)
Visualization
Scatter plots: PEI vs Wins and REI vs Wins
Boxplots: compare pass-heavy and run-heavy teams
Correlation heatmap: show links between stats and win counts
Statistical Analysis
Correlation analysis: find which metrics relate most to wins
Regression model: see if passing or rushing predicts wins better
Hypothesis test:
H₀: Passing and rushing efficiency don’t affect wins
H₁: At least one of them does
Interpretation
Explain what the numbers mean for real football
Discuss what kind of offense works best in today’s game
Expected Outcomes
Find which stats are most related to winning
See if the NFL really favors passing now
Show results with visual graphs
Give a short discussion about what strategies work best
