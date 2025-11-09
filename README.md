# Campaing-1
Digital Marketing
1. Overview

The script creates and populates a digital marketing database called Digital_Marketing. It contains three core tables:

campaigns – defines each marketing campaign.

ad_performance – stores detailed metrics on campaign performance across digital platforms.

platforms – contains metadata about social and advertising platforms, including active user counts.

The database is suitable for analysing marketing performance, campaign efficiency, and platform reach.
2. Database Structure
a. campaigns
| Column          | Type                     | Description                                            |
| --------------- | ------------------------ | ------------------------------------------------------ |
| `campaign_id`   | VARCHAR(50), PRIMARY KEY | Unique identifier for each campaign                    |
| `campaign_name` | VARCHAR(50)              | Campaign title                                         |
| `start_date`    | DATE                     | Start of campaign                                      |
| `end_date`      | DATE                     | End of campaign                                        |
| `budget`        | DECIMAL(10,2)            | Allocated budget                                       |
| `objective`     | VARCHAR(50)              | Marketing goal (e.g., Increase Sales, Brand Awareness) |
b. ad_performance
| Column           | Type                            | Description                                   |
| ---------------- | ------------------------------- | --------------------------------------------- |
| `performance_id` | INT AUTO_INCREMENT, PRIMARY KEY | Unique performance record                     |
| `campaign_id`    | VARCHAR(50), FOREIGN KEY        | Links to `campaigns` table                    |
| `_date_`         | DATE                            | Date of recorded performance                  |
| `platform`       | VARCHAR(50)                     | Digital platform (Facebook, Instagram, etc.)  |
| `impressions`    | INT                             | Number of times the ad was shown              |
| `clicks`         | INT                             | Number of ad interactions                     |
| `cost`           | DECIMAL(10,2)                   | Advertising spend                             |
| `revenue`        | DECIMAL(10,2)                   | Income generated                              |
| `conversions`    | INT                             | Successful customer actions (e.g., purchases) |
c. platforms
| Column                 | Type                            | Description                              |
| ---------------------- | ------------------------------- | ---------------------------------------- |
| `platform_id`          | INT AUTO_INCREMENT, PRIMARY KEY | Unique ID for each platform              |
| `platform_name`        | VARCHAR(50)                     | Platform name                            |
| `monthly_active_users` | BIGINT                          | Estimated number of monthly active users |
3. Data Insertion Summary

20 campaigns are inserted, spanning from early 2024 to early 2025.

20 performance records correspond to these campaigns, distributed across Facebook, Instagram, Google Ads, Twitter, and LinkedIn.

20 platforms are inserted, including Facebook (2.9B users), YouTube, TikTok, WeChat, and others.

The inserted data allows meaningful joins and aggregate analytics.4. Example Analytical Queries

The file ends with several SQL analyses:

Query	Description
SELECT * FROM campaigns;	Displays all campaigns
| Query                         | Description                                                         |
| ----------------------------- | ------------------------------------------------------------------- |
| `SELECT * FROM campaigns;`    | Displays all campaigns                                              |
| `JOIN ad_performance`         | Combines campaign and performance data for unified reporting        |
| CTR Calculation               | `(clicks * 100 / impressions)` measures ad click-through rates      |
| Profit Calculation            | `(revenue - cost)` estimates gross profit                           |
| Top 5 Campaigns by Revenue    | Uses `GROUP BY` and `ORDER BY`                                      |
| Total Impressions by Platform | Aggregates engagement by media channel                              |
| Active Campaigns              | Filters using `WHERE CURDATE()` between `start_date` and `end_date` |
5. Key Insights (from example queries)

Facebook and Google Ads appear as dominant platforms by both impressions and revenue potential.

Campaigns like “Black Friday Deals” and “Holiday Sales 2024” are designed for high-volume conversions.

CTR and profit calculations enable straightforward marketing ROI evaluation.
6. Recommendations for Improvement

Add data integrity constraints:

Use NOT NULL and CHECK constraints on numeric columns (cost ≥ 0, impressions ≥ clicks).

Normalize platforms:

Replace text platform names in ad_performance with platform_id foreign keys.

Add indexes:

Index campaign_id and _date_ for faster analytical queries.

Add derived analytics views:

For CTR, ROI, conversion rate, and cost per acquisition (CPA).
7. Conclusion

This database provides a solid foundation for a Digital Marketing Analytics System.
It can support:

ROI dashboards

Multi-platform ad performance reports

Temporal trend analysis

Campaign effectiveness evaluation

It’s production-ready once indexed and secured.
