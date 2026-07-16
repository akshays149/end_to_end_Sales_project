Advanced Analytical Report: 
RFM, Funnel, Cohort, and Performance Intelligence

## Overview
This report focuses only on the advanced analytical layers of the workbook rather than repeating a standard sales summary. The dataset contains 120 records from 2023-08-01 to 2023-11-09 across 10 salespeople, 2 products, and 6 regions, which is sufficient for segmentation, retention-style cohort analysis, funnel proxy review, productivity benchmarking, and performance scoring.

## Analytical Framework
The report is built around six advanced perspectives: RFM segmentation, funnel proxy analysis, cohort retention, productivity variance, Pareto concentration, and quality-adjusted performance review. This approach is more valuable than a simple ranking report because it links operational behavior to decision-making rather than only describing totals.

At a high level, the data shows three important patterns. First, revenue is relatively balanced at the team level, so deeper metrics are needed to separate strong performers from merely active ones. Second, the funnel and cohort views show that activity exists, but sustained high performance is limited. Third, RFM and efficiency analysis reveal clear differences between champion, loyal, at-risk, and low-quality performance profiles .

## RFM Segmentation
RFM analysis classifies performance using Recency, Frequency, and Monetary value. In this workbook, the model was applied at the salesperson level using latest activity for recency, record count for frequency, and total revenue for monetary contribution 
Salesman	Recency	Frequency	Monetary	Segment

Marco	77 	12 	885,800 	Champions
Kelly	57 	12 	875,800 	Loyal 
Noah	67 	12 	846,000 	Loyal 
Gordon	31 	12 	848,000 	Hibernating 
Mich	18 	12 	860,600 	At Risk 
Patrick	1 	12 	799,400	    At Risk 

The main insight is that raw totals do not tell the whole story. Marco stands out as the strongest all-round contributor because the model places him in the champion segment, while Kelly and Noah appear more stable than explosive, fitting the loyal profile. Gordon's hibernating label and the at-risk classification for Mich, Patrick, and Una show that not all contribution is equally durable or healthy over time.

The business implication is straightforward: the team should not be managed as one group. Champions and loyal performers should be studied for repeatable best practices, while at-risk and hibernating segments should receive coaching, pipeline review, and targeted support 

## Funnel Proxy
A traditional sales funnel was not available because the workbook does not include explicit lead stages. Instead, a proxy funnel was built using meaningful operational thresholds: total records, high activity calls, high sales output, high revenue output, and high client satisfaction.

Funnel Stage        	   Count
Total Records	            120 
High Activity Calls (>300)	117 
High Sales (>30)	         9 
High Revenue (>80000)	    28 
High Satisfaction (>0.75)	32 

This funnel is meaningful because it separates effort from outcomes. High activity is widespread, but only a small portion of records convert into very high unit-sales outcomes, which suggests that the main bottleneck is not effort generation but the conversion of effort into strong commercial results.
I
n practical terms, the business appears to have enough activity volume already. The stronger opportunity lies in improving call quality, conversion skill, customer targeting, and close effectiveness rather than simply pushing the team to make more calls.

## Cohort Retention
Cohort analysis tracks persistence after the first active period. In this workbook, each salesperson was grouped by first active month, and later activity was measured across subsequent monthly intervals.
Cohort Month	Month 0	Month 1	Month 2	Month 3
2023-08	         1.00 	0.50 	0.40 	0.10 

The pattern is steeply negative, falling from full participation in the starting month to only 10 percent by month 3. This suggests weak continuity in the activity pattern represented by the file, which matters because sustained commercial performance depends not only on spikes of activity but on repeat engagement over time.

From a managerial perspective, this is a retention-style warning sign. Stronger monthly review cycles, follow-up discipline, and recurring account plans would likely be more valuable than one-off performance pushes.

## Productivity Variance
One of the most important analyst shifts is to compare people against the team benchmark, not just against one another. Revenue totals can hide whether strong performers are efficient, sustainable, or dependent on excess effort.

Joe leads total revenue at 920,200, but Marco produces 10,802.44 revenue per hour compared with Joe's 9,789.36, and Marco also posts a stronger conversion proxy at about 0.082 versus Joe's 0.077. This means Joe leads in scale, but Marco appears stronger in productivity quality and operational leverage.

That distinction changes the business conclusion. If management rewards only totals, it may overvalue volume and undervalue scalable efficiency; if it rewards balanced productivity, Marco's profile becomes more strategically important than Joe's raw lead 

## Pareto Concentration
Pareto analysis asks whether a small share of performers drives most of the output. This matters because teams often appear balanced at first glance, yet still rely heavily on a few contributors for the majority of value 
In this dataset, revenue among the top performers is relatively close, which suggests weaker concentration than in many commercial teams, but the question remains important because even a moderate concentration effect can create management risk. The right analytical use of Pareto here is not only to identify top contributors, but to determine how much of total revenue would be exposed if one or two leading performers weakened 

## Quality-Adjusted Performance
High revenue is not always high-quality performance. Because the dataset includes positive, negative, and satisfaction metrics, performance can be judged not only on output but also on customer experience quality.

This is important because some performers can drive short-term revenue while damaging customer sentiment, which creates future churn or brand risk. A meaningful business analysis should therefore test whether high revenue is accompanied by healthy satisfaction and whether certain regions or salespeople show a pattern of commercial output with weak experience quality 

## Product and Region Opportunity
The workbook contains only two products, which makes mix analysis especially important because product underperformance cannot be diversified away easily. Product-level output files were prepared for revenue, unit volume, call activity, and satisfaction, which supports efficiency comparisons such as revenue per call and satisfaction-adjusted product contribution.

Region-level outputs were also prepared to compare revenue, units, and average satisfaction across six markets. The analytical goal is not only to rank regions, but to classify them into strongholds, underperformers, and hidden opportunities, especially where satisfaction is strong but revenue is still weak.

## Integrated Interpretation
Taken together, the analyses tell one coherent story. The business does not appear to have an activity problem, because the funnel shows high operational effort. It appears to have a conversion-quality and continuity problem, because very high performance is concentrated, cohort persistence drops sharply, and some performers are clearly stronger than others when efficiency and quality are considered together.

That makes the most meaningful management agenda clear. The first priority is to replicate champion behaviors from the strongest performers, especially those who combine solid monetary contribution with efficient execution. The second priority is to improve the middle and at-risk group through targeted intervention rather than blanket pressure, because the data suggests uneven quality of execution rather than insufficient total effort.

## Advanced SQL Questions
The following questions fit this advanced report structure more meaningfully than a basic sales summary:
•	Which salesperson leads on revenue, revenue per hour, and conversion proxy, and do these leaders differ?
•	Which salespeople perform above the team average on revenue, productivity, and satisfaction at the same time?
•	Which salespeople fall into champion, loyal, at-risk, and hibernating RFM segments?
•	What percentage of revenue is generated by the top 20 percent of performers?
•	Which performers make up the first 80 percent of cumulative revenue?
•	At which funnel stage does the largest drop-off occur?
•	Are high call volumes translating into high sales and high satisfaction, or only into activity?
•	How quickly does activity persistence decline across monthly cohorts?
•	Which product produces higher revenue per call and stronger satisfaction-adjusted performance?
•	Which region has low revenue but high satisfaction, indicating untapped opportunity?
•	Which salesperson creates strong revenue but weak customer quality, indicating sustainability risk?
•	Which performers should be rewarded, coached, or reassigned under a composite scorecard?

SQL Query Set
Revenue, Efficiency, and Conversion
```sql
SELECT
    Salesman,
    SUM(Revenue) AS total_revenue,
    SUM(Hours) AS total_hours,
    SUM(Calls) AS total_calls,
    SUM(Sales) AS total_units,
    SUM(Revenue) * 1.0 / NULLIF(SUM(Hours),0) AS revenue_per_hour,
    SUM(Sales) * 1.0 / NULLIF(SUM(Calls),0) AS conversion_proxy
FROM sales_dashboard
GROUP BY Salesman
ORDER BY total_revenue DESC;
```
Team-Average Variance
```sql
WITH team_avg AS (
    SELECT
        AVG(Revenue * 1.0) AS avg_revenue,
        AVG(Revenue * 1.0 / NULLIF(Hours,0)) AS avg_rev_per_hour,
        AVG([Client Satisfaction] * 1.0) AS avg_satisfaction
    FROM sales_dashboard
)
SELECT
    Salesman,
    AVG(Revenue) AS avg_revenue_per_record,
    AVG(Revenue * 1.0 / NULLIF(Hours,0)) AS avg_rev_per_hour,
    AVG([Client Satisfaction] * 1.0) AS avg_satisfaction
FROM sales_dashboard, team_avg
GROUP BY Salesman, avg_revenue, avg_rev_per_hour, avg_satisfaction
HAVING AVG(Revenue) > avg_revenue
   AND AVG(Revenue * 1.0 / NULLIF(Hours,0)) > avg_rev_per_hour
   AND AVG([Client Satisfaction] * 1.0) > avg_satisfaction
ORDER BY avg_rev_per_hour DESC;
```
RFM Base
```sql
WITH rfm_base AS (
    SELECT
        Salesman,
        DATEDIFF(DAY, MAX([Sale Date]), (SELECT DATEADD(DAY,1,MAX([Sale Date])) FROM sales_dashboard)) AS recency,
        COUNT(*) AS frequency,
        SUM(Revenue) AS monetary
    FROM sales_dashboard
    GROUP BY Salesman
)
SELECT *
FROM rfm_base
ORDER BY monetary DESC;
```

Funnel Proxy
```sql
SELECT 'Total Records' AS funnel_stage, COUNT(*) AS record_count FROM sales_dashboard
UNION ALL
SELECT 'High Activity Calls (>300)', COUNT(*) FROM sales_dashboard WHERE Calls > 300
UNION ALL
SELECT 'High Sales (>30)', COUNT(*) FROM sales_dashboard WHERE Sales > 30
UNION ALL
SELECT 'High Revenue (>80000)', COUNT(*) FROM sales_dashboard WHERE Revenue > 80000
UNION ALL
SELECT 'High Satisfaction (>0.75)', COUNT(*) FROM sales_dashboard WHERE [Client Satisfaction] > 0.75;
```

Cohort Setup
```sql
WITH base AS (
    SELECT
        Salesman,
        DATEFROMPARTS(YEAR([Sale Date]), MONTH([Sale Date]), 1) AS order_month,
        MIN(DATEFROMPARTS(YEAR([Sale Date]), MONTH([Sale Date]), 1)) OVER (PARTITION BY Salesman) AS cohort_month
    FROM sales_dashboard
),
cohort_data AS (
    SELECT
        Salesman,
        cohort_month,
        order_month,
        DATEDIFF(MONTH, cohort_month, order_month) AS cohort_index
    FROM base
)
SELECT cohort_month, cohort_index, COUNT(DISTINCT Salesman) AS active_salesmen
FROM cohort_data
GROUP BY cohort_month, cohort_index
ORDER BY cohort_month, cohort_index;
```
Pareto Contribution
```sql
WITH perf AS (
    SELECT Salesman, SUM(Revenue) AS revenue
    FROM sales_dashboard
    GROUP BY Salesman
), ranked AS (
    SELECT
        Salesman,
        revenue,
        SUM(revenue) OVER (ORDER BY revenue DESC ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW) AS cumulative_revenue,
        SUM(revenue) OVER () AS total_revenue
    FROM perf
)
SELECT
    Salesman,
    revenue,
    cumulative_revenue,
    ROUND(100.0 * cumulative_revenue / total_revenue, 2) AS cumulative_pct
FROM ranked
ORDER BY revenue DESC;
```

Quality Analysis
```sql
SELECT
    Salesman,
    SUM(Revenue) AS total_revenue,
    AVG([Client Satisfaction] * 1.0) AS avg_satisfaction,
    SUM(Positive) AS total_positive,
    SUM(Negative) AS total_negative
FROM sales_dashboard
GROUP BY Salesman
ORDER BY total_revenue DESC;
```

Product Efficiency
```sql
SELECT
    Product,
    SUM(Revenue) AS total_revenue,
    SUM(Sales) AS total_units,
    SUM(Calls) AS total_calls,
    SUM(Revenue) * 1.0 / NULLIF(SUM(Calls),0) AS revenue_per_call,
    AVG([Client Satisfaction] * 1.0) AS avg_satisfaction
FROM sales_dashboard
GROUP BY Product
ORDER BY total_revenue DESC;
```
Region Opportunity
```sql
SELECT
    Region,
    SUM(Revenue) AS total_revenue,
    SUM(Sales) AS total_units,
    AVG([Client Satisfaction] * 1.0) AS avg_satisfaction,
    SUM(Revenue) * 1.0 / NULLIF(SUM(Hours),0) AS revenue_per_hour
FROM sales_dashboard
GROUP BY Region
ORDER BY total_revenue DESC;
```

Window Function Ranking
```sql
SELECT
    Salesman,
    Region,
    SUM(Revenue) AS total_revenue,
    RANK() OVER (PARTITION BY Region ORDER BY SUM(Revenue) DESC) AS regional_rank,
    ROUND(100.0 * SUM(Revenue) / SUM(SUM(Revenue)) OVER (), 2) AS revenue_share_pct
FROM sales_dashboard
GROUP BY Salesman, Region;
```
Monthly Variance
```sql
WITH monthly AS (
    SELECT
        FORMAT([Sale Date], 'yyyy-MM') AS sale_month,
        SUM(Revenue) AS monthly_revenue
    FROM sales_dashboard
    GROUP BY FORMAT([Sale Date], 'yyyy-MM')
)
SELECT
    sale_month,
    monthly_revenue,
    LAG(monthly_revenue) OVER (ORDER BY sale_month) AS previous_month_revenue,
    monthly_revenue - LAG(monthly_revenue) OVER (ORDER BY sale_month) AS variance
FROM monthly
ORDER BY sale_month;
```

Composite Performance Scorecard
```sql
WITH perf AS (
    SELECT
        Salesman,
        SUM(Revenue) AS revenue,
        SUM(Revenue) * 1.0 / NULLIF(SUM(Hours),0) AS revenue_per_hour,
        AVG([Client Satisfaction] * 1.0) AS satisfaction
    FROM sales_dashboard
    GROUP BY Salesman
)
SELECT
    Salesman,
    revenue,
    revenue_per_hour,
    satisfaction,
    DENSE_RANK() OVER (ORDER BY revenue DESC) AS revenue_rank,
    DENSE_RANK() OVER (ORDER BY revenue_per_hour DESC) AS efficiency_rank,
    DENSE_RANK() OVER (ORDER BY satisfaction DESC) AS satisfaction_rank
FROM perf
ORDER BY revenue_rank, efficiency_rank;
```

## Recommendations
The most meaningful recommendation is to manage performance through a balanced framework instead of a pure sales-total lens. Revenue should be evaluated together with efficiency, conversion, persistence, and customer quality so that high effort is not confused with high performance.

Champion and loyal profiles should be used as internal benchmarks, while at-risk and hibernating segments should receive targeted recovery plans focused on pipeline quality, conversion skill, and account continuity. Funnel and cohort findings suggest that the main problem is not a shortage of activity, but weak conversion depth and weak continuity over time.

## Closing
This version of the report is intentionally centered on advanced analysis only. It is better suited for an analyst portfolio, case-study submission, or SQL interview discussion because it presents one meaningful analytical story built around segmentation, retention, conversion quality, and managerial action.



