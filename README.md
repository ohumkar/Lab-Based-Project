# Backorder Prediction
Predict Backorders as part of Lab Based Project for MIN-300

### Dataset Feature Description
<details>
  <summary>Click to view feature description</summary>

| Variable          | Description                                                    |
| ------------------|----------------------------------------------------------------|
| sku               |  Random ID for the product                                     |
| national_inv      |  Current inventory level for the part                          |
| lead_time         |  Transit time for product (if available)                       |
| in_transit_qty    |  Amount of product in transit from source                      |
| forecast_3_month  |  Forecast sales for the next 3 months                          |
| forecast_6_month  |  Forecast sales for the next 6 months                          |
| forecast_9_month  |  Forecast sales for the next 9 months                          |
| sales_1_month     |  Sales quantity for the prior 1 month time period              |
| sales_3_month     |  Sales quantity for the prior 3 month time period              |
| sales_6_month     |  Sales quantity for the prior 6 month time period              |
| sales_9_month     |  Sales quantity for the prior 9 month time period              |
| min_bank          |  Minimum recommend amount to stock                             |
| potential_issue   |  Source issue for part identified                              |
| pieces_past_due   |  Parts overdue from source                                     |
| perf_6_month_avg  |  Source performance for prior 6 month period                   |
| perf_12_month_avg |  Source performance for prior 12 month period                  |
| local_bo_qty      | – Amount of stock orders overdue                               |
| deck_risk         |  Part risk flag                                                |
| oe_constraint     |  Part risk flag                                                |
| ppap_risk         |  Part risk flag                                                |
| stop_auto_buy     |  Part risk flag                                                |
| rev_stop          |  Part risk flag                                                |
| went_on_backorder |  Product actually went on backorder. This is the target value  |

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
