# E-commerce Consumer Behavior Analysis

## DSA210 - Introduction to Data Science
### EDA and Hypothesis Testing Phase
### Ahmet Ertekin

## Project Overview
This project analyzes online shopping behavior using the Online Shoppers Purchasing Intention dataset. Through advanced feature engineering and data enrichment, I investigate what browsing patterns predict successful conversions and which factors influence purchase decisions.

## Motivation
I'm interested in understanding how consumers make decisions when shopping online, particularly what data points influence their purchasing choices. By analyzing e-commerce data, we can identify patterns in how browsing behaviors affect consumer choices. This data-driven approach reveals which elements have the strongest correlation with purchasing decisions and what browsing patterns most frequently lead to conversions.

## Research Questions
1. Which browsing patterns and website interaction metrics best predict purchase completion?
2. What browsing behaviors indicate high purchase intent versus casual browsing?
3. How do seasonal and temporal factors (weekend vs. weekday, month) affect browsing and purchasing behavior?
4. How does time spent on different page types relate to purchase likelihood?
5. What user engagement metrics correlate most strongly with conversion?
6. How do different user segments (new vs. returning visitors) differ in their browsing and purchasing behavior?
7. What is the relationship between bounce rates, exit rates, and conversion likelihood?

## Data Source
**Online Shoppers Purchasing Intention Dataset**
- Source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset)
- What it contains:
  - 12,330 sessions of browsing data
  - Page views, duration, and bounce rates
  - Weekend/weekday information
  - Month and seasonal indicators
  - Visitor type (new vs. returning)
  - Boolean conversion attribute (purchase or no purchase)

## What I've Done

### Data Preparation and Enrichment
Instead of using the raw data as is, I've applied significant transformations and created derived features:

1. **Advanced Behavioral Metrics**
   - Browsing efficiency ratio
   - Content-to-product page ratio
   - Engagement depth scoring
   - Value potential metrics

2. **User Segmentation**
   - Behavioral clustering using K-means
   - Interest category inference
   - Loyalty scoring

3. **Temporal and Engagement Analysis**
   - Time efficiency metrics for different page types
   - Comprehensive engagement scoring
   - Bounce and exit rate categorization

### Analysis Methods
1. **Browsing Pattern Analysis**
   - Identified browsing behaviors that lead to conversion
   - Calculated engagement metrics that predict purchases
   - Compared successful vs. unsuccessful shopping sessions

2. **Temporal Behavior Analysis**
   - Compared shopping patterns across different times
   - Analyzed weekend vs. weekday browsing differences
   - Measured how time spent on site impacts purchase likelihood

3. **Behavioral Segmentation**
   - Created behavior clusters using K-means
   - Identified key segments like "High Converters" and "Product Browsers"
   - Analyzed conversion rates across different segments

4. **Interest Category Analysis**
   - Inferred user interests based on browsing patterns
   - Created categories like "Product-Focused" and "Research-Oriented"
   - Examined how interest categories relate to conversion

### Visualizations
- Conversion rates by behavior segment
- Engagement score distributions
- Value potential across user segments
- Browsing efficiency metrics and their relationship to conversion
- Time spent on different page types by conversion outcome

## Key Findings (Preliminary)
- Behavioral clusters show significant differences in conversion rates
- Time efficiency metrics strongly correlate with purchase likelihood
- The content-to-product ratio provides insights into user intent
- Interest categories demonstrate clear patterns in conversion behavior
- Engagement depth scoring effectively predicts purchase outcomes

## Repository Structure
- `data/`
  - `raw/`: Original dataset
  - `processed/`: Cleaned and processed dataset
  - `enriched/`: Dataset with engineered features
- `notebooks/`
  - `data_preparation.ipynb`: Initial data cleaning
  - `online_shoppers_enriched_data.ipynb`: Feature engineering and enrichment
  - `exploratory_analysis.ipynb`: EDA and visualization (in progress)
  - `hypothesis_testing.ipynb`: Statistical tests (in progress)
- `figures/`: Visualizations generated from the analysis
- `README.md`: Project documentation

## Next Steps
1. Complete in-depth exploratory data analysis on the enriched dataset
2. Formulate and test specific hypotheses about shopping behavior
3. Create comprehensive visualizations of key findings
4. Develop predictive models for the machine learning phase
5. Document insights and business applications

## Technical Implementation
- Python 3.12
- Key libraries: pandas, numpy, scikit-learn, matplotlib, seaborn
- Jupyter notebooks for documentation and analysis
