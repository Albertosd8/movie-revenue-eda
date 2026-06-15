# Movie EDA — What Actually Drives Box Office Success?

An exploratory data analysis of ~45,000 movies from the TMDB dataset, examining 
the relationships between budget, revenue, audience ratings, language, and release decade.

---

## Project Overview

This project explores what factors are most associated with movie financial 
performance, using real-world data cleaning, feature engineering, and visual 
storytelling with Python.

**Dataset:** TMDB Movies Metadata (~45,000 records)  
**Tools:** Python · Pandas · Matplotlib · Seaborn

---

## Questions Explored

1. Do bigger budgets mean bigger revenue?
2. Are better-rated movies more profitable?
3. How has film revenue changed across decades?
4. Which movies made the most money?

---

## Key Findings

Budget had the strongest relationship with revenue — bigger productions tend to 
earn more, which makes intuitive sense. What was more interesting was that vote 
count (a measure of audience reach) turned out to be a slightly stronger revenue 
predictor than budget itself (r = 0.81 vs 0.77). Ratings, on the other hand, 
barely moved the needle on profitability (r = 0.10).

The data has real limitations. Financial records had missing values and 
inconsistencies, so these findings are directional rather than definitive. 
But the core question — what makes a movie financially successful — turned out 
to be more nuanced than the numbers alone can answer.

---

## Visualizations

### 1. Correlation heatmap
![Correlation heatmap](assets/correlation_heatmap.png)
Budget–revenue correlation: 0.77. Vote count is the strongest revenue predictor 
at 0.81. Ratings show almost no relationship with revenue (0.10).

### 2. Rating distribution: profitable vs unprofitable
![Rating distribution](assets/rating_distribution.png)
Profitable films peak around 6–7; unprofitable ones are more spread with a spike 
near 0. The overlap between groups is too large to use ratings as a reliable predictor.

### 3. Revenue by decade
![Revenue by decade](assets/revenue_by_decade.png)
Clear upward trend from ~$30B in the 1980s to ~$200B in the 2010s, with the 
steepest jump between the 1990s (~$80B) and 2000s (~$175B).

### 4. Top 10 highest-grossing movies
![Top 10 movies](assets/top10_revenue.png)
All 10 titles exceeded $1.3B. Avatar leads by a wide margin, followed by Star Wars: The Force Awakens and Titanic.

---

## Data Cleaning Highlights

- Converted `id`, `budget`, and `revenue` from mixed-type objects to numeric
- Removed 3 invalid IDs and 59 duplicate records
- Engineered `is_english_original` binary feature
- Cleaned `popularity` column (formatting inconsistencies)
- Parsed `release_date` → extracted year and decade; filtered to 1980+

---

## How to Run
```bash
git clone https://github.com/Albertosd8/movie-revenue-eda
cd movie-revenue-eda
pip install pandas matplotlib seaborn
jupyter notebook movie_dataset_eda.ipynb
```
Dataset: [TMDB Movies Metadata on Kaggle](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset)
---

## About

Built by Alberto Sandoval.
Feedback welcome via Issues or LinkedIn: https://www.linkedin.com/in/alberto-sandoval-6b79ab14a
