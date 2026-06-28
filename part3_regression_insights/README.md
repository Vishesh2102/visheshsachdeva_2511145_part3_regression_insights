# Monthly Sales Prediction and Business Driver Analysis

## Business Problem Summary

The purpose of this project is to identify the factors associated with monthly sales performance across retail stores. The leadership team wants to understand which business variables have the strongest relationship with sales so that future decisions regarding marketing budgets, inventory management, store operations, and expansion strategies can be supported by data.

Regression analysis was used to examine how different business factors influence monthly sales. Both simple and multiple regression models were developed to compare individual predictors against a combined business model. The final objective was to determine which factors appear most important for sales performance and provide recommendations based on statistical evidence.

---

# Dataset Description

The dataset contains monthly performance information for retail stores operating across different regions and store formats.

The data includes information related to:

* Marketing expenditure
* Customer footfall
* Discount levels
* Inventory availability
* Staffing levels
* Customer ratings
* Distance from competitors
* Region
* Store type
* Monthly sales

During the initial review of the dataset, duplicate Store IDs were identified. However, no duplicate combinations of Store ID and Month were found, indicating that repeated Store IDs represent different monthly observations for the same store.

Missing values were identified in:

* Customer Rating
* Distance to Competitor (km)

These observations were reviewed during data preparation before regression analysis was performed.

After data cleaning and preparation, the dataset was used to develop regression models and evaluate sales drivers.

---

# Dataset Understanding

## Dependent Variable

The dependent variable used throughout the analysis is:

**Monthly Sales (monthly_sales)**

Monthly sales represent the business outcome that management is interested in understanding and predicting. All regression models were developed using monthly sales as the target variable.

---

## Potential Independent Variables

The following variables were considered as potential predictors of monthly sales:

* Marketing Spend
* Footfall
* Average Discount Percentage
* Inventory Availability Percentage
* Staff Count
* Customer Rating
* Distance to Competitor (km)
* Region
* Store Type

These variables were selected because they represent factors that could reasonably influence store performance.

---

## Numerical Variables

The dataset contains the following numerical variables:

* Marketing Spend
* Footfall
* Average Discount Percentage
* Inventory Availability Percentage
* Staff Count
* Customer Rating
* Distance to Competitor (km)
* Monthly Sales

These variables can be used directly in regression analysis after data preparation.

---

## Categorical Variables

The dataset contains two categorical variables:

* Region
* Store Type

Region consists of four categories:

* North
* South
* East
* West

Store Type consists of four categories:

* Airport
* HighStreet
* Residential
* Mall

Since regression models require numerical inputs, these variables were converted into dummy variables before being included in the multiple regression model.

---

## Variables Requiring Cleaning or Transformation

Several variables required preparation before analysis.

### Missing Values

Missing values were identified in:

* Customer Rating
* Distance to Competitor (km)

These variables were reviewed during data preparation.

### Dummy Variable Creation

Region and Store Type required transformation into dummy variables before they could be used in regression analysis.

### Duplicate Review

Store IDs appeared multiple times because stores were observed across multiple months. No duplicate Store ID and Month combinations were found, so no records were removed for duplication.

---

## Variables Not Used for Regression

Store ID was excluded from the regression model because it functions only as a unique identifier.

Store ID does not represent a business driver and therefore provides no meaningful information for explaining monthly sales.

---

# Regression Approach

The analysis was conducted in multiple stages.

## Stage 1: Simple Regression Models

Two simple regression models were created to understand the relationship between monthly sales and individual predictors.

### Model 1

Monthly Sales vs Marketing Spend

Purpose:

To determine whether marketing expenditure is associated with higher sales performance.

### Model 2

Monthly Sales vs Footfall

Purpose:

To determine whether customer traffic is associated with higher sales performance.

The simple models were useful for understanding the independent contribution of each variable before developing a more comprehensive model.

---

## Stage 2: Multiple Regression Model

A multiple regression model was developed using several predictors simultaneously.

Variables included:

### Numerical Predictors

* Marketing Spend
* Footfall
* Inventory Availability Percentage

### Dummy Variables

#### Region

* Region_North
* Region_South
* Region_East

Reference Category:

* West

#### Store Type

* Store_Airport
* Store_HighStreet
* Store_Residential

Reference Category:

* Mall

The purpose of the multiple regression model was to evaluate the effect of each variable while controlling for all other variables in the model.

---

# Dummy Variable Approach

Categorical variables cannot be used directly in regression models because regression requires numerical inputs.

To solve this problem, dummy variables were created.

## Region

Three dummy variables were created:

* Region_North
* Region_South
* Region_East

West was selected as the reference category.

When all three region dummy variables equal zero, the observation belongs to the West region.

## Store Type

Three dummy variables were created:

* Store_Airport
* Store_HighStreet
* Store_Residential

Mall was selected as the reference category.

When all store-type dummy variables equal zero, the observation belongs to a Mall store.

## Avoiding the Dummy Variable Trap

Only three dummy variables were created for each categorical variable.

Including all categories simultaneously would create perfect multicollinearity, known as the Dummy Variable Trap.

Using West and Mall as reference categories avoids this problem and allows meaningful interpretation of coefficients.

---

# Model Comparison Summary

Three models were evaluated during the analysis.

| Model                     | R²    |
| ------------------------- | ----- |
| Marketing Spend Model     | 0.167 |
| Footfall Model            | 0.736 |
| Multiple Regression Model | 0.827 |

### Marketing Spend Model

Marketing spend demonstrated a positive and statistically significant relationship with monthly sales. However, the model explained only 16.7% of sales variation.

### Footfall Model

Footfall demonstrated a strong positive relationship with sales and explained approximately 73.6% of sales variation.

### Multiple Regression Model

The multiple regression model achieved the highest explanatory power with an R² value of 0.827.

The model identified:

* Marketing Spend
* Footfall
* Inventory Availability
* Region_East
* Store_Residential

as significant predictors of monthly sales.

---

# Final Model Selected

The Multiple Regression Model was selected as the final model.

Reasons for selection:

* Highest R² value (0.827)
* Strongest explanatory power
* Incorporates multiple business drivers simultaneously
* Accounts for regional differences
* Accounts for store-type differences
* Provides the most useful business insights

The model explains approximately 82.7% of variation in monthly sales and therefore provides the best overall representation of sales performance within the dataset.

---

# Business Recommendation

The regression results suggest that management should focus primarily on:

### Increasing Footfall

Customer traffic was identified as the strongest predictor of monthly sales.

### Maintaining Inventory Availability

Stores with higher inventory availability generally generated stronger sales performance.

### Optimizing Marketing Spend

Marketing expenditure remained significant even after controlling for other variables.

### Reviewing East Region Stores

East-region stores showed significantly lower sales than comparable West-region stores.

### Reviewing Residential Store Performance

Residential stores generated lower sales than comparable Mall stores.

These findings suggest opportunities for targeted operational improvements.

---

# Assumptions and Limitations

## Assumptions

The analysis assumes:

* Linear relationships between variables
* Reliable and accurate data collection
* Stable relationships across observations
* Appropriate representation of categorical variables through dummy variables

## Limitations

Several limitations should be considered:

* The dataset does not include pricing information.
* Promotional effectiveness was not measured directly.
* Competitive activity was not included.
* Seasonal effects were not included.
* Economic conditions were not included.
* Approximately 17.3% of sales variation remains unexplained.

Most importantly, regression identifies associations rather than proving direct causation.

---

# Screenshots Included

The repository includes the following supporting screenshots:

* simple_regression_output.png
* multiple_regression_output.png
* residuals_preview.png
* model_comparison_preview.png

These screenshots provide evidence of the regression outputs, model comparison results, and residual analysis used throughout the project.

---

# Conclusion

The analysis demonstrates that customer footfall, marketing spend, and inventory availability are the strongest positive factors associated with monthly sales. The Multiple Regression Model achieved the best performance and was selected as the final model because it provides the most complete explanation of store sales performance. The findings can support data-driven decision-making while recognizing the limitations of regression-based analysis.
