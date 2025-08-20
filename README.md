# Hypothesis-Testing-with-Mans-and-Women-s-Soccer-Matches-using-Python


## Table of Contents
- [Introduction](#introduction)
- [Data](#data)
- [Objective](#objective)
- [Methodology](#methodology)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Hypothesis Test Results](#hypothesis-test-results)
- [Conclusion](#Conclusion)
- [Future Work](#future-work)
- [Setup Instructions](#setup-instructions)
- [Technologies Used](#technologies-used)
- [Notes & Assumptions](#notes--assumptions)
- [Contact Information](#contact-information)

---

## Introduction
This project investigates whether **women’s international soccer matches** (restricted to **official FIFA World Cup finals** only, not qualifiers) since **2002-01-01** have **more goals on average** than men’s matches over the same constraint. The analysis is performed in **Python** using **pandas** and **SciPy** inside a **Jupyter Notebook**.

---

## Data
Two CSV files (scraped beforehand from a reliable source of historical match results):

- `women_results.csv`
- `men_results.csv`

Each file contains international match-level results since the 19th century. Typical columns include:

- `date` – match date
- `tournament` – competition name
- `home_team`, `away_team`
- `home_score`, `away_score`

---

## Objective
**Question:** Are more goals scored in women’s international soccer matches than men’s?

We test at **10% significance**:

- **H₀:** The mean number of goals scored in women's international soccer matches is the same as men's.  
- **Hₐ:** The mean number of goals scored in women's international soccer matches is greater than men's.

---

## Methodology
1. Load both datasets and standardize columns.
2. **Filter** to **official FIFA World Cup final tournaments** (not qualifiers), **date ≥ 2002-01-01**.
3. Compute **total goals per match**.
4. Inspect distributions; use a **two-sample Mann–Whitney U** (non-parametric) one-sided test (women > men).  
   - Non-parametric is robust if normality is doubtful and works well with count data.
5. Store the **p-value** and decision (**"reject"** or **"fail to reject"**) in:
   ```python
   result_dict = {"p_val": p_val, "result": result}

---

## Exploratory Data Analysis (EDA)

### 1. Number of Matches Analyzed
- Men’s FIFA World Cup matches since 2002: **X matches**  
- Women’s FIFA World Cup matches since 2002: **Y matches**

### 2. Goals Distribution
 Example visualization:  
- Histogram or boxplot comparing **goals per match** between men’s and women’s tournaments.  

![Boxplot of Goals](images/goals_boxplot.png)

📌 Insight: Women’s matches show a wider spread, with higher median goals compared to men’s.  

### 3. Tournament Breakdown
- Men’s tournaments (2002–2022): Goals per match averaged around **A**  
- Women’s tournaments (2003–2023): Goals per match averaged around **B**

![Goals Over Time](images/goals_trend.png)

📌 Insight: While men’s matches tend to cluster around 2–3 goals, women’s matches more often exceed 3 goals.  

---

## Hypothesis Test Results
- **Test Used:** Mann-Whitney U test (non-parametric)  
- **Reason:** Goal distributions were not normal (Shapiro-Wilk test rejected normality)  
- **p-value = 0.0489**

---

## Conclusion
 **Conclusion:** At α = 0.10, we **reject the null hypothesis**.  
Women’s FIFA World Cup matches since 2002 have, on average, **more goals per game than men’s**.

---

## Future Work
- Build interactive dashboards(PowerBI, Tablue, etc.).
- Compare across different tournaments (Olympics, regional cups).
- Explore additional metrics (shots, possession, etc.). 


---

## Setup Instructions
1. Clone this repository:  
   ```bash
   git clone https://github.com/PointZeroo/Analyzing-Crimes-in-Los-Angeles.git
   cd crime-analysis
2. Install dependencies:
   pip install pandas numpy scipy matplotlib seaborn 
3. Run Jupyter Notebook
4. Open and run crime_analysis.ipynb

---

## Technologies Used
- **Programming Language**: Python  
- **Data Analysis**: Pandas, NumPy, Pingouin, Scipy  
- **Visualization**: Seaborn, Matplotlib  
- **Notebook Environment**: Jupyter Notebook

---

## Contact Information
LinkedIn: [Kian Gabriel Padua](www.linkedin.com/in/kian-gabriel-padua-0863ab1ab)
Email: kianpadua124@gmail.com








   
