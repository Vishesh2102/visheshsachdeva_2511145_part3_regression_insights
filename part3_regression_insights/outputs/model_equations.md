# Model Equations and Variable Interpretation

## Dummy Variable Approach

The dataset contains two categorical variables, **Region** and **Store Type**, which cannot be used directly in regression analysis. To include them in the model, dummy variables were created.

### Region Dummies

The original Region variable contains four categories:

* North
* South
* East
* West

Three dummy variables were created:

| Region | Region_North | Region_South | Region_East |
| ------ | ------------ | ------------ | ----------- |
| North  | 1            | 0            | 0           |
| South  | 0            | 1            | 0           |
| East   | 0            | 0            | 1           |
| West   | 0            | 0            | 0           |

**Reference Category:** West

All region coefficients are interpreted relative to stores located in the West region.

### Store Type Dummies

The original Store Type variable contains four categories:

* Airport
* HighStreet
* Residential
* Mall

Three dummy variables were created:

| Store Type  | Store_Airport | Store_HighStreet | Store_Residential |
| ----------- | ------------- | ---------------- | ----------------- |
| Airport     | 1             | 0                | 0                 |
| HighStreet  | 0             | 1                | 0                 |
| Residential | 0             | 0                | 1                 |
| Mall        | 0             | 0                | 0                 |

**Reference Category:** Mall

All store type coefficients are interpreted relative to Mall stores.

### Avoiding the Dummy Variable Trap

Only three dummy variables were created for each categorical variable. Using all categories simultaneously would create perfect multicollinearity because one category can always be derived from the others. Therefore, West and Mall were used as reference categories and excluded from the regression model.

---

# Simple Regression Model 1: Marketing Spend

### Dependent Variable

**monthly_sales**

### Independent Variable

**marketing_spend**

### Regression Equation

monthly_sales = 560777.346 + 2.13 × marketing_spend

### Results

| Metric      | Value   |
| ----------- | ------- |
| R²          | 0.167   |
| Coefficient | 2.13    |
| P-value     | 2.5E-14 |

### Interpretation

The model suggests that every additional ₹1 spent on marketing is associated with approximately ₹2.13 higher monthly sales.

The relationship is statistically significant, indicating that marketing activity contributes positively to store performance. However, the model explains only 16.7% of sales variation, showing that marketing alone is not sufficient to predict overall sales performance.

### Business Insight

Marketing investment appears to support revenue growth, but other operational and customer-related factors also play an important role.

---

# Simple Regression Model 2: Footfall

### Dependent Variable

**monthly_sales**

### Independent Variable

**footfall**

### Regression Equation

monthly_sales = 446410.58 + 35.68 × footfall

### Results

| Metric      | Value   |
| ----------- | ------- |
| R²          | 0.736   |
| Coefficient | 35.68   |
| P-value     | 4.8E-94 |

### Interpretation

The model indicates that each additional customer visit is associated with approximately ₹35.68 in additional monthly sales.

The relationship is highly significant and explains approximately 73.6% of sales variation, making footfall a much stronger predictor than marketing spend.

### Business Insight

Customer traffic is one of the strongest drivers of store revenue. Stores with higher footfall consistently generate higher sales.

## Comparison of Simple Regression Models 

Both variables are statistically significant. However, footfall explains a much larger portion of sales variation than marketing spend.

While marketing investment contributes to growth, customer traffic appears to be the more important standalone driver of revenue. For decision-making purposes, footfall provides stronger predictive value and should receive greater attention from management.

---

# Multiple Regression Model

## Model Specification

### Dependent Variable

**monthly_sales**

### Numerical Predictors

* marketing_spend
* footfall
* inventory_availability_pct

### Dummy Variables

* Region_North
* Region_South
* Region_East
* Store_Airport
* Store_HighStreet
* Store_Residential

Reference Categories:

* Region: West
* Store Type: Mall

---

## Regression Equation

monthly_sales = 150574.38
+ 1.1884(marketing_spend)
+ 33.8598(footfall)
+ 2961.27(inventory_availability_pct)
− 10576.29(Region_North)
+ 1313.40(Region_South)
− 18934.82(Region_East)
+ 10756.80(Store_Airport)
− 12295.39(Store_HighStreet)
− 28871.87(Store_Residential)

---

## Model Performance

| Metric         | Value  |
| -------------- | ------ |
| Multiple R     | 0.909  |
| R²             | 0.827  |
| Adjusted R²    | 0.822  |
| Standard Error | 43,806 |
| Observations   | 320    |

### Interpretation

The model explains approximately 82.7% of the variation in monthly sales, indicating strong explanatory power. Compared with the simple regression models, it provides a more complete view of the factors associated with sales performance.

---

# Coefficient Interpretation

### Intercept

The intercept represents the estimated sales for a Mall store in the West region when all numerical variables equal zero. While not practically meaningful, it serves as the baseline for the model.

### Marketing Spend

Coefficient: **1.188**

P-value: **1.57E-18**

Marketing spend has a positive and statistically significant relationship with sales. Higher marketing investment is associated with higher monthly revenue.

### Footfall

Coefficient: **33.860**

P-value: **1.31E-103**

Footfall is the strongest predictor in the model. More customer visits are strongly associated with higher sales performance.

### Inventory Availability

Coefficient: **2961.27**

P-value: **5.07E-10**

Stores with better inventory availability tend to achieve higher sales because fewer stockouts reduce missed purchase opportunities.

## Region Effects

### Region_North
- **Coefficient:** -10,576
- **P-value:** 0.144

After controlling for other variables in the model, stores located in the North region are estimated to generate approximately ₹10,576 lower monthly sales than comparable stores in the West region. However, the p-value is greater than 0.05, indicating that this difference is not statistically significant.

### Region_South
- **Coefficient:** 1,313
- **P-value:** 0.857

South region stores are estimated to generate approximately ₹1,313 higher monthly sales than comparable stores in the West region. The very high p-value suggests that this difference is not statistically significant, indicating similar sales performance between South and West stores.

### Region_East
- **Coefficient:** -18,935
- **P-value:** 0.003

East region stores are estimated to generate approximately ₹18,935 lower monthly sales than comparable stores in the West region. Since the p-value is below 0.05, this difference is statistically significant and suggests that location in the East region is associated with lower sales performance.

---

## Store Type Effects

### Store_Airport
- **Coefficient:** 10,757
- **P-value:** 0.270

Airport stores are estimated to generate approximately ₹10,757 higher monthly sales than Mall stores. However, the p-value is greater than 0.05, indicating that the difference is not statistically significant.

### Store_HighStreet
- **Coefficient:** -12,295
- **P-value:** 0.061

HighStreet stores are estimated to generate approximately ₹12,295 lower monthly sales than Mall stores. While the relationship is close to the significance threshold, the p-value remains slightly above 0.05, so the evidence is not strong enough to conclude a meaningful difference.

### Store_Residential
- **Coefficient:** -28,872
- **P-value:** 0.000021

Residential stores are estimated to generate approximately ₹28,872 lower monthly sales than comparable Mall stores. The very small p-value indicates a statistically significant relationship, suggesting that Residential stores consistently underperform relative to Mall stores after accounting for other factors in the model.

---

# Significant Variables

The following variables showed statistically significant relationships with monthly sales:

* marketing_spend
* footfall
* inventory_availability_pct
* Region_East
* Store_Residential

These variables provide the strongest evidence of association with sales performance.

---

# Final Model Selected

The **Multiple Regression Model** was selected as the final model for this analysis.

### Reasons for Selection

1. It achieved the highest explanatory power with an R² of **82.7%**.
2. It incorporates multiple business drivers rather than relying on a single predictor.
3. It accounts for both operational factors and categorical differences across regions and store types.
4. It provides more realistic business insights than the simple regression models.
5. It offers stronger predictive capability for sales planning and decision-making.

---

# Key Findings

The analysis identified the following variables as the most important factors associated with monthly sales:

* Footfall
* Marketing Spend
* Inventory Availability Percentage

In addition, stores located in the **East region** and **Residential store format** were associated with lower sales performance compared with their respective reference categories.

Variables such as Region_North, Region_South, Store_Airport, and Store_HighStreet did not show statistically significant relationships and should be interpreted cautiously.

---

# Conclusion

The multiple regression model provides the most complete explanation of monthly sales performance and was selected as the final model for this project.

The results suggest that increasing customer traffic, maintaining strong inventory availability, and investing effectively in marketing are likely to have the greatest association with higher sales performance. The model also highlights differences across regions and store formats that may warrant further investigation.

While the analysis identifies important relationships, regression measures association rather than causation. Therefore, the findings should be used to guide business decisions alongside operational knowledge and additional analysis.