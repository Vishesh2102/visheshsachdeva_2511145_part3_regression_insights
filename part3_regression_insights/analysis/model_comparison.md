# Model Comparison

## Model 1: Monthly Sales vs Marketing Spend

**Dependent Variable:** monthly_sales

**Independent Variable:** marketing_spend

**R²:** 0.167

### Significant Variable

* marketing_spend (p < 0.05)

### Business Interpretation

The regression results show a positive relationship between marketing spend and monthly sales. This means that stores spending more on marketing generally achieve higher sales. However, the R² value is only 0.167, which means the model explains about 16.7% of the variation in sales. This suggests that marketing spend alone is not enough to predict store performance accurately.

### Business Usefulness

The model is useful for understanding whether marketing investment affects sales, but it should not be used on its own for forecasting.

### Limitations

Many important factors such as customer footfall, inventory availability, region, and store type are not included in this model.

---

## Model 2: Monthly Sales vs Footfall

**Dependent Variable:** monthly_sales

**Independent Variable:** footfall

**R²:** 0.736

### Significant Variable

* footfall (p < 0.05)

### Business Interpretation

Footfall has a strong positive relationship with monthly sales. The regression coefficient indicates that sales tend to increase as the number of customers visiting the store increases. With an R² value of 0.736, the model explains about 73.6% of the variation in monthly sales, making it much stronger than the marketing spend model.

### Business Usefulness

This model can be useful for estimating sales based on expected customer traffic and identifying the importance of attracting customers to stores.

### Limitations

Although the model performs well, it does not consider factors such as marketing activities, inventory levels, regional differences, or store characteristics.

---

## Model 3: Multiple Regression Model

**Dependent Variable:** monthly_sales

**Independent Variables:**

* marketing_spend
* footfall
* inventory_availability_pct
* Region_North
* Region_South
* Region_East
* Store_Airport
* Store_HighStreet
* Store_Residential

**R²:** 0.827

### Significant Variables (p < 0.05)

* marketing_spend
* footfall
* inventory_availability_pct
* Region_East
* Store_Residential

### Business Interpretation

This model explains approximately 82.7% of the variation in monthly sales, which is the highest among all models tested. The results show that marketing spend, footfall, and inventory availability have positive effects on sales. Among the dummy variables, Region_East and Store_Residential are statistically significant, suggesting that location and store type can also influence performance.

The coefficient for footfall is positive and relatively large, indicating that customer traffic is one of the strongest drivers of sales. Inventory availability is also important because stores cannot generate sales if products are unavailable. Marketing spend remains significant even after controlling for other factors.

### Business Usefulness

This is the most useful model because it considers multiple factors that affect sales at the same time. It provides a better understanding of store performance and can support business decisions related to marketing, inventory management, and store operations.

### Limitations

Some dummy variables have high p-values and do not appear to have a strong statistical impact on sales. In addition, factors such as pricing, promotions, competition, economic conditions, and seasonality are not included in the dataset, so the model cannot explain every variation in sales.

---

# Overall Comparison

| Model                               | R²    |
| ----------------------------------- | ----- |
| Simple Regression (Marketing Spend) | 0.167 |
| Simple Regression (Footfall)        | 0.736 |
| Multiple Regression Model           | 0.827 |

The comparison shows that the Multiple Regression Model performs the best with an R² of 0.827. While footfall alone explains a large portion of sales variation, combining footfall with marketing spend, inventory availability, region, and store type improves the model further. Therefore, the Multiple Regression Model was selected as the final model because it provides the highest explanatory power and is the most suitable for business analysis and sales prediction.
