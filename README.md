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

## Folder Structure

- `data/` – Raw, cleaned, and enriched datasets  
- `notebooks/` – Jupyter notebooks for each project stage  
- `report/` – Full project report (detailed findings and answers to research questions)
  
---

## Project Process and AI Assistance

This was my first time working with a full dataset independently from start to finish. While the core idea of this project — understanding what makes online shoppers convert — came from me, I had limited experience in areas like feature engineering, clustering, and designing custom behavioral metrics.

To bridge this gap, I frequently used ChatGPT as a learning assistant. I didn’t always know the right terminology or the exact methods I should apply, but I asked questions based on what I wanted to explore or understand better.

My workflow often looked like this:
- I had a research question in mind (e.g., “How do we know if time on a product page predicts a purchase?”)
- I tried to figure out what kind of metric or test could answer it
- I asked ChatGPT how to calculate that or how to compare groups
- I read through the explanation, tried the code, and modified it based on my dataset

### Example Prompts I Asked (and Why I Asked Them)

These are real types of questions I asked ChatGPT throughout the project. They reflect both my curiosity and the areas where I needed technical help:

---

#### “I want to group users based on their browsing behavior. Should I use KMeans or something else? How do I decide the number of clusters?”

**Why I asked:** I didn’t know what clustering algorithm to use or how many groups would make sense, but I liked the idea of behavioral segmentation.

---

#### “What kind of features can I create to measure engagement, time efficiency, or how much a user is interacting with the site?”

**Why I asked:** I knew I needed new metrics beyond what the dataset gave me, but I didn’t know how to design meaningful ones.

---

#### “How can I combine multiple variables (like page views, time spent, bounce rates) into a single ‘engagement score’?”

**Why I asked:** I wanted to create a simple number to rank users’ engagement, but I wasn’t sure how to combine different types of features.

---

#### “What’s a good way to classify users based on what kind of pages they visit most? Can I create interest categories?”

**Why I asked:** I noticed some users focused more on product pages, others on informational ones, and I thought this might say something about their intent.

---

#### “How do I use t-tests or ANOVA in Python to compare behavior between groups like converters vs non-converters?”

**Why I asked:** I wanted to apply hypothesis testing, but I wasn’t sure which test was appropriate for which kind of comparison.

---

#### “Can I use A/B testing logic to compare weekend vs weekday conversion rates?”

**Why I asked:** I was curious whether time-based patterns affected purchases, and I’d heard about A/B tests but had never tried one.

---

#### “How do I make a radar chart to compare clusters based on engagement or browsing metrics?”

**Why I asked:** I saw radar charts in online examples and thought they could help visualize the profiles of each user segment.

---

#### “Can you fix this code/ can you fix the errors in the explanation and revise it accordingly”

**Why I asked:** I had some challenges on some parts of code, also I wanted to make sure that there was no grammar error in explanations etc.

### How I Used These Answers

I didn’t just copy the code I received. I read through the explanation, tested it on my data, and sometimes rewrote or simplified it to match my level. Some of the code was directly used (especially in visualization or clustering), but I made sure I understood what each line was doing.

---

## Requirements

- **Python 3.12** (recommended)
- **pandas, numpy** – data manipulation
- **matplotlib, seaborn** – data visualization
- **scikit-learn** – clustering and normalization
- **Jupyter Notebooks** – exploratory workflow
