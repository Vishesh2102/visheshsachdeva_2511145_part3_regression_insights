# Residual Analysis

## Objective

Residual analysis was performed on the final multiple regression model to evaluate prediction accuracy and identify observations where the model substantially over-predicted or under-predicted monthly sales.

Predicted sales values were generated using the final regression equation. Residuals were then calculated as:

**Residual = Actual Monthly Sales − Predicted Monthly Sales**

A positive residual indicates that actual sales were higher than predicted by the model, while a negative residual indicates that actual sales were lower than predicted.

---

## Calculation Method

### Predicted Sales

Predicted sales were calculated using the final multiple regression equation:

Predicted Sales = Intercept + (Coefficient × Variable Value)

The equation included:

* Marketing Spend
* Footfall
* Inventory Availability %
* Region Dummy Variables
* Store Type Dummy Variables

### Residual

Residual = Actual Sales − Predicted Sales

### Absolute Residual

Absolute Residual = ABS(Residual)

Absolute residuals were used to identify observations with the largest prediction errors regardless of direction.

---

# Largest Positive Residuals (Under-Predicted by the Model)

These observations generated higher sales than the model expected.

| Actual Sales | Predicted Sales |   Residual |
| -----------: | --------------: | ---------: |
|   813,316.71 |      697,606.08 | 115,710.63 |
|   713,611.16 |      603,455.90 | 110,155.26 |
|   625,514.04 |      524,454.50 | 101,059.54 |
|   735,786.64 |      639,364.47 |  96,422.17 |
|   820,519.04 |      724,483.26 |  96,035.78 |

### Interpretation

For these stores, actual sales exceeded the model's predictions by approximately ₹96,000 to ₹116,000.

This suggests that additional business factors may be contributing to sales performance but are not captured by the regression model.

Possible explanations include:

* Strong local demand
* Effective store management
* Local promotional campaigns
* Seasonal effects
* Customer demographics
* Competitive advantages not represented in the dataset

Several of the largest positive residuals are associated with stores from the East region, suggesting that certain East-region locations may be outperforming expectations after controlling for marketing spend, footfall, inventory availability, and store characteristics.

---

# Largest Negative Residuals (Over-Predicted by the Model)

These observations generated lower sales than the model expected.

| Actual Sales | Predicted Sales |    Residual |
| -----------: | --------------: | ----------: |
|   685,379.08 |      851,738.64 | -166,359.56 |
|   627,171.90 |      760,561.84 | -133,389.94 |
|   595,467.60 |      722,105.37 | -126,637.77 |
|   800,451.94 |      912,993.82 | -112,541.88 |
|   641,865.03 |      741,946.01 | -100,080.98 |

### Interpretation

For these stores, actual sales were significantly below the model's predictions.

The model expected stronger performance based on the available predictors, but actual results were lower.

Possible explanations include:

* Temporary operational issues
* Local competition
* Staffing challenges
* Store-level execution problems
* Market conditions not captured in the dataset

These observations indicate that important sales drivers may still exist outside the variables included in the regression model.

---

# Business Interpretation of Residuals

Residuals provide useful insight into factors that the model cannot fully explain.

Positive residuals indicate stores that performed better than expected, while negative residuals indicate stores that performed worse than expected.

Because the model explains approximately 82.7% of sales variation (R² = 0.827), most observations are predicted reasonably well. However, the existence of large residuals shows that some store-level influences remain unmeasured.

Examples of potential missing factors include:

* Local economic conditions
* Competitor activity
* Promotional effectiveness
* Store management quality
* Product assortment differences
* Seasonal demand variations

---

# Under-Prediction and Over-Prediction Analysis

The residual patterns do not indicate severe systematic bias toward a single category of store.

However, some observations can be made:

* Multiple under-predicted stores belong to the East region.
* Residential store indicators appear in both the largest positive and largest negative residual groups.
* Residuals are distributed across several combinations of regions and store characteristics.

This suggests that the model performs reasonably consistently across the dataset and does not appear to consistently favor or penalize one specific store category.

---

# Conclusion

The final regression model demonstrates strong predictive performance with an R² of 82.7%. Most variation in monthly sales is explained by marketing spend, footfall, inventory availability, regional effects, and store-type characteristics.

Residual analysis shows that some stores still perform substantially above or below expectations. These differences likely arise from business factors that are not included in the dataset.

Overall, the residual patterns suggest that the model is suitable for business decision-making and sales forecasting, while also highlighting opportunities for future model improvement through the inclusion of additional operational and market variables.
