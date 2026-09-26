IT Expenditure Analysis
The organization is facing challenges in effectively managing its IT expenditure, evidenced by significant variances between actual spending and both planned and forecasted budgets. This project provides a structured Excel-based analysis and interactive dashboard to identify where these discrepancies are occurring—across months, business areas, countries, cost elements, and IT areas—enabling leadership to understand the root causes and gain better control over future IT financial performance.

Data Source
File: IT Expenditure dataset.xlsx

Data Structure: Contains categorized IT financial data including Date, Business Area, Region, Country, IT Sub Area, IT Area, Cost Element Group, and Cost Element Sub Group.

Metrics: Actual, Forecast, and Plan amounts.

Data Cleaning & Transformation (Power Query)
The raw dataset required significant cleaning before analysis due to data fragmentation.

Exact Deduplication: Removed 1,929 exact duplicate rows (complete copy-paste artifacts).

Consolidation of Fragmented Rows: The original dataset split Actual, Forecast, and Plan values for the exact same categories across multiple distinct rows (resulting in over 56,000 fragmented records).

Power Query Grouping: Used Excel's Power Query (Data > From Table/Range) to group the data by all categorical columns (Date through Cost Element Sub Group) and applied a Sum aggregation to the Actual, Forecast, and Plan columns. This compressed the fragmented data into a clean, single-row-per-category format.

Calculated Metrics
The following custom columns were added to the cleaned dataset to enable variance tracking:

Variance vs Plan: =[@[Actual Total]] - [@[Plan Total]]

Variance vs Forecast: =[@[Actual Total]] - [@[Forecast Total]]

Dashboard Architecture
The analysis is driven by five interconnected Excel PivotTables and PivotCharts, built on the cleaned data sheet.

1. YTD Monthly Trend
Structure: Rows mapped to Date (filtered to exclude inactive months Sep–Dec). Values include sum of Actual, Plan, Forecast, and Variance vs Plan.

Visualization: Combo Chart (Lines for Actual/Plan/Forecast; Clustered Columns for Variance).

Purpose: Identifies timeline-based budget deviations (e.g., the massive January start-of-year underspend).

2. Variance by Business Area
Structure: Rows mapped to Business Area. Values mapped to Variance vs Plan. Sorted Smallest to Largest.

Visualization: Bar Chart.

Purpose: Highlights operational units missing budget targets (primarily R&D and BU).

3. Variance by Country
Structure: Rows mapped to Country. Values mapped to Variance vs Plan. Sorted Smallest to Largest.

Visualization: Bar Chart.

Purpose: Isolates geographic drivers of expenditure gaps (primarily the USA).

4. Variance by Cost Element Group
Structure: Rows mapped to Cost Element Group. Values mapped to Variance vs Plan. Sorted Smallest to Largest.

Visualization: Bar Chart.

Purpose: Identifies specific procurement or resourcing issues (primarily Labor and Hardware & Software).

5. Variance by IT Area
Structure: Rows mapped to IT Area. Values mapped to Variance vs Plan. Sorted Smallest to Largest.

Visualization: Bar Chart.

Purpose: Tracks functional IT alignment against original capacity planning.

Interactivity & Drill-Down
The dashboard utilizes Report-Connected Slicers (Business Area, Country, and IT Area) linked across all five PivotTables. This allows users to cross-reference data dynamically—for example, clicking "USA" instantly filters the Cost Element chart to reveal whether the geographic variance is driven by Labor or Hardware.
