# Chart Selection Justification – Retail Executive Dashboard

This dashboard was designed to support leadership decision-making rather than display isolated visualizations. Chart selection was based on the analytical question each view needed to answer.

---

# 1. Sales Trend View

## Business Question
How is sales performance changing over time and are there visible growth patterns across regions?

## Chart Type Selected
Line Chart

## Why This Chart Is Appropriate
A line chart is the most effective way to display trends over time because it preserves continuity and allows leadership to observe movement, seasonality, and overall business direction.

Monthly sales comparison becomes easier without visual distortion.

## Visual Encoding Used

X-axis:
- Order Date (Month)

Y-axis:
- SUM(Sales)

Color:
- Region

Tooltip:
- Sales
- Profit
- Profit Margin

Filters:
- Date
- Region
- Customer Segment

## Design Principle Applied
- Time-series visualization
- Minimal clutter
- Clear comparison across regions

## Mistake Avoided
Avoided bar charts because they create unnecessary visual weight for long time periods.

---

# 2. Regional Performance View

## Business Question
Which regions generate the highest sales and profitability?

## Chart Type Selected
Horizontal Bar Chart

## Why This Chart Is Appropriate
Bar charts support accurate comparison across categories and allow fast identification of ranking and performance gaps.

Horizontal orientation improves readability for regional labels.

## Visual Encoding Used

Y-axis:
- Region

X-axis:
- SUM(Sales)

Color:
- Sales intensity (blue gradient)

Label:
- Sales

Tooltip:
- Profit
- Profit Margin
- Return Rate

Filters:
- Date
- Category

## Design Principle Applied
- Consistent scale
- Easy comparison
- Descending sorting

## Mistake Avoided
Avoided pie charts because they reduce precision and make ranking difficult.

---

# 3. Category Profitability View

## Business Question
Which categories and sub-categories create profit and which reduce margin?

## Chart Type Selected
Horizontal Bar Chart

## Why This Chart Is Appropriate
Category performance requires direct comparison across discrete groups.

Bar charts reveal profitable and weak performers immediately.

## Visual Encoding Used

Y-axis:
- Category
- Sub Category

X-axis:
- SUM(Profit)

Color:
- Category

Label:
- Profit Margin

Filters:
- Category
- Region

## Design Principle Applied
- Profit-first comparison
- Sorted ranking
- Limited color palette

## Mistake Avoided
Avoided treemaps because area comparison reduces margin visibility.

---

# 4. Customer Segment View

## Business Question
Which customer segments contribute most to business value?

## Chart Type Selected
Grouped Bar Chart

## Why This Chart Is Appropriate
Segment comparison requires side-by-side evaluation rather than showing distribution.

Bars allow quick comparison of segment contribution.

## Visual Encoding Used

X-axis:
- Customer Segment

Y-axis:
- SUM(Sales)

Color:
- Profit Margin

Tooltip:
- Profit
- Return Rate
- Average Order Value

Filters:
- Region
- Category

## Design Principle Applied
- Comparative analysis
- Simple categorical encoding

## Mistake Avoided
Avoided stacked bars because they complicate segment comparison.

---

# 5. Shipping Performance View

## Business Question
Which shipping modes create delivery delays and operational risk?

## Chart Type Selected
Bar Chart

## Why This Chart Is Appropriate
Average delivery time across shipping methods is easiest to compare using bars.

Delay buckets add operational interpretation.

## Visual Encoding Used

X-axis:
- Ship Mode

Y-axis:
- AVG(Delivery Days)

Color:
- Shipping Delay Bucket

Label:
- Average Delivery Days

Filters:
- Region
- Ship Mode

## Design Principle Applied
- Operational clarity
- Meaningful color hierarchy

## Mistake Avoided
Avoided stacked averages because they distort delay interpretation.

---

# 6. Discount vs Profit View

## Business Question
How does discounting influence profitability?

## Chart Type Selected
Scatter Plot with Trend Line

## Why This Chart Is Appropriate
Scatter plots are best for evaluating relationships between continuous variables.

This chart reveals whether increasing discount levels improve or reduce profit.

## Visual Encoding Used

X-axis:
- AVG(Discount)

Y-axis:
- SUM(Profit)

Color:
- Category

Size:
- SUM(Sales)

Detail:
- Sub Category

Trend Line:
- Single overall trend line

Filters:
- Category
- Region

## Design Principle Applied
- Relationship analysis
- Controlled use of size encoding
- Reduced overlap

## Mistake Avoided
Avoided line charts because discount is not a time variable.

Avoided multiple trend lines to reduce clutter.

---

# 7. Return Analysis View

## Business Question
Where are returns creating business risk?

## Chart Type Selected
Bar Chart

## Why This Chart Is Appropriate
Return rates need direct comparison across categories and customer groups.

Bars make risk concentration easy to identify.

## Visual Encoding Used

Y-axis:
- Category

X-axis:
- Return Rate

Color:
- Return intensity

Tooltip:
- Segment
- Region
- Return %

Filters:
- Region
- Category
- Customer Segment

## Design Principle Applied
- Risk-focused color usage
- Clear hierarchy

## Mistake Avoided
Avoided pie charts because small differences in return rates become difficult to interpret.

---

# Dashboard-Level Design Decisions

## Layout Logic

Dashboard flow:

KPIs

↓

Business Growth

↓

Geographic Performance

↓

Product Performance

↓

Customer Performance

↓

Operational Efficiency

↓

Business Risk

This sequence guides leadership from performance measurement to business action.

---

## Color Strategy

Blue:
Sales and performance

Green:
Profit and healthy outcomes

Orange:
Operational concern

Red:
Risk and returns

Gray:
Supporting information

---

## Final Design Philosophy

The dashboard was designed to maximize business interpretation while minimizing visual clutter. Every chart was selected to answer a specific leadership question and support actionable decisions.