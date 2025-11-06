# App Usage Analytics
Power BI project analyzing mobile app usage and user engagement data.
# 📱 App Usage Analytics Dashboard (Power BI)

## Overview
This Power BI project analyzes mobile app usage patterns to uncover user engagement trends, productivity habits, and feature performance.  
The dataset includes daily records of user screen time, app launches, and interactions across multiple categories.

The goal of this analysis is to identify:
- Which app categories drive the most screen time
- How user engagement varies across apps
- The balance between productive and non-productive app usage
- YouTube-specific engagement trends (views, likes, and comments)

---

## Dataset Description
**Dataset:** [Screen Time and App Usage Dataset (iOS/Android)](https://www.kaggle.com/datasets)  
**Source Format:** CSV  
**Imported Into:** Power BI Desktop  

| Column | Description |
|---------|-------------|
| `user_id` | Unique identifier for each user |
| `date` | Date of recorded usage |
| `app_name` | Name of the application |
| `category` | Category or type of the app (e.g., Social, Productivity, Entertainment) |
| `screen_time_min` | Total screen time in minutes for that app on that date |
| `launches` | Number of times the app was opened |
| `interactiions` | Number of in-app interactions (clicks, taps, scrolls) |
| `is_productive` | Indicates if the app is classified as productive |
| `youtube_views` | Number of YouTube video views (if applicable) |
| `youtube_likes` | Total likes generated on YouTube |
| `youtube_comments` | Number of comments on YouTube videos |

---

## Dashboard Pages

### 🟢 **1. Usage Overview**
Key metrics and visuals:
- Total Screen Time (min)
- Average Screen Time per User
- Total App Launches
- Distinct Apps Used
- **Visuals:**
  - Line chart: Daily screen time trend
  - Donut chart: Usage by category
  - Stacked bar chart: Productive vs Non-Productive usage breakdown

---

### 🟡 **2. App Engagement**
Focuses on user engagement and behavior across apps:
- Top 10 Apps by Screen Time
- Average Interactions per Launch
- Scatter plot: Launches vs Interactions (to identify high-engagement apps)
- Table view with app-level metrics

---

### 🔵 **3. YouTube Analytics**
A focused view of YouTube-related engagement:
- KPIs: Total Views, Likes, Comments, and Engagement Rate (%)
- Column chart: Views by Date
- Table: Daily breakdown of YouTube activity

---

## DAX Measures

| Measure | Formula (Simplified) | Purpose |
|----------|----------------------|----------|
| **Total Screen Time (min)** | `SUM(AppUsage[screen_time_min])` | Total time users spent on apps |
| **Average Screen Time per User** | `DIVIDE([Total Screen Time (min)], DISTINCTCOUNT(AppUsage[user_id]))` | Engagement level per user |
| **Total Launches** | `SUM(AppUsage[launches])` | Total number of app openings |
| **Average Interactions per Launch** | `DIVIDE(SUM(AppUsage[interactiions]), [Total Launches])` | Interaction intensity per session |
| **Productive Usage (min)** | `CALCULATE([Total Screen Time (min)], AppUsage[is_productive] = "Yes")` | Productive time spent |
| **YouTube Engagement Rate** | `DIVIDE(SUM(AppUsage[youtube_likes]) + SUM(AppUsage[youtuve_comments]), SUM(AppUsage[youtube_views]))` | User engagement on YouTube |

---

## Key Insights
- Productivity apps account for **~38%** of total screen time.
- Social and Entertainment categories have the **highest launch frequency** but lower average engagement per session.
- The average user spends **3+ hours daily** across ~12 unique apps.
- YouTube engagement rate is **8–10%**, with weekend peaks in both views and likes.

---

## Tools & Skills Demonstrated
- **Power BI Desktop**
  - Data modeling and DAX calculations
  - Custom measures and calculated columns
  - Interactive dashboards with dynamic filters and drill-through
- **Data Cleaning** with Power Query
- **Data Visualization & Storytelling**
- **Business Analysis** and insight generation from usage data

---

## Screenshots / Demos
Example: ![Dashboard Preview](https://github.com/Eugene0913/app-usage-analytics/blob/main/App%20Usage%20Overview.png)
