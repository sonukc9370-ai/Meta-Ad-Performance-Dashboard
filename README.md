# 📊 Meta Ad Performance Dashboard (Power BI)

[![Meta Ad Performance Dashboard](Images/image%20(2).png)](https://app.powerbi.com/view?r=eyJrIjoiZjBlOGE0ZDYtZDA3Mi00YjVmLTljMTUtZjM5NmFmMjkxNGI4IiwidCI6IjA1ODJiNDQ5LTFhZWEtNGM1ZC05YTE0LTA5NGZlYmI4NGFmNiJ9)
![Data Modeling](Images/data_model.png)

## 🚀 Introduction

This project is a comprehensive Power BI dashboard designed to analyze and visualize the performance of advertising campaigns on Meta platforms (Facebook and Instagram). The dashboard provides a high-level overview of key metrics and allows for deep-dive analysis into audience demographics, ad types, and campaign performance to drive data-driven marketing decisions.

---

## Problem Statement
The goal is to consolidate complex ad performance data into a single, interactive, and easy-to-understand report. This helps marketers and analysts to quickly:
* Track key performance indicators (KPIs) in real-time.
* Understand audience behavior and preferences.
* Identify high-performing and
    low-performing ads and campaigns.
* Optimize ad spend and improve return on investment (ROI).

---

## 🛠️ Technology Stack
* **Power BI Desktop:** Used for data modeling, analysis, and visualization.
* **Power Query:** Used for data cleaning, transformation, and ETL (Extract, Transform, Load).
* **DAX (Data Analysis Expressions):** Used for creating complex measures and calculated columns.

---

---

================================
DATA MODEL & SCHEMA
================================

---
[ FACT TABLE ]
---
(1) ad_events
    - ad_id (FK -> ads.ad_id)
    - Date (FK -> Custom_Calendar.Date)
    - user_id (FK -> users.user_id)
    - event_id (PK)
    - event_type
    - Hour
    - day_of_week
    - time_of_day

---
[ DIMENSION TABLES ]
---
(2) ads
    - ad_id (PK)
    - ad_platform
    - ad_type
    - campaign_id (FK -> campaigns.campaign_id)
    - target_age_group
    - target_gender
    - target_interests

(3) campaigns
    - campaign_id (PK)
    - name
    - start_date
    - end_date
    - duration_days
    - total_budget

(4) users
    - user_id (PK)
    - age_group
    - country
    - interests
    - location
    - user_age
    - user_gender

(5) Custom_Calendar
    - Date (PK)
    - Day
    - Day Name
    - Month
    - Month Name

---
[ SUPPORTING / UTILITY TABLES ]
---
(6) Measures
    - [This is an empty container table used to store all DAX measures for better organization.]

(7) Select dynamic Measure
    - [This is a disconnected parameter table holding the list of measure names. 
    - It is used to power the dynamic slicer, allowing users to change the 
      entire report's context (e.g., from 'Clicks' to 'CTR').]



## ✨ Key Features & Visuals

This dashboard is built with several key interactive features:

### 1. Interactive Filtering & Navigation
* **Platform Toggle:** Seamlessly switch between **Facebook** and **Instagram** data.
* **Dynamic Measure Selection:** A master slicer allows the user to change the entire report's context (e.g., from "Clicks" to "Engagement" or "Conversions"), which dynamically updates most charts.
* **Filter Panel:** A dedicated side panel for drilling down by **Campaign Name** and **Target Interest**.

### 2. 📈 KPI Overview (KPI Cards)
A top-level summary of the most critical metrics:
* Impressions, Clicks, Shares, Comments
* Purchases (Conversion), Engagement
* Click-Through Rate (CTR), Engagement Rate, Conversion Rate
* Total Budget & Avg. Budget Per Campaign

### 3. 👥 Audience Analysis
* **Performance by Gender:** Donut chart breaking down metrics by Male, Female, and All.
* **Performance by Age:** Histogram showing which age groups are most responsive.
* **Performance by Country:** A map visual (bubble map) highlighting geographic hotspots.

### 4. ⌛ Trend & Ad Type Analysis
* **Weekly & Hourly Trends:** Stacked bar and area charts to identify peak performance times and days.
* **Clicks by Calendar Month:** A calendar visual for selecting specific date ranges.
* **Analysis by Ad Type:** A detailed matrix comparing the performance of **Carousel, Image, Stories,** and **Video** ads against key metrics (IMPR, CLKS, CTR, PR, CR, ER).

---

## 💡 How to Use
To explore this dashboard:

1.  Clone this repository.
2.  Download the `.pbix` file.
3.  Open the file in Power BI Desktop.
4.  (Optional) If the dataset is included (`.csv` or `.xlsx`), you may need to update the data source path in Power Query.



