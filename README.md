
# Campaing-1
Digital Marketing
1. Overview

The script creates and populates a digital marketing database called Digital_Marketing. It contains three core tables:
[Campaing Done.sql](https://github.com/user-attachments/files/23436396/Campaing.Done.sql)DROP DATABASE IF EXISTS `Digital_Marketing`;
CREATE DATABASE `Digital_Marketing`;
USE `Digital_Marketing`;
CREATE TABLE campaigns (
campaign_id VARCHAR(50) NOT NULL,
campaign_name VARCHAR(50),
start_date DATE,
end_date DATE,
budget DECIMAL(10,2),
objective VARCHAR(50),
PRIMARY KEY (campaign_id)
);
CREATE TABLE ad_performance (
performance_id INT AUTO_INCREMENT,
campaign_id VARCHAR(50),
_date_ DATE,
platform VARCHAR(50),
impressions INT,
clicks INT,
cost DECIMAL(10,2),
revenue DECIMAL(10,2),
conversions INT,
PRIMARY KEY (performance_id),
FOREIGN KEY (campaign_id) REFERENCES campaigns(campaign_id)
);
CREATE TABLE platforms (
platform_id INT AUTO_INCREMENT,
platform_name VARCHAR(50) NOT NULL,
monthly_active_users BIGINT,
PRIMARY KEY (platform_id)
);
INSERT INTO campaigns (campaign_id, campaign_name, start_date, end_date, budget,
objective)
VALUES
('1', 'Holiday Sales 2024', '2024-11-01', '2024-12-31', 5000.00, 'Increase Sales'),
('2', 'Brand Awareness Q4', '2024-10-01', '2024-12-31', 3000.00, 'Brand Awareness'),
('3', 'Back to School Promo', '2024-08-01', '2024-09-15', 4000.00, 'Increase Sales'),
('4', 'Product Launch', '2024-05-01', '2024-05-31', 7000.00, 'Generate Leads'),
('5', 'Black Friday Deals', '2024-11-20', '2024-11-30', 10000.00, 'Increase Sales'),
('6', 'Spring Clearance', '2024-03-01', '2024-03-31', 3500.00, 'Increase Sales'),
('7', 'Summer Discounts', '2024-06-01', '2024-06-30', 6000.00, 'Increase Sales'),
('8', 'New Year Campaign', '2024-12-15', '2025-01-15', 8000.00, 'Increase Sales'),
('9', 'Social Media Drive', '2024-09-01', '2024-09-30', 2500.00, 'Engagement'),
('10', 'SEO Boost', '2024-07-01', '2024-07-31', 4000.00, 'Brand Awareness'),
('11', 'Flash Sale', '2024-02-01', '2024-02-05', 1500.00, 'Increase Sales'),
('12', 'Valentine Promo', '2024-02-10', '2024-02-15', 2000.00, 'Increase Sales'),
('13', 'Charity Event Drive', '2024-04-01', '2024-04-30', 5000.00, 'Community Engagement'),
('14', 'Easter Sale', '2024-03-20', '2024-04-01', 3000.00, 'Increase Sales'),
('15', 'Halloween Specials', '2024-10-15', '2024-10-31', 2500.00, 'Increase Sales'),
('16', 'Corporate Discounts', '2024-08-01', '2024-08-31', 4500.00, 'B2B Sales'),
('17', 'Gaming Promo', '2024-09-15', '2024-10-15', 5000.00, 'Increase Sales'),
('18', 'Health Awareness', '2024-06-01', '2024-06-15', 2000.00, 'Engagement'),
('19', 'Cyber Monday Deals', '2024-11-30', '2024-12-05', 9000.00, 'Increase Sales'),
('20', 'Loyalty Program Promo', '2024-07-15', '2024-07-31', 4000.00, 'Retention');
INSERT INTO ad_performance (
    campaign_id,
    _date_,
    platform,
    impressions,
    clicks,
    cost,
    revenue,
    conversions
)
VALUES
(1, '2024-11-01', 'Facebook', 5000, 250, 150.00, 500.00, 30),
(2, '2024-10-02', 'Instagram', 3200, 120, 95.00, 300.00, 15),
(3, '2024-08-03', 'Google Ads', 1500, 80, 50.00, 150.00, 10),
(4, '2024-05-04', 'Twitter', 1800, 90, 60.00, 200.00, 12),
(5, '2024-11-21', 'Facebook', 8000, 400, 250.00, 1000.00, 50),
(6, '2024-03-05', 'LinkedIn', 1200, 50, 70.00, 100.00, 5),
(7, '2024-06-06', 'Instagram', 2200, 110, 80.00, 220.00, 15),
(8, '2024-12-16', 'Google Ads', 4500, 300, 200.00, 700.00, 35),
(9, '2024-09-07', 'Facebook', 3300, 150, 130.00, 400.00, 20),
(10, '2024-07-08', 'Instagram', 2900, 140, 100.00, 350.00, 18),
(11, '2024-02-02', 'Twitter', 500, 30, 25.00, 50.00, 3),
(12, '2024-02-10', 'Google Ads', 800, 40, 35.00, 80.00, 5),
(13, '2024-04-15', 'Facebook', 2700, 120, 110.00, 300.00, 15),
(14, '2024-03-21', 'Instagram', 2500, 100, 90.00, 280.00, 12),
(15, '2024-10-16', 'Google Ads', 3500, 200, 180.00, 550.00, 25),
(16, '2024-08-10', 'LinkedIn', 1600, 70, 50.00, 150.00, 8),
(17, '2024-09-20', 'Instagram', 1900, 95, 70.00, 230.00, 12),
(18, '2024-06-02', 'Twitter', 1000, 50, 40.00, 120.00, 6),
(19, '2024-11-30', 'Facebook', 7000, 380, 240.00, 900.00, 45),
(20, '2024-07-15', 'Google Ads', 3100, 160, 120.00, 400.00, 20);

INSERT INTO platforms (platform_name, monthly_active_users)
VALUES
('Facebook', 2900000000),
('Instagram', 2000000000),
('Google Ads', 3500000000),
('Twitter', 500000000),
('LinkedIn', 900000000),
('Snapchat', 700000000),
('Pinterest', 450000000),
('TikTok', 1000000000),
('YouTube', 2300000000),
('Reddit', 430000000),
('WhatsApp', 2000000000),
('WeChat', 1300000000),
('Telegram', 700000000),
('Discord', 400000000),
('Quora', 300000000),
('Tumblr', 200000000),
('Bing Ads', 300000000),
('Amazon Ads', 150000000),
('Yahoo Ads', 100000000),
('Apple Ads', 200000000);
SELECT * FROM campaigns;
SELECT * FROM ad_performance;
SELECT
c.campaign_name,
a._date_,
a.platform,
a.impressions,
a.clicks,
a.revenue
FROM campaigns c
JOIN ad_performance a ON c.campaign_id = a.campaign_id;
SELECT
campaign_id,
impressions,
clicks,
(clicks * 100.0 / impressions) AS ctr_percentage
FROM ad_performance;
SELECT
campaign_id,
revenue,
cost,
(revenue - cost) AS profit
FROM ad_performance;
SELECT
campaign_id,
SUM(revenue) AS total_revenue
FROM ad_performance
GROUP BY campaign_id
ORDER BY total_revenue DESC
LIMIT 5;
SELECT
platform,
SUM(impressions) AS total_impressions
FROM ad_performance
GROUP BY platform
ORDER BY total_impressions DESC;
SELECT *
FROM campaigns
WHERE CURDATE() BETWEEN start_date AND end_date;



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
