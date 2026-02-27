[README.md](https://github.com/user-attachments/files/25615173/README.md)
# Applied Data Analysis Projects

Welcome to my Applied Data Analysis portfolio. This repository contains end-to-end data science projects demonstrating my ability to extract, clean, analyze, and visualize real-world datasets using Python's core data science stack (Pandas, NumPy, and Matplotlib).

Rather than simple procedural scripts, all projects within this repository are structured using **Object-Oriented Programming (OOP)** principles to ensure modularity, readability, and scalable data pipelines.

## Repository Structure & Projects

This repository is divided into two comprehensive projects, each tackling different aspects of the data science workflow:

### 1. Advanced NBA Statistics Analysis (`/nba_pandas`)
An in-depth statistical exploration of NBA player performances across multiple seasons using advanced Pandas operations.
* **Key Focus:** Feature engineering and complex data manipulation.
* **Highlights:** * Calculating Year-over-Year (YoY) progression and efficiency metrics per 36 minutes.
  * Detecting statistical outliers using Z-Score calculations.
  * Evaluating team dependencies and player consistency via variance (`std`) analysis.
  * Computing Pearson correlation coefficients between playmaking and mistake rates.
  * Utilizing advanced Pandas methods: `transform`, `pivot`, `qcut`, `apply`, and custom `lambda` functions.

### 2. Weather Data Analysis & Visualization (`/hava_durumu_veri_analizi`)
A comprehensive, two-module pipeline that processes a 365-day weather dataset and automatically generates visual reports.
* **Key Focus:** Separation of concerns (Data Engine vs. Visualization Engine) and automated reporting.
* **Highlights:**
  * **Data Module:** Cleans missing values, calculates core statistical metrics (mean, median), and filters data to compare general yearly averages against specific national holidays.
  * **Visualization Module:** Imports processed data to programmatically generate Histograms, comparative Line Charts, and Threshold Bar Charts.
  * **Automation:** Automatically exports and saves 10 high-quality `.png` charts for instant analytical reporting.

## Key Technical Competencies Demonstrated

* **Language:** Python 3.x
* **Data Manipulation:** Advanced `pandas` (grouping, window functions, imputation, aggregation).
* **Numerical Computing:** `numpy` (histograms, arrays).
* **Data Visualization:** `matplotlib.pyplot` (dynamic thresholds, subplots, automated `.png` saving).
* **Software Engineering:** OOP design patterns applied to data pipelines (Classes, constructors, modular methods).

## Getting Started

1. Clone the repository to your local machine:
   ```bash
   git clone [https://github.com/kadir465/Applied-Data-Analysis-Projects.git](https://github.com/kadir465/Applied-Data-Analysis-Projects.git)

2. Install the required dependencies:
pip install pandas numpy matplotlib

3. Navigate to a specific project directory and run the scripts. For example, to run the weather visualization engine:
cd Applied-Data-Analysis-Projects/hava_durumu_veri_analizi
python hava_durumu_veri_analizi1.1.py

Author
Kadir Emir Yücel Computer Science Student | Software Developer

GitHub: @kadir465
