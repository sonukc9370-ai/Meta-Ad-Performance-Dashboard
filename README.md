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

## 🗂️ Data Model & Schema

The data model consists of several tables, structured to support comprehensive analysis. The schema is designed in a star schema fashion, with one central fact table and multiple dimension tables.

*(Your existing `![Data Modeling](Images/data_model.png)` image could also be moved here!)*

### 1. `fact_performance` (Fact Table)
This table contains all the quantitative performance metrics for each ad on a given day.

| Column Name | Description | Data Type |
| :--- | :--- | :--- |
| `Date` | Date of the ad performance record | Date |
| `Ad_ID` | Foreign key linking to the `dim_ads` table | Text |
| `Audience_ID`| Foreign key linking to the `dim_audience` table | Text |
| `Impressions` | Number of times the ad was shown | Whole Number |
| `Clicks` | Number of clicks on the ad | Whole Number |
| `Purchases` | Number of purchases (conversions) | Whole Number |
| `Shares` | Number of shares | Whole Number |
| `Comments` | Number of comments | Whole Number |
| `Budget` | Amount spent on that ad on that day | Decimal |

### 2. `dim_ads` (Dimension Table)
This table contains descriptive information about each ad.

| Column Name | Description | Data Type |
| :--- | :--- | :--- |
| `Ad_ID` | Primary key for the ad | Text |
| `Ad_Type` | Type of ad (e.g., Carousel, Image, Video) | Text |
| `Campaign_ID` | Foreign key linking to `dim_campaigns` | Text |
| `Platform` | (e.g., Facebook, Instagram) | Text |

### 3. `dim_audience` (Dimension Table)
This table contains demographic information about the target audience.

| Column Name | Description | Data Type |
| :--- | :--- | :--- |
| `Audience_ID` | Primary key for the audience segment | Text |
| `Gender` | (e.g., Male, Female, All) | Text |
| `Age_Range` | (e.g., 18-24, 25-34) | Text |
| `Country` | Country of the target audience | Text |
| `Interest` | Target interest group | Text |

### 4. `dim_campaigns` (Dimension Table)
This table contains information about each marketing campaign.

| Column Name | Description | Data Type |
| :--- | :--- | :--- |
| `Campaign_ID` | Primary key for the campaign | Text |
| `Campaign_Name` | The official name of the campaign | Text |

---


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



