# Hypothesis-Testing-with-Mans-and-Women-s-Soccer-Matches-using-Python


## Table of Contents
- [Introduction](#introduction)
- [Data](#data)
- [Objective](#objective)
- [Methodology](#methodology)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Hypothesis Test Results](#hypothesis-test-results)
- [Conclusion](#conclusion)
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

Each file contains international match-level results since the 19th century. Columns include:

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
- Men’s FIFA World Cup matches since 2002: **384 matches**  
- Women’s FIFA World Cup matches since 2002: **200 matches**

<img width="590" height="490" alt="image" src="https://github.com/user-attachments/assets/0e8e908d-af8d-4c0d-be58-b466146b10ac" />

---

### 2. Total Goals: Men vs Women
   - A Boxplot and Barplot showing the comparison between the goals of men and women.

<img width="1189" height="590" alt="image" src="https://github.com/user-attachments/assets/3fe7f154-c62b-4d4f-8812-b8cea55cab56" />


📌 **Insight**: 
- **Boxplot:** Women’s matches tend to have more goals per game compared to men’s, with a slightly higher median and more extreme high-scoring outliers.
- **Barplot:** On average, women’s matches also show a higher number of goals than men’s matches, although the error bars suggest considerable variability.
   **Overall**, women’s matches appear to be higher scoring on average and more variable than men’s.
---

### 3. Goals Distribution
 Example visualization:  
- Histogram or boxplot comparing **goals per match** between men’s and women’s tournaments.  

<img width="1189" height="590" alt="image" src="https://github.com/user-attachments/assets/5ecf58fb-924f-4d9f-81a5-a9cd04790c01" />


📌 **Insight**: 
This chart shows histograms of total goals per match for men’s and women’s football tournaments. It’s split into two subplots:

Men’s World Cup: Most matches end with 1–3 goals, showing tighter, more balanced games.
Women’s World Cup: Wider spread, with more high-scoring matches (6+ goals), showing greater variability.

**In short**: Men’s matches are more consistently low to moderate in scoring, while women’s matches have greater scoring variability and occasional goal-heavy results. 
  

---

## Hypothesis Test Results

<img width="531" height="393" alt="image" src="https://github.com/user-attachments/assets/abe48807-ebcd-4e3d-b11b-0a66dd320c80" />
<img width="545" height="374" alt="image" src="https://github.com/user-attachments/assets/a84e8663-ccff-473f-afa8-48c849d7c187" />


- **Test Used:** Mann-Whitney U test (non-parametric)  
- **Reason:** Goal distributions were not normal (Shapiro-Wilk test rejected normality)  
- **p-value = 0.005**

---

## Conclusion
 **Conclusion:** At p-value = 0.005, we **reject the null hypothesis**.  

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
   pip install pandas numpy scipy pingouin matplotlib seaborn 
3. Run Jupyter Notebook
4. Open and run men_vs_women_soccer.ipynb

---

## Technologies Used
- **Programming Language**: Python  
- **Data Analysis**: Pandas, NumPy, Pingouin, Scipy  
- **Visualization**: Seaborn, Matplotlib  
- **Notebook Environment**: Jupyter Notebook

---

## Notes and Assumptions

- Assumes matches are independent (ignores team form/history)
- Focuses only on FIFA World Cup matches since 2002
- Used Mann-Whitney U test due to non-normality of data
---

## Contact Information
LinkedIn: [Kian Gabriel Padua](www.linkedin.com/in/kian-gabriel-padua-0863ab1ab)
Email: kianpadua124@gmail.com








   
