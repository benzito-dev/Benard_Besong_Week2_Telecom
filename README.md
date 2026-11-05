# Mobile Device Metrics Dashboard

An Excel dashboard that analyzes how 700 users use their mobile phones, to support user segmentation, product design, battery optimization and marketing.

## Business problem

A mobile technology company wants to understand how people use their phones so it can segment users and guide product design, battery optimization and marketing.

## Objectives

- Work out what the **User Behavior Class** represents and which questions the data can answer
- Profile each class by screen time, battery drain, data usage and apps installed
- Test whether demographics or usage behavior defines the classes
- Compare device models on battery drain and usage

## Dataset

One row per user: 700 users, 11 columns.
**Source:** "User Behaviour Dataset", provided for the internship project: https://drive.google.com/file/d/12RxyulkewkrhGnjRA4XUg0-6-spgsCUm/view?usp=sharing

| Column | Description |
|---|---|
| User ID | Unique user identifier |
| Device Model | Google Pixel 5, iPhone 12, OnePlus 9, Samsung Galaxy S21 or Xiaomi Mi 11 |
| Operating System | Android or iOS |
| App Usage Time (min/day) | Time spent inside apps |
| Screen On Time (hours/day) | Total time the display is on, including the lock screen and home screen |
| Battery Drain (mAh/day) | Battery used per day |
| Number of Apps Installed | Apps on the device |
| Data Usage (MB/day) | Mobile data used per day |
| Age | Age in years |
| Gender | Female or Male |
| User Behavior Class | Label from 1 to 5 |

**Derived column:** `Age_Category` (18-30, 31-40, 41-50, 51+), created from Age for the age pivots and slicer.

**About User Behavior Class:** the dataset does not define it. In the data it behaves as an ordinal usage-intensity label, from 1 (light) to 5 (extreme). Treat it as a category, not a number: do not average it.

## Workbook structure

| Sheet | Contents |
|---|---|
| Visualisation | The dashboard: KPI cards, charts and slicers |
| user_behavior_data | The Clean (prepared) data |
| Class Profile | Pivot tables by class: battery drain, screen time, data usage, class size |
| Device Model performance | Pivot tables by device model: battery drain, screen-on time, data usage, apps installed |
| Demographics | Pivot tables for gender, operating system and age category, plus gender and OS by class |
| Admin Configuration | Contain Validation Options|

## Dashboard

| KPI | Definition |
|---|---|
| Total Users | Count of User ID |
| AVG Battery Drain | Average of Battery Drain (mAh/day) |
| AVG Data Usage | Average of Data Usage (MB/day) |
| AVG Screen-On Time | Average of Screen On Time (hrs/day) |
| Heavy-User Share | Users in classes 4 and 5 divided by total users |

**Charts:** Gender Performance Per User Class, User Class Size, Average Battery Drain By Class, User Class Per Operating System Performance, User Class Per Data & Time Usage.

**Slicers:** Device Model, Gender, Age_Category, User Behavior Class.

## Findings

Usage rises steadily from class 1 to class 5, and demographics do not explain the classes. Full findings and recommendations are in the one-page **Mobile Device Metrics Report**.

## How to use

1. Open the workbook in Microsoft Excel and go to the **Visualisation** sheet.
2. Click the slicers to filter the dashboard. Hold **Ctrl** to select several buttons, and use the funnel icon to clear a filter.
3. If the data changes, go to **Data > Refresh All** to update the pivot tables and charts.
4. If a chart does not respond to a slicer, check **Slicer > Report Connections** and tick that chart's pivot table.

## Data notes and limitations

- The class definition is inferred, not documented.
- The data is a snapshot, so it shows association, not cause.
- Some rows show app usage time above screen-on time. These rows were flagged but not changed.
- The Android/iOS split (79% / 21%) reflects the model mix (four Android models, one iPhone), not a measured platform preference.
- There is no time-of-day, app-category, price or region data.

## Tools

Microsoft Excel: PivotTables, PivotCharts and Slicers.
