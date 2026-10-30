# mlb-operations-pipeline

 📊 Executive Summary
This project builds an end-to-end data engineering and predictive modeling pipeline using historical Lahman Baseball Databank data. By combining robust SQL extraction (CTEs, window functions, self-joins) with a `scikit-learn` Linear Regression model, this pipeline evaluates the direct statistical correlation between team offensive production (specifically Home Runs) and game wins.

🔑 Key Findings & Methodology
* **Data Engineering:** Built an in-memory SQLite pipeline via Python/Pandas to ingest and transform raw CSV mirrors.
* **SQL Transformations:** Utilized Common Table Expressions (CTEs), multi-table self-joins for historical baseline comparisons, and `RANK()` window functions to track annual power distribution.
* **Predictive Modeling:** Trained a linear regression model confirming that offensive metrics drive high win totals, while uncovering critical operational outliers.

## 📈 Visualizing the Correlation (Charts)
### Figure 1: Offensive Power (Home Runs) vs. Team Wins
https://github.com/JJAMES02814199808/mlb-operations-pipeline/blob/main/hr_wins_regression.png

*Demonstrating a strong positive correlation between home run production and total season wins, while highlighting high-power outliers.*

### Figure 2: The Outlier Factor (Run Differential vs. Wins)
hr_wins_regression_outliers.png

*Exposing how pitching and run prevention separates the high-HR teams that made the playoffs from the ones that fell short.*


🕵️‍♂️ Investigating the Outliers
To make this model production-ready, we dug into the teams that broke the trend:
* **The High-HR, Low-Win Outliers:** Teams with elite power metrics that still finished under .500. Analysis revealed a critical flaw in **Runs Allowed (RA)**—all-offense squads whose pitching and bullpen units leaked runs nightly.
* **The Low-HR, High-Win Outliers:** Teams with modest home run totals that still notched 95+ wins, driven by elite run prevention, high on-base efficiency, and run-manufacturing.


## 🛠️ Tech Stack & Tools
* **Python** (Pandas, Scikit-learn, Matplotlib/Seaborn)
* **SQL / SQLite** (Window functions, CTEs, self-joins)
* **Google Colab** (Development environment)

## 🚀 How to Run
1. Clone the repository.
2. Open the Jupyter notebook in the `notebooks/` directory.
3. Run the cells to execute the SQLite data extraction and model training.  
