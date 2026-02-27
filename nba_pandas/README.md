# Advanced NBA Player Statistics Analysis with Pandas

This directory contains an Object-Oriented Python data analysis project (`pandas_lesson5.py`) that performs deep statistical operations, feature engineering, and trend analysis on a comprehensive NBA dataset (`practice_nba.csv`).

This project goes beyond basic data manipulation to demonstrate real-world sports analytics, identifying player consistency, team dependency, shooting categorizations, and historical performance outliers.

## Dataset Overview (`practice_nba.csv`)

The analysis is built upon a custom dataset tracking NBA player performances across multiple seasons. The dataset includes the following key features:
* **Demographics & Play:** `Season`, `Team`, `Player`, `Games`, `Minutes`
* **Offensive Metrics:** `PTS_per_game` (Points), `AST_per_game` (Assists), `TOV_per_game` (Turnovers)
* **Shooting Efficiency:** `FG%` (Field Goal Percentage), `3P%` (3-Point Percentage), `FT%` (Free Throw Percentage)
* **Advanced Metrics:** `TRB_per_game` (Total Rebounds), `Fouls`, `Efficiency`

## Analytical Queries & Feature Engineering

The `PandasLesson1` class processes this dataset to extract 9 distinct analytical insights:

### 1. Top Performers per Season
Dynamically groups the dataset by `Season` and sorts by `PTS_per_game` to extract the top 3 highest-scoring players for every recorded season.

### 2. Player Progression (Year-over-Year Growth)
Calculates the Year-over-Year (YoY) improvement of players. By utilizing `groupby()` and the `diff()` function, it identifies which players showed the most dramatic increase in their scoring averages across consecutive seasons.

### 3. Team Efficiency Trends via Pivot Tables
Restructures the data using `pivot()`, setting seasons as columns and teams as rows. It isolates the `Efficiency` metric to calculate the long-term operational growth of teams by subtracting the 2014-2015 season metrics from the 2018-2019 season.

### 4. Advanced Metric Calculation: Efficiency Per 36 Minutes
Normalizes the `Efficiency` metric by engineering a new feature: `Efficiency_per_36`. It calculates the average minutes played per game and projects efficiency to a standard 36-minute window. To ensure statistical reliability, it filters out players with fewer than 40 `Games`.

### 5. Categorical Binning & Group Profiling (Shooting Splits)
Discretizes continuous shooting variables using `pd.qcut()`. Players are binned into "Low" and "High" categories for both `FG%` and `3P%`. It then cross-tabulates these groups to find the mean `PTS_per_game` and `Efficiency` for each quadrant.

### 6. Player Consistency (Variance Analysis)
Evaluates performance stability by calculating the standard deviation (`std`) of `PTS_per_game` for players with multiple seasons (`count >= 2`). A lower standard deviation highlights the most consistent players in the league.

### 7. Statistical Correlation (Playmaking vs. Mistakes)
Computes the Pearson correlation coefficient between `AST_per_game` and `TOV_per_game` globally and season-by-season using the `.corr()` method, revealing the relationship between playmaking volume and mistake rates.

### 8. Team Dependency (Top-Heavy Rosters)
Calculates "Team Load" by determining what percentage of a team's total points are scored exclusively by their top 5 players with the most `Minutes`. This is achieved using a custom lambda function with `nlargest()`.

### 9. Outlier Detection (Z-Score)
Identifies historic, outlier performances by calculating the Z-Score for the `Efficiency` column. It mathematically flags players whose efficiency deviates by more than 3 standard deviations from the league average `abs(z_eff) > 3`.

## Technologies Used

* **Python 3.x**
* **Pandas:** Leveraging `groupby`, `transform`, `pivot`, `qcut`, `corr`, and mathematical vectorization.

## How to Run

Ensure your terminal is at the root of the main repository (`Applied-Data-Analysis-Projects`), so the script can correctly locate the CSV file within the `nba_pandas` folder:

```bash
python nba_pandas/pandas_lesson5.py