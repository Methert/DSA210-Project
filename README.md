# E-commerce Consumer Behavior Analysis

## DSA210 - Introduction to Data Science
### Project Proposal
### Ahmet Ertekin

## Project Overview
This project will analyze online shopping behavior using two complementary datasets: Amazon Reviews 2023 and Online Shoppers Purchasing Intention. I'll investigate what factors influence purchase decisions and post-purchase satisfaction, as well as which browsing patterns predict successful conversions.

## Motivation
I'm interested in understanding how consumers make decisions when shopping online, particularly what data points influence their purchasing choices. By analyzing e-commerce data, we can identify patterns in how product features, pricing, and browsing behaviors affect consumer choices. This data-driven approach can reveal which elements have the strongest correlation with purchasing decisions and what browsing patterns most frequently lead to conversions.

## Research Questions
1. Which browsing patterns and website interaction metrics best predict purchase completion? (Shoppers Intention dataset)
2. What browsing behaviors indicate high purchase intent versus casual browsing? (Shoppers Intention dataset)
3. How do seasonal and temporal factors (weekend vs. weekday, month) affect browsing and purchasing behavior? (Shoppers Intention dataset)
4. How does time spent on product pages relate to purchase likelihood? (Shoppers Intention dataset)
5. What product features receive the most attention in positive versus negative reviews? (Amazon Reviews dataset)
6. How do review patterns differ between product categories and price points? (Amazon Reviews dataset)
7. What makes reviews helpful to other consumers? (Amazon Reviews dataset)
8. How does verified purchase status affect review content and helpfulness? (Amazon Reviews dataset)

## Data Sources

### Primary Datasets
**Amazon Reviews 2023 Dataset**
- Source: [Amazon Reviews 2023](https://amazon-reviews-2023.github.io)
- What it contains:
  - 31 million customer reviews
  - Product metadata (price, features, categories)
  - Verified purchase labels
  - Review ratings and helpful votes
  - Temporal information (review dates)

**Online Shoppers Purchasing Intention Dataset**
- Source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset)
- What it contains:
  - 12,330 sessions of browsing data
  - Page views, duration, and bounce rates
  - Weekend/weekday information
  - Month and seasonal indicators
  - Visitor type (new vs. returning)
  - Boolean conversion attribute (purchase or no purchase)
  - Traffic type and region information

## What I'll Do

### Data Preparation
1. Clean and organize the Amazon review data
   - Process review text for analysis
   - Extract product categories and price information
   - Identify verified purchases and helpful votes
   
2. Process the online shopper intention dataset
   - Calculate engagement metrics (time on page, bounce rate)
   - Identify session patterns
   - Prepare temporal features (weekend, month)

### Analysis Methods
1. **Browsing Pattern Analysis** (Shoppers Intention dataset)
   - Identify browsing behaviors that lead to conversion
   - Calculate engagement metrics that predict purchases
   - Compare successful vs. unsuccessful shopping sessions

2. **Temporal Behavior Analysis** (Shoppers Intention dataset)
   - Compare shopping patterns across different times
   - Analyze weekend vs. weekday browsing differences
   - Measure how time spent on site impacts purchase likelihood

3. **Review Content Analysis** (Amazon Reviews dataset)
   - Extract key terms from positive and negative reviews
   - Identify frequently mentioned product features
   - Compare review content across different product categories

4. **Review Quality Analysis** (Amazon Reviews dataset)
   - Compare verified vs. non-verified purchase reviews
   - Analyze what characteristics make reviews helpful to others
   - Measure how review length relates to helpfulness

5. **Product Category Analysis** (Amazon Reviews dataset)
   - Compare review patterns across different product categories
   - Analyze how price points affect review sentiment
   - This analysis may be challenging due to dataset limitations, but could yield valuable insights if successful

6. **Conversion Prediction Modeling** (Shoppers Intention dataset)
   - Build models to predict purchase completion from browsing data
   - Identify the strongest predictors of conversion
   - Create customer segmentation based on browsing behaviors

### Visualizations
- Heat maps of conversion factors
- Funnel charts showing browsing-to-purchase journey
- Word clouds from review content
- Bar charts of review helpfulness by category
- Time series charts of browsing patterns

## Possible Limitations
- The two datasets cannot be directly linked
- Review data represents only customers who chose to leave feedback
- Browsing data doesn't contain actual product information
- The Amazon Reviews dataset is very large and may require sampling
- No demographic information in either dataset
- Limited regional information in the browsing dataset

## Expected Results
This project will show:
1. Browsing patterns that most strongly indicate purchase intent
2. Product features that consistently drive positive reviews
3. Temporal patterns in online shopping behavior
4. Engagement metrics that best predict conversion
5. Characteristics of helpful vs. unhelpful reviews
6. Differences in review patterns across product categories
7. Effective segmentation of shoppers based on browsing behavior

## Business Applications
This project will provide valuable insights for e-commerce businesses to optimize their websites, improve product listings, and develop more effective marketing strategies based on real consumer behavior data. The findings can help businesses understand what drives both browsing conversion and post-purchase satisfaction.      
