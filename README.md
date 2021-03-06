# Backorder Prediction
Predict Backorders as part of Lab Based Project for MIN-300

### Dataset Feature Description
<details>
  <summary>Click to view feature description</summary>

| Variable          | Description                                                    | Values     |
| ------------------|----------------------------------------------------------------|------------|
| sku               |  Random ID for the product                                     | int        |
| national_inv      |  Current inventory level for the part                          | float      |
| lead_time         |  Transit time for product (if available)                       | int        |
| in_transit_qty    |  Amount of product in transit from source                      | int        |
| forecast_3_month  |  Forecast sales for the next 3 months                          | int        |
| forecast_6_month  |  Forecast sales for the next 6 months                          | int        |
| forecast_9_month  |  Forecast sales for the next 9 months                          | int        |
| sales_1_month     |  Sales quantity for the prior 1 month time period              | int        |
| sales_3_month     |  Sales quantity for the prior 3 month time period              | int        |
| sales_6_month     |  Sales quantity for the prior 6 month time period              | int        |
| sales_9_month     |  Sales quantity for the prior 9 month time period              | int        |
| min_bank          |  Minimum recommend amount to stock                             | int        |
| potential_issue   |  Source issue for part identified                              | (Yes, No)  |
| pieces_past_due   |  Parts overdue from source                                     | int        |
| perf_6_month_avg  |  Source performance for prior 6 month period                   | float      |
| perf_12_month_avg |  Source performance for prior 12 month period                  | float      |
| local_bo_qty      | – Amount of stock orders overdue                               | (Yes, No)  |
| deck_risk         |  Part risk flag                                                | (Yes, No)  |
| oe_constraint     |  Part risk flag                                                | (Yes, No)  |
| ppap_risk         |  Part risk flag                                                | (Yes, No)  |
| stop_auto_buy     |  Part risk flag                                                | (Yes, No)  |
| rev_stop          |  Part risk flag                                                | (Yes, No)  |
| went_on_backorder |  Product actually went on backorder. This is the target value  | (Yes, No)  |

</details>

### Observations
- Each row represents a unique product 
- There 168761 of these products
- Only one feature has missing values --> lead_time
    - Missingness is about 6%
    - Use mean or mice imputation
- Data is highly imbalanced
    - We hardly have any information of products that went on backorder

### Questions to answers using EDA

- Most popular products (top - 10)
- Predicted sales for these products 
    - Predicted sales for next 1,3,6 months
- Which of these products faced backorders ?
- Of the products that went on backorder what was the cause ? 
    - Amt of stock orders overdue
    - Risk flags
    - Current stock for them
- Transit Analysis
- Average Lead Time
- Variable Correlation
