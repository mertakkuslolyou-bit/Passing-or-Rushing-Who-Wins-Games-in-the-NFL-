# Passing-or-Rushing-Who-Wins-Games-in-the-NFL

## Project Overview
In this project, I analyze how passing and rushing performance affect a team’s probability of winning in the NFL. The goal is to evaluate whether today’s NFL is primarily a “passing league” or whether rushing performance still plays a major role.

## Project Details

### Project Title
**Passing or Rushing: Who Wins Games in the NFL?**

### Data Sources
- **nfl_data_py (API):** Official NFL play-by-play and team data
- **Pro-Football-Reference:** Advanced and historical statistics (reference)
- **Kaggle NFL Team Stats Dataset:** Additional datasets for older seasons (reference)

### Data Enrichment (New Measures)
- **Passing Efficiency Index (PEI):** Passing yards / Passing attempts  
  Measures how efficiently a team passes.
- **Rushing Efficiency Index (REI):** Rushing yards / Rush attempts  
  Measures how efficiently a team runs.
- **Offensive Balance Ratio (OBR):** Pass attempts / (Pass attempts + Rush attempts)  
  Indicates whether an offense is pass-heavy or run-heavy.
- **Turnover Impact Score (TIS):** Takeaways − Giveaways
- **Scoring Efficiency (SE):** Points / Total yards

---

## 1. Data Collection
NFL data from the **2022–2024 regular seasons** was collected using the `nfl_data_py` API.

### Sources Used
- `nfl_data_py.import_pbp_data()` → Play-by-play level data  
- `nfl_data_py.import_schedules()` → Game outcomes (home/away teams, scores, win/loss)

### Collected Variables
- Passing yards and attempts  
- Rushing yards and attempts  
- Total points  
- Game IDs and team IDs  
- Win/loss outcomes  

---

## 2. Exploratory Data Analysis (EDA)
After collecting the data, I performed exploratory data analysis to understand the structure and patterns in the dataset.

### Initial Exploration
- Displayed the first rows using `head()`
- Checked column counts (approximately 400 play-by-play features)
- Filtered only regular-season games

### Feature Engineering
- Aggregated play-by-play data to team-level game statistics
- Created custom performance metrics: **PEI**, **REI**, and **OBR**

### Visual EDA
- Scatter plots:
  - Passing Efficiency (PEI) vs win
  - Rushing Efficiency (REI) vs win
  - Offensive Balance Ratio (OBR) vs win
- Correlation matrix and heatmap

### Insights from EDA
- **PEI** shows a strong positive relationship with winning
- **REI** shows little separation between winning and losing teams
- **OBR** indicates that pass-heavy teams win more consistently

---

## 3. Hypothesis Testing
To statistically evaluate the impact of passing and rushing performance, independent t-tests were conducted between winning and losing teams.

### 3.1 Passing Efficiency Index (PEI)
- **t-statistic:** 17.20  
- **p-value:** 7.0 × 10⁻⁶¹  

**Conclusion:** Passing efficiency is highly statistically significant and strongly associated with winning.

### 3.2 Rushing Efficiency Index (REI)
- **t-statistic:** 1.49  
- **p-value:** 0.136  

**Conclusion:** Rushing efficiency is not statistically significant; winning and losing teams have similar rushing efficiency.

### 3.3 Offensive Balance Ratio (OBR)
- **t-statistic:** −21.28  
- **p-value:** 7.5 × 10⁻⁸⁹  

**Conclusion:** Teams that pass more frequently are significantly more likely to win.

### Summary of Statistical Findings
- **PEI:** Strong positive predictor of wins  
- **REI:** Not a significant predictor  
- **OBR:** Highly significant predictor  

Overall, the results suggest that passing performance explains game outcomes better than rushing in recent NFL seasons.

---

## 4. Machine Learning (ML): Logistic Regression
In addition to EDA and hypothesis testing, a supervised machine learning method was applied.

### Model
A **Logistic Regression** model was used to predict game outcomes (**win = 0/1**) using:
- **PEI (Passing Efficiency Index)**
- **REI (Rushing Efficiency Index)**
- **OBR (Offensive Balance Ratio)**

### Methodology
- Data split into **70% training** and **30% testing**
- Model evaluated using accuracy, confusion matrix, and classification report

### Results and Interpretation
- The model achieved approximately **77% accuracy**
- **PEI** has a positive coefficient, increasing win probability
- **REI** has a weak effect
- **OBR** has a relatively large coefficient, indicating an advantage for pass-heavy teams

These results are consistent with the earlier EDA and hypothesis testing findings.

---
## AI Assistance Disclosure

I used ChatGpt for these purposes:
- Debug Python environment and Jupyter Notebook issues (e.g., package installation and kernel errors)
- Help structure and rephrase parts of the README for clarity and organization

Example prompts used include:
- "How can I fix Jupyter kernel issues when scikit-learn is installed but not recognized?"
- "Help me write a short README section explaining logistic regression results in basic terms."
- "Paraphrase the README section more academically."
- "Why does Jupyter Notebook not run cells even when Shift+Enter is pressed?"
- Debug Python environment issues related to **Anaconda Navigator**, virtual environments, and Jupyter Notebook kernels.
- Resolve package installation problems (e.g., `scikit-learn` being installed but not recognized due to environment mismatch).
- Assist with restarting and reconnecting Jupyter kernels when the terminal and notebook became unresponsive.
- Assist with cleaning the notebook by identifying and removing **broken / erroneous output cells** (e.g., NameError outputs) directly on GitHub.

## How to Run

Install required packages:
   pip install -r requirements.txt
