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
Here is the text, updated to match the data model from your screenshot:🗂️ Data Model & SchemaThe data model consists of several tables, structured to support comprehensive analysis. The schema is designed in a star schema fashion, with one central fact table (ad_events) and multiple dimension tables.1. ad_events (Fact Table)This table contains all the individual event records related to the ads.Column NameDescriptionData Typead_idForeign key linking to the ads tableText/IDDateForeign key linking to the Custom_Calendar tableDateday_of_weekThe day of the week the event occurredTextevent_idPrimary key for the event recordText/IDevent_typeType of event (e.g., Click, Impression, Share)TextHourThe hour of the day the event occurred (0-23)Whole Numbertime_of_dayA category for the time (e.g., Morning, Afternoon)Text2. ads (Dimension Table)This table contains descriptive information about each ad.Column NameDescriptionData Typead_idPrimary key for the adText/IDad_platformPlatform where the ad was shown (e.g., Facebook)Textad_typeType of ad (e.g., Carousel, Image, Video)Textcampaign_idForeign key linking to campaignsText/IDtarget_age_groupThe intended age demographic for the adTexttarget_genderThe intended gender demographic for the adTexttarget_interestsThe intended interest group for the adText3. users (Dimension Table)This table contains demographic information about the users who interacted with the ads.Column NameDescriptionData Typeage_groupAge range of the userTextcountryCountry of the userTextinterestsThe user's interestsTextlocationSpecific location of the userTextuser_ageThe specific age of the userWhole Numberuser_genderThe gender of the userTextuser_idPrimary key for the userText/ID4. campaigns (Dimension Table)This table contains information about each marketing campaign.Column NameDescriptionData Typecampaign_idPrimary key for the campaignText/IDduration_daysThe total number of days the campaign ranWhole Numberend_dateThe date the campaign endedDatenameThe official name of the campaignTextstart_dateThe date the campaign startedDatetotal_budgetThe total budget allocated to the campaignDecimal Number5. Custom_Calendar (Dimension Table)This is a standard date dimension table used for time-based analysis.Column NameDescriptionData TypeDatePrimary key for the dateDateDayDay of the month (1-31)Whole NumberDay NameName of the day (e.g., Monday)TextMonthMonth number (1-12)Whole NumberMonth NameName of the month (e.g., January)Text

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



