# Social Media & Paid Ads Performance Dashboard (Power BI)

An interactive Power BI report that analyses social media ad performance across platforms, campaigns and countries, built around the core performance marketing KPIs: **CTR, CPC, CPM, CPE, engagement rate and conversion rate**.

## Overview

| | |
|---|---|
| Period | 1 Jan 2025 to 27 Sep 2025 |
| Scope | 2,964 posts, 6 platforms, 9 campaigns, 6 countries |
| Volume | about $408K ad spend, 49.6M impressions, 543K clicks, 36K conversions |
| Tools | Power BI Desktop, DAX |

## Report pages

1. **Social Media Performance:** posts, engagements, clicks, CTR, engagement rate and impressions, by platform and by month.
2. **Ads Performance:** total spend, CPC, CPE, CPM, conversion rate and conversions, with a platform cost comparison, spend share by platform, spend vs. conversions by month and a campaign-level KPI table.
3. **Post Performance & Region:** engagements by country and a map. This is a drillthrough page, so it is filtered to the campaign you drill in from.

Slicers on the pages: date, platform, objective, country and target audience age.

## KPI definitions (DAX)

```DAX
CPC                 = DIVIDE([Total Spend], [Total Clicks])
CPM                 = DIVIDE([Total Spend], [Total Impressions]) * 1000
CPE                 = DIVIDE([Total Spend], [Total Engagements])
CTR %               = DIVIDE([Total Clicks], [Total Impressions])
Engagement Rate %   = DIVIDE([Total Engagements], [Total Impressions])
Conversion Rate %   = DIVIDE([Total Conversions], [Total Clicks])
Prev Period Spend   = CALCULATE([Total Spend], DATEADD(DateTable[Date], -1, MONTH))
Spend vs Prev %     = DIVIDE([Total Spend] - [Prev Period Spend], [Prev Period Spend])
```

The model has one fact table, a date table and a separate measures table.

## Key findings

- Overall: CTR 1.09%, CPC $0.75, CPM $8.22, CPE $0.15, conversion rate 6.69%.
- TikTok is the most cost-efficient platform (lowest CPC and CPM) and the biggest driver of impressions and engagements.
- LinkedIn is the most expensive platform on CPC and CPM.
- Campaign CPC is very similar across the 9 campaigns ($0.71 to $0.80), so platform choice matters more than campaign choice for cost.

## Screenshots

<img width="648" height="361" alt="image" src="https://github.com/user-attachments/assets/7eb698dd-ce4c-4e30-923a-5521a8c5701f" />

<img width="641" height="368" alt="image" src="https://github.com/user-attachments/assets/71e99933-9bc3-416b-b266-b9fe3516d931" />

<img width="652" height="366" alt="image" src="https://github.com/user-attachments/assets/ddfea06e-d5bb-4d55-801a-33574fae56e5" />


## Files

- `SOCIAL_MEDIA.pbix`: the Power BI report (open with Power BI Desktop)
- `data/social_media_ad_performance_dataset.csv`: source data
- `screenshots/`: report page images

## Data

The dataset has 2,964 rows and 22 columns (date, platform, campaign, post, objective, ad format, audience age, country, impressions, reach, clicks, engagement breakdown, conversions and ad spend in USD). Source: [add the link to where you got the dataset and check its licence].

## Author

Karthik Venkataraju, M.Sc. Data Science, AI & Digital Business, Gisma University, Berlin  
[GitHub](https://github.com/karthik-0077)
