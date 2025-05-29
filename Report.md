# E-commerce Consumer Behavior Analysis – Full Project Report

This report explains my analysis of online shoppers’ behavior, covering every step from raw data exploration to machine learning modeling. Each section describes a different part of my workflow, starting from the initial state of the data and going through cleaning, feature engineering, hypothesis testing, and prediction.

---

## EDA_beforeCleaningV4.ipynb – Getting Familiar with the Raw Data

In this section, I focused on the original online shoppers dataset before any cleaning or changes. I started by loading the data and just getting a sense of its general structure—number of rows, main columns, and what the first few records look like. The idea here was to see the natural state of the data, including all the messy and possibly weird values.

I checked basic statistics to get an idea about typical session lengths, how bounce rates and exit rates are distributed, and what kind of values show up in the dataset. While doing this, I noticed a lot of zeros, especially in the duration columns, and realized some sessions might actually be empty or non-human interactions. I also looked at how conversion rates (`Revenue`) were distributed overall, and made some quick breakdowns by month and visitor type.

At this point, I didn’t try to “fix” anything—my goal was just to observe and note patterns or outliers that might need attention in later steps. This exploration helped shape my approach for data cleaning and set a baseline for later analysis.

---

## online_shoppers_V4.ipynb – Data Cleaning and Preparation

After getting a sense of the raw data, I moved on to the cleaning phase. In this notebook, I worked on filtering out sessions that didn’t make sense for analysis—like those with zero time spent on all page types, which I considered noise or bot activity. I also checked for outliers and made sure data types were correct for further analysis.

Once the obvious noise was removed, I did some basic exploratory analysis again to see how the cleaned data looked compared to the original. I looked at things like conversion rates, the breakdown of sessions by month and visitor type, and the distribution of key metrics. This gave me a better foundation for the next steps, like feature engineering and deeper analysis, with a dataset that was more trustworthy and ready for actual modeling.

---

## online_shoppers_enrichmentV4.ipynb – Feature Engineering & Enrichment

In this part, I focused on creating new features to better capture user behavior. Using what I noticed in the earlier EDA, I designed metrics like engagement score, product ratio, and some categorical groupings based on page types and time spent. I also experimented with clustering (like KMeans) to segment users into different behavioral groups.

The goal here was to go beyond the basic columns and make the dataset richer and more informative for both hypothesis testing and future machine learning. After building these new features, I updated the cleaned data and saved it for use in the next analysis steps.

---

## online_shoppers_edaV4.ipynb – EDA After Feature Engineering

In this file, I explored the dataset after feature engineering and enrichment. I looked at how the new features—like engagement score and product ratio—related to conversion, and checked their distributions. I used visualizations and grouped statistics to dig deeper into patterns, such as which visitor types or months saw the highest conversion rates.

This round of EDA helped me understand which features seemed most promising for prediction and which user segments were more likely to convert. It set the stage for statistical testing and building ML models in the next steps.

---

## online_shoppers_hypothesis_V4.ipynb – Hypothesis Testing

In this section I applied statistical tests to see which features actually separate buyers from non-buyers. I started by running t-tests on several of the main metrics. For example, the engagement score turned out not to matter at all (t=0.01, p=0.99) since the means for buyers and non-buyers were nearly identical. The same was true for average time per page and exit rates—no meaningful difference between groups.

On the other hand, the product ratio was strongly significant (t=-6.43, p=0.0000), with buyers having a lower product ratio on average. Bounce rates also showed a statistically significant result (t=-2.30, p=0.0227), but in practice the means were so close (both rounded to 0.01) that I don’t think it matters much for actual prediction.

I also used chi-square tests for categorical features. Returning visitors were much more likely to convert (chi2=47.91, p=0.0000), and sessions on the weekend also had a higher conversion rate (chi2=5.62, p=0.0177).

Finally, I checked for differences across months with ANOVA. There was a huge effect of month on conversion rates (F=26.05, p < 1e-43), with some months like November and December standing out.

In summary, product ratio, being a returning visitor, and visiting on weekends were among the features most strongly linked to conversion, while others (like engagement score) didn’t really matter.

---

## ML2.ipynb – Predicting Conversion: Machine Learning Results & Insights

In this final section of the project, I built and evaluated a machine learning model to predict whether a session would lead to a purchase. Because my data was heavily imbalanced—only a small fraction of sessions actually ended in a purchase—I focused on both model performance and how to interpret the results realistically.

After selecting features based on earlier statistical tests, I used logistic regression with balanced class weights and standardized features. Instead of just reporting the default predictions, I wanted to show how changing the probability threshold affects performance. This matters especially with imbalanced data, where the default 0.5 threshold usually misses most buyers.

### Why Tune the Threshold?

With imbalanced data, a model will almost always predict the majority class (non-buyers) unless you lower the threshold for predicting a buyer. By reporting results at multiple thresholds, I can show the trade-off between catching more buyers (recall) and being more precise (precision). This is important because, in real applications, you might want to prioritize one over the other.

---

### Threshold Analysis Table

Below are the key metrics at different probability thresholds for the logistic regression model:

| Threshold | Precision (Buyer) | Recall (Buyer) | F1 (Buyer) | Weighted Avg Precision | Accuracy |
| --------- | ----------------- | -------------- | ---------- | ---------------------- | -------- |
| 0.95      | 0.20              | 0.05           | 0.08       | 0.94                   | 0.96     |
| 0.7       | 0.10              | 0.41           | 0.15       | 0.95                   | 0.86     |
| 0.55      | 0.08              | 0.81           | 0.15       | 0.96                   | 0.70     |
| 0.5       | 0.08              | 0.88           | 0.15       | 0.97                   | 0.69     |
| 0.3       | 0.07              | 0.95           | 0.12       | 0.97                   | 0.56     |
| 0.2       | 0.06              | 0.98           | 0.11       | 0.97                   | 0.49     |
| 0.1       | 0.06              | 0.98           | 0.11       | 0.97                   | 0.49     |

*Note: Precision, recall, and F1 shown here are for the buyer class, which is the minority.*

This table makes it clear: with such imbalanced data, there’s no perfect setting where both precision and recall for buyers are high. Lowering the threshold increases recall but drops precision sharply.

---

### Comments on the Graphs

**ROC Curve:**  
The ROC curve gives an overall sense of the model’s ability to distinguish between buyers and non-buyers across all possible thresholds. The area under the curve (AUC) is relatively high in this case, which might suggest good performance. However, with severe class imbalance, the ROC curve can sometimes look deceptively optimistic—so while it’s useful, I focused more on precision and recall for the buyer class.

**Regression Coefficient Plot:**  
This plot shows which features push the prediction towards purchase or not. Positive coefficients increase the likelihood of predicting a buyer, while negative ones do the opposite. Features like product ratio, being a returning visitor, and sessions in certain months (especially November and December) had the most impact. This matches what I saw in the hypothesis tests: not every feature matters, and some like engagement score turned out not to be as useful as I expected.

**Precision and Recall vs. Threshold:**  
This plot is key for understanding the trade-offs in a real-world setting. As I lower the threshold, recall for buyers climbs quickly—almost all buyers are predicted at the lowest thresholds. But precision drops, so most sessions flagged as buyers aren’t actually buyers. There’s no sweet spot where both are high, so the threshold really depends on what the business cares about: finding every possible buyer (recall), or being sure that those flagged are actually buyers (precision).

---

### Why I Showed Different Thresholds

I reported different thresholds because, with this data, using the default threshold isn’t enough. With so few buyers, the model will almost always default to “no purchase.” By showing results at different levels, I can be transparent about what’s actually possible. Depending on the application, a business might want to prioritize catching as many buyers as possible, or might be okay missing some if it means fewer false positives.

---

### Limitations Due to Data Imbalance

Even after careful feature engineering, statistical testing, and model tuning, the model’s ability to perfectly identify buyers is limited by the underlying data. When buyers are less than 5% of sessions, the model is almost always right by saying “no purchase,” but this isn’t very useful if you want to actually find real buyers. Adjusting the threshold helps, but the precision-recall tradeoff is a fundamental limitation here. In short, with this data, this was the maximum I could do with standard methods.

---

## Connecting Results to My Research Questions

- **Which behavioral metrics are most correlated with purchase completion?**  
  Statistical tests and model coefficients both pointed to product ratio, certain months (like November and December), and being a returning visitor as key predictors. Other features, like engagement score and average time per page, did not actually make much difference.

- **How do bounce and exit rates influence conversion?**  
  Bounce rate was statistically significant, but the actual difference in means was very small, so it probably doesn’t matter much for actual prediction. Exit rate didn’t show any effect.

- **How do different segments of users behave?**  
  Returning visitors and users visiting during certain months were far more likely to convert. Most buyers came from these groups.

- **Does time spent on product or informational pages predict purchases?**  
  Time spent did not matter as much as expected—product ratio was a stronger signal than absolute time.

- **Do weekend visits or specific months lead to more purchases?**  
  Yes, weekend sessions and sessions in November/December had higher conversion rates, as confirmed by both hypothesis testing and model results.

---

## Summary

By combining statistical analysis with machine learning and threshold tuning, I was able to identify the features most closely tied to purchases and give a realistic picture of what can and can’t be predicted with this dataset. The biggest challenge was the imbalance, and the best I could do was to honestly present the trade-offs involved in any practical prediction. The visualizations back up these findings and show both the strengths and unavoidable weaknesses of modeling rare events like e-commerce conversion.
