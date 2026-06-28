# Final Recommendation

## Executive Summary

The objective of this analysis was to identify the factors most strongly associated with monthly sales and provide data-driven recommendations for business decision-making. Three regression models were evaluated: a simple regression model using marketing spend, a simple regression model using footfall, and a multiple regression model incorporating operational, regional, and store-type variables.

Among the models tested, the Multiple Regression Model was selected as the final model because it achieved the highest explanatory power with an **R² of 0.827** and an **Adjusted R² of 0.822**. This indicates that approximately **82.7% of the variation in monthly sales** can be explained by the variables included in the model.

---

# Which Factors Appear Most Strongly Associated with Monthly Sales?

The regression results indicate that the strongest factors associated with monthly sales are:

### 1. Footfall

Footfall was the most influential variable in the analysis.

Regression Evidence:

* Coefficient = **33.860**
* P-value = **1.31 × 10⁻¹⁰³**
* Simple Regression R² = **0.736**

Interpretation:

Each additional customer visit is associated with approximately **₹33.86 higher monthly sales**, holding other variables constant.

The very small p-value and high explanatory power indicate that customer traffic is the strongest predictor of sales performance in the dataset.

---

### 2. Marketing Spend

Regression Evidence:

* Coefficient = **1.188**
* P-value = **1.57 × 10⁻¹⁸**
* Simple Regression R² = **0.167**

Interpretation:

Every additional ₹1 spent on marketing is associated with approximately **₹1.19 higher monthly sales** after controlling for other variables.

Although marketing spend alone explains a relatively small portion of sales variation, it remains statistically significant in the final model.

---

### 3. Inventory Availability Percentage

Regression Evidence:

* Coefficient = **2961.27**
* P-value = **5.07 × 10⁻¹⁰**

Interpretation:

A one-percentage-point increase in inventory availability is associated with approximately **₹2,961 higher monthly sales**.

This highlights the importance of maintaining product availability and reducing stockout situations.

---

### 4. Regional and Store-Type Effects

The regression model identified two significant categorical effects:

| Variable          | Coefficient |  P-value |
| ----------------- | ----------: | -------: |
| Region_East       |     -18,935 |    0.003 |
| Store_Residential |     -28,872 | 0.000021 |

Interpretation:

* East-region stores generate approximately **₹18,935 lower monthly sales** than comparable West-region stores.
* Residential stores generate approximately **₹28,872 lower monthly sales** than comparable Mall stores.

These differences remain significant even after controlling for marketing spend, footfall, and inventory availability.

---

# Which Variables Should Leadership Focus On?

Based on the regression evidence, leadership should prioritize the following areas:

### Customer Footfall

Footfall demonstrated the strongest and most consistent relationship with monthly sales.

Potential actions:

* Customer acquisition campaigns
* Loyalty programs
* Local advertising
* Community engagement initiatives
* Improvements in customer experience

### Inventory Availability

Maintaining high inventory availability can directly support revenue generation.

Potential actions:

* Better demand forecasting
* Improved inventory planning
* Supply chain optimization
* Automated replenishment systems

### Marketing Effectiveness

Marketing spend remains an important contributor to sales growth.

Potential actions:

* Focus on high-performing campaigns
* Measure return on marketing investment
* Improve targeting and customer segmentation

### East Region and Residential Stores

The analysis suggests that these store categories consistently underperform relative to their reference groups.

Management should investigate:

* Local competition
* Product assortment
* Consumer behavior
* Operational efficiency
* Market-specific challenges

---

# Which Variables Should Not Be Over-Interpreted?

The following variables were not statistically significant in the final model:

* Region_North
* Region_South
* Store_Airport
* Store_HighStreet

Although these variables have positive or negative coefficients, their p-values exceed the conventional significance threshold of 0.05.

Therefore, the current dataset does not provide sufficient evidence to conclude that these variables meaningfully influence monthly sales.

Major business decisions should not be based solely on these results.

---

# Recommended Business Actions

Based on the findings, the following actions are recommended:

### Action 1: Increase Customer Traffic

Since footfall is the strongest predictor of sales, management should prioritize initiatives that increase store visits.

### Action 2: Maintain High Inventory Availability

Reducing stockouts and ensuring product availability can improve customer satisfaction and increase revenue opportunities.

### Action 3: Optimize Marketing Investments

Marketing budgets should continue to be allocated strategically toward activities that generate measurable customer traffic and sales growth.

### Action 4: Review Underperforming Store Segments

East-region stores and Residential stores should be examined in greater detail to identify operational, competitive, or location-specific issues affecting performance.

---

# Evidence from Residual Analysis

Residual analysis was performed to evaluate prediction accuracy.

The model achieved strong predictive performance, but some stores still showed substantial differences between actual and predicted sales.

Largest positive residuals ranged from approximately:

* ₹96,000 to ₹116,000

Largest negative residuals ranged from approximately:

* ₹100,000 to ₹166,000

These results suggest that some business factors affecting sales are not captured by the current dataset.

Possible missing variables include:

* Promotional effectiveness
* Store management quality
* Customer demographics
* Seasonal demand
* Competitor activity
* Local economic conditions

Residual analysis therefore supports the conclusion that the model performs well overall but cannot explain every variation in store performance.

---

# Risks and Limitations

Several limitations should be considered before using the model for strategic decision-making.

### Limited Variables

The dataset does not include several potentially important drivers of sales, including:

* Product pricing
* Promotional discounts
* Competitor activity
* Economic conditions
* Weather effects
* Customer demographics
* Seasonal factors

### Unexplained Variation

Although the model explains approximately 82.7% of sales variation, approximately **17.3% remains unexplained**.

### Statistical Limitations

Some variables included in the model were not statistically significant and should be interpreted cautiously.

As a result, the model should be viewed as a decision-support tool rather than a perfect forecasting system.

---

# Why Regression Does Not Automatically Prove Causation

Regression analysis identifies statistical associations between variables.

A statistically significant relationship does not automatically prove that one variable directly causes changes in another.

For example:

* Higher marketing spend may be associated with higher sales, but successful stores may also receive larger marketing budgets.
* Higher footfall may be associated with higher sales, but factors such as location quality, brand strength, and customer experience may influence both footfall and sales simultaneously.

Therefore, regression results should be interpreted as evidence of association rather than proof of cause-and-effect relationships.

Business decisions should combine statistical findings with managerial judgment and operational knowledge.

---

# Final Conclusion

The Multiple Regression Model was selected as the final model because it achieved the highest explanatory power (**R² = 0.827**) and provided the most complete explanation of monthly sales performance.

The analysis indicates that **footfall, marketing spend, and inventory availability** are the strongest positive factors associated with monthly sales. In contrast, **East-region stores** and **Residential stores** were associated with significantly lower sales relative to their reference categories.

Overall, leadership should focus on increasing customer traffic, maintaining inventory availability, optimizing marketing investments, and investigating the causes of underperformance in specific store segments. While the model provides strong business insight, the results should be interpreted as associations rather than definitive evidence of causation.
