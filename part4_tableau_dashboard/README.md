# Part 4 - Tablue Executive Dashboard & Data Storytelling

## Dataset
Source file: dashboard_sales_data.xlsx

## Data Validation
- order_date and ship_date treated as Date fields.
- sales, profit, discount, customer_rating treated as continuous measures.
- return_flag interpreted as:
  - 0 = Not Returned
  - 1 = Returned

## Missing Values
- customer_rating contains missing values (32 records).
- campaign_channel contains missing values (24 records).
- Missing campaign channels may be grouped under "Unknown".

## Business Assumptions
- delivery_days represents total order fulfillment duration.
- Profitability evaluated using total profit and profit margin.
- Discount impact measured against sales and profit.
- Returned orders considered potential operational risk.

## Dashboard Goal
Provide leadership visibility into:
- Sales performance
- Profitability
- Customer segments
- Product categories
- Shipping performance
- Discount effectiveness
- Return behavior



# Tableau Workbook Description

Workbook:
`Retail_Executive_Dashboard.twbx`

The Tableau workbook was designed as a leadership reporting dashboard that integrates financial, operational, customer, and product performance into a single executive view.

Dashboard objectives:

1. Monitor sales growth
2. Track profitability
3. Evaluate regional performance
4. Compare customer segments
5. Measure shipping performance
6. Understand discount impact
7. Detect return-related risk

---

# Calculated Fields Created

## Profit Margin
Formula:

```tableau
IF SUM([sales])=0 THEN 0
ELSE SUM([profit])/SUM([sales])
END
```

Purpose:
Measure profitability efficiency.

---

## Cost
Formula:

```tableau
[sales]-[profit]
```

Purpose:
Estimate operational cost.

---

## Average Order Value

```tableau
SUM([sales]) / COUNTD([order_id])
```

Purpose:
Measure customer purchasing value.

---

## Return Rate

```tableau
SUM([return_flag]) / COUNTD([order_id])
```

Purpose:
Monitor return exposure.

---

## Shipping Delay Bucket

```tableau
IF [delivery_days]<=2 THEN "Fast"
ELSEIF [delivery_days]<=5 THEN "Standard"
ELSEIF [delivery_days]<=8 THEN "Delayed"
ELSE "Critical Delay"
END
```

Purpose:
Classify operational delivery performance.

---

## Additional Calculated Fields

- Discount Bucket
- Profit Status
- Customer Satisfaction Bucket

---

# Dashboard Components

The dashboard contains the following visual components:

## KPI Cards
- Total Sales → ₹217.02M
- Total Profit → ₹33.31M
- Profit Margin → 15.35%
- Return Rate → 4.55%
- Average Order Value → ₹51,671

---

## Dashboard Views

### Sales Trend
Line chart showing sales movement over time.

### Regional Performance
Bar chart comparing regional sales and profitability.

### Category Profitability
Category and sub-category profit comparison.

### Customer Segment Performance
Customer contribution analysis.

### Shipping Performance
Delivery efficiency by shipping mode.

### Discount vs Profit
Scatter plot evaluating pricing effectiveness.

### Return Analysis
Return risk evaluation.

---

# Filters and Interactions Used

## Dashboard Filters

- Date
- Region
- Category
- Customer Segment
- Ship Mode


Filters were configured to apply across all worksheets.

---

## Interactive Actions

Dashboard Filter Action:

Source:
Regional Performance

Targets:
- Category Profitability
- Customer Segment
- Return Analysis

Interaction:
Selecting a region updates dependent views.

---

# Key Business Insights

## Revenue Performance
Total business sales reached ₹217.02M with stable growth.

## Regional Opportunity
South generated highest sales (₹64.69M) and profit (₹9.99M).

## Product Profitability
Technology achieved stronger margins (~18%) than Furniture (~6–8%).

## Customer Value
Home Office customers generated highest sales and profit.

## Discount Impact
Profit margin declined from 20.56% (No Discount) to 6.54% (High Discount).

## Shipping Performance
Standard Class recorded highest delivery burden.

## Return Risk
Furniture showed highest return rate (7.67%).

---

# Dashboard Story Summary

The dashboard demonstrates that strong revenue does not automatically produce stronger profitability.

Business growth is supported by high-performing regions and customer segments, but category mix, discount intensity, delivery performance, and return patterns significantly affect long-term value creation.

Key opportunities include:

- Expand Technology growth
- Strengthen South region strategy
- Improve shipping efficiency
- Reduce return exposure
- Optimize discount policy

Leadership should prioritize profitable growth instead of maximizing sales alone.

---

# Assumptions and Limitations

## Assumptions

- delivery_days represents complete order fulfillment duration.
- return_flag:
  - 0 → Not Returned
  - 1 → Returned
- Profit calculated at transaction level.
- Missing campaign values grouped as Unknown where required.

---

## Limitations

- Historical analysis only (no forecasting).
- Customer acquisition metrics unavailable.
- Marketing ROI unavailable.
- Return reasons unavailable.
- Profit excludes broader operational cost structure.
- Dashboard supports executive monitoring but not detailed root-cause analysis.

---

# Tools Used

- Tableau Desktop

---

# Project Outcome

A single executive dashboard was created to help leadership monitor performance, identify operational risks, and support strategic decision-making using interactive business analytics.

# Repository 
```
part4_tableau_dashboard/
├── data/
│   └── dashboard_sales_data.xlsx
├── tableau/
│   └── executive_dashboard.twbx
├── outputs/
│   ├── dashboard_story.md
│   ├── business_insights.md
│   └── chart_selection_justification.md
├── screenshots/
│   ├── full_dashboard.png
│   ├── sales_trend_view.png
│   ├── regional_performance_view.png
│   ├── category_profitability_view.png
│   └── filter_interaction_view.png
└── README.md
```