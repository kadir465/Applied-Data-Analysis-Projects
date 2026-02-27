# Comprehensive Weather Data Analysis & Visualization

This directory contains an end-to-end data science project focused on analyzing and visualizing a custom weather dataset for the year 2024. The project demonstrates a modular, Object-Oriented approach to data manipulation and automated reporting.

By separating the analytical logic from the visualization processes, this project showcases clean code principles and scalable software design.

## Dataset Overview (`hava_durumu_2024_zor.csv`)

The analysis is powered by a comprehensive, 365-day weather dataset. The dataset includes missing values and varied data types to simulate real-world data cleaning scenarios.
* **Columns:**
  * `tarih`: Date of the record (YYYY-MM-DD).
  * `sicaklik`: Average daily temperature (°C).
  * `nem`: Daily humidity percentage (%).
  * `yagis`: Precipitation amount (mm).
  * `tatil`: Specifies if the day is a national holiday or special occasion (contains NaN values for regular days).

## Project Architecture & Modules

The project is divided into two distinct Python scripts, each handling a specific part of the data pipeline:

### 1. Data Processing & Statistical Analysis (`hava_durumu_veri_analizi1.py`)
This script acts as the data engine. It uses **Pandas** to load, clean, and analyze the raw dataset.
* **Key Features:**
  * Calculates core statistical metrics (Mean and Median) for temperature, humidity, and precipitation across the entire year.
  * Filters and isolates data specifically for official holidays using `notnull()`.
  * Performs comparative analysis between general yearly averages and holiday-specific averages.
  * Dynamically identifies extreme weather events, such as finding the exact date, holiday name, and value of the maximum precipitation recorded during a holiday using `idxmax()` and `.loc[]`.

### 2. Data Visualization & Reporting (`hava_durumu_veri_analizi1.1.py`)
This script imports the processed data from the first module and uses **Matplotlib** and **NumPy** to generate insightful visualizations.
* **Key Features:**
  * **Histograms:** Generates 10-bin histograms using `np.histogram` to understand the frequency distribution of temperature, humidity, and precipitation.
  * **Comparative Line Charts:** Plots continuous yearly data against static holiday averages, using custom markers and colors for clear distinction.
  * **Threshold Bar Charts:** Visualizes holiday-specific metrics using bar charts, overlaid with dynamic horizontal lines (`plt.axhline()`) that represent the overall yearly averages for instant visual comparison.
  * **Automated Export:** Automatically generates, formats (rotating x-axis labels for readability), and saves 10 different high-quality `.png` charts (`foto1.png` to `foto10.png`) directly to the local directory.

## Technologies Used

* **Python 3.x**
* **Pandas:** For data ingestion, cleaning, filtering, and statistical aggregation.
* **NumPy:** For advanced numerical binning and array manipulation.
* **Matplotlib:** For programmatic generation of varied and complex visual charts.

## How to Run

Ensure your terminal is in the correct directory. You only need to run the visualization script, as it automatically initializes the analysis module:

```bash
# Make sure you have the required libraries installed
pip install pandas numpy matplotlib

# Run the visualization script
python hava_durumu_veri_analizi1.1.py

Note: Running the script will process the CSV data, print the statistical findings to the terminal, and automatically save the generated graphs (foto1.png to foto10.png) into the current directory. It is recommended to move these images to a dedicated /grafs folder for repository cleanliness.