# E-commerce Consumer Behavior Analysis

## DSA210 - Introduction to Data Science
**Exploratory Data Analysis Phase**  
**Ahmet Ertekin**

---

##  Project Overview

This project explores consumer behavior on an e-commerce platform using the **Online Shoppers Purchasing Intention Dataset**. The goal is to investigate which browsing patterns, time-based metrics, and user engagement scores are associated with higher conversion rates. Through feature enrichment and exploratory data analysis (EDA), I attempt to draw insights into what makes an online session more likely to result in a purchase.

---

##  Motivation

As someone interested in how digital behavior translates into real decisions, I wanted to explore what drives an online shopper to complete a purchase. Can certain metrics like time spent on pages, bounce rates, or time of visit reveal user intent? With this project, I aim to combine behavioral intuition with data-driven analysis to answer those questions.

---

## Research Questions

1. Which behavioral metrics are most correlated with purchase completion?
2. How do bounce and exit rates influence conversion?
3. How do different segments of users (e.g., quick bouncers, loyal visitors) behave?
4. Does time spent on product or informational pages predict purchases?
5. Do weekend visits or specific months lead to more purchases?

---

## Data Source

**Online Shoppers Purchasing Intention Dataset**  
Source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset)  
- 12,330 browsing sessions  
- Page views, durations, bounce/exit rates  
- Timestamps, visitor type (new vs. returning)  
- Final purchase (conversion) flag  

---

## What I’ve Done (So Far)

### 1. Data Cleaning  
Removed outliers, handled 0-duration cases, ensured feature consistency.

### 2. Feature Enrichment  
Using the original dataset, I created new behavioral metrics:
- **Browsing Efficiency**
- **Engagement Depth and Score**
- **Value per Page and Value Potential**
- **Time Efficiency and Average Time per Page**
- **Interest Category Inference** (based on page type ratios)
- **Behavioral Segmentation via KMeans**

These were designed to better represent how users interact with the site and what patterns indicate higher intent to purchase.

### 3. Exploratory Data Analysis  
I explored:
- Conversion rates by visitor type, interest category, and behavioral segment
- Distributions of engagement and value-based metrics
- Correlation between behavioral scores and conversion
- Time-based patterns (weekend vs. weekday)

---

## Key Findings

- **Conversion Rate:** 15.63% overall
- **Strongest predictors of purchase:**
  - `value_potential` and `PageValues` (both ~0.49 correlation)
  - `engagement_score` (moderate correlation ~0.15)
- **Behavioral segments** showed huge differences:
  - *High Converters*: 78% conversion rate
  - *Quick Bouncers*: Less than 1%
- **Interest categories** matter:
  - *Balanced Shoppers* had the highest conversion
  - *Research-Oriented* users rarely convert
- **Returning visitors** were far more likely to convert than new ones

---

## Next Steps

I plan to expand the analysis with statistical and predictive techniques:
1. **Hypothesis Testing**
   - A/B tests and t-tests to compare means (e.g., weekend vs. weekday sessions)
   - ANOVA or F-tests to test variation across multiple categories
2. **Predictive Modeling**
   - Train classifiers to predict conversion using behavioral metrics
3. **Final Report**
   - Combine findings, visuals, and code into a comprehensive GitHub-based report

---

## Project Process and AI Assistance

The core idea and structure of this project were developed by me. I wanted to explore how user behavior affects online purchases. Some parts of the implementation, especially in feature engineering and visualization (e.g., clustering, radar charts), were created with the assistance of AI tools like ChatGPT. I used AI for suggestions, explanations, and code support, but always reviewed and modified the outputs.

This README, project plan, and analysis represent my own thinking, and I’ve been careful to ensure I understand every step of the process.

---

## Tools & Technologies

- **Python 3.12**
- **pandas, numpy** – data manipulation
- **matplotlib, seaborn** – data visualization
- **scikit-learn** – clustering and normalization
- **Jupyter Notebooks** – exploratory workflow

---

## Repository Structure

```bash
├── data/
│   ├── raw/                  # Original dataset
│   ├── processed/            # Cleaned dataset
│   └── enriched/             # Feature-enriched version
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_feature_engineering.ipynb
│   └── 03_exploratory_analysis.ipynb
│
├── figures/                  # Saved plots (optional if using plt.show)
├── requirements.txt
└── README.md
