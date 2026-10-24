# Retail Performance Dashboard: Revenue & Margin Analysis

An interactive business intelligence dashboard that analyses retail performance from January to June 2026 across four regions, three product categories, and two sales channels. It is built to answer one question:

> **Which regions and categories are driving or dragging revenue and margin, and where should management act?**

## Short Description

> A retail performance dashboard tracking revenue, gross margin, units sold, and returns by region, product category, and channel (In-Store vs Online), with region and month slicers to help management spot where to act.

## Dashboard Overview

![Dashboard screenshot](dashboard.png)

*(Save the dashboard screenshot as `dashboard.png` in the same folder so the image displays.)*

### KPI Cards

| Metric | Value |
|--------|-------|
| Total Revenue (USD) | 3.70M |
| Average Gross Margin | 39.76% |
| Units Sold | 95K |
| Returns Count | 3K |

### Visuals

| Visual | What it shows |
|--------|---------------|
| **Monthly Revenue by Region** (line chart) | Revenue trend for East, North, South, and West from January to June |
| **Revenue by Category and Channel** (clustered bar chart) | Revenue for Electronics, Apparel, and Home & Living, split by In-Store and Online |
| **Gross Margin % Matrix** | Average gross margin by Region and Product Category, with totals |
| **Region slicer** | Filter the whole dashboard by East, North, South, or West |
| **Month slicer** | Filter by month, January to June 2026 |

## Dataset

- **Source:** [Retail Performance Dataset on Kaggle](ADD-KAGGLE-LINK-HERE) (`retail_performance_dataset.csv`)
- **Size:** 72 rows and 11 columns, with no missing values
- **Coverage:** January to June 2026, 4 regions × 3 categories × 6 months, with 36 In-Store and 36 Online rows

| Column | Description |
|--------|-------------|
| `RowID` | Unique row identifier |
| `Month` | Month label (e.g. Jan-2026) |
| `MonthSort` | Sortable month key (e.g. 2026-01), used to order months correctly |
| `Region` | East, North, South, or West |
| `ProductCategory` | Apparel, Electronics, or Home & Living |
| `Channel` | In-Store or Online |
| `Revenue_USD` | Revenue in US dollars |
| `UnitsSold` | Number of units sold |
| `GrossMarginPercent` | Gross margin as a percentage of revenue |
| `ReturnsCount` | Number of returned items |
| `CustomerFootfall` | Number of customer visits |

## Key Insights

All figures below were calculated from the dataset and checked against the dashboard.

**Revenue**
- **North** is the largest region by revenue (USD 1.02M, about 28% of the total), followed by West (0.94M), East (0.91M), and South (0.83M)
- **Electronics** drives revenue, with USD 1.71M, about 46% of the total. Apparel brings in 1.08M and Home & Living 0.91M
- **Monthly trend:** revenue peaked in April, dipped in May, and recovered in June. North peaked at about 191K in April, and West showed the strongest June rebound at about 175K
- **Channels** are almost level (Online 1.86M vs In-Store 1.84M). In-Store leads in Electronics, while Online leads in Apparel and Home & Living

**Margin**
- **North is the biggest drag.** It has the largest revenue but the lowest margin in every category (35.96% overall), about 3.8 points below the company average of 39.76%
- **South** has the highest margin (41.59%) but the lowest revenue, so it is profitable but under-scaled
- **East** has the highest single margin cell in the matrix (Apparel, 43.95%)
- **Electronics** has the lowest category margin (38.71%) even though it is the largest category by revenue

**Returns**
- The overall returns rate is about 3.6% of units sold (3,450 returns on 94,882 units)
- **Apparel** has the highest returns rate (about 4.1%), and Electronics the lowest (about 3.4%)

## Suggested Actions for Management

1. **Fix North's margin first.** It is the largest region, so closing its 3.8-point gap to the average would add roughly USD 39K in gross profit over these six months at current revenue.
2. **Review Electronics pricing and costs.** It is nearly half of revenue, so small margin gains here matter most.
3. **Grow South.** It has the best margins but the lowest volume, which makes it a candidate for more marketing or distribution investment.
4. **Look into Apparel returns.** The higher returns rate may point to sizing, quality, or product description issues.
5. **Investigate the May dip.** Find out whether it was seasonal, a stock problem, or a promotion gap.

## How to Use

1. Open the dashboard file in Power BI Desktop (or the Power BI Service)
2. Use the **Region** and **Month** slicers to filter all visuals at once
3. Click a bar or line series to cross-highlight the other visuals

## Notes and Limitations

- **Average margin vs weighted margin:** the dashboard shows the simple average of margin percentages (39.76%). Weighted by revenue, the true overall margin is about 39.29%
- **Channel comparisons:** each region, category, and month combination appears in only one channel, so In-Store vs Online is not a like-for-like comparison
- **Small dataset:** with only 72 rows, perfectly balanced across regions and categories, the data looks illustrative or synthetic. Treat the findings as a demonstration of the method rather than a real-world business conclusion
- **Time span:** six months is too short to draw firm seasonal conclusions

## Tools Used

- Power BI (report, DAX measures, slicers)

## Possible Improvements

- Add a revenue-weighted gross margin measure
- Add a returns rate by region and category
- Add a margin trend line over time
- Highlight the lowest and highest margin cells in the matrix with conditional formatting
- Add a target or budget comparison for revenue and margin
- Add a revenue-per-footfall or conversion metric using `CustomerFootfall`

## License

This project is open for learning and educational use. Please check the Kaggle dataset page for the dataset's own license terms.
