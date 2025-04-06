# Vessel Operations Performance Dashboard
## Project Overview
This dashboard provides real-time updates on on-going vessel operations and crane activities at the port providing a comprehensive view of key performance indicators related to vessel activity, crane usage, and cargo handling. The primary objective of the dashboard is to enable users to monitor and track the efficiency of ongoing operations, promptly identify bottlenecks or issues, and take immediate remedial actions to optimize vessel port stay and overall port performance.

This dashboard is designed for display on a TV wall in the control room and configured to refresh every 30 minutes.

## Dashboard Walkthrough
Below is the overview page of the Power BI dashboard which shows the performance of vessels currently working at berth. 
The interactive dashboard can be found here.
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/screenshots/Vessel_Operations_Performance_Dashboard.png" alt="Overview Page"></p>

### The Card Visuals
The top card visual shows the vessels actively working at the quay, with each card representing a berth, distinguished by a consistent accent color applied consistently throughout the dashboard.
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/screenshots/Dashboard_Card_Visual.png" alt="Dashboard Card Visual"></p>

Each card displays:
- Vessel information: berth, name of the vessel, service, and shipping line.
- The most critical operational KPI: Port Hours Saved (PHS).
- Other KPIs: Crane Moves Per Hour (CMPH) and Total Moves (Sum of executed and balance), Crane Intensity (CI), Percent of Completion, and Required Time of Departure (RTD) to meet PHS target.

Additionally, each card functions as a navigation button, directing users the Vessel Operations Situation Report (SitRep) below.
This SitRep is used to keep shipping line agents and stakeholders informed on real-time vessel operations. Its goal is to facilitate seamless collaboration, ensuring timely vessel departures and efficient sailing operations.
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Vessel_Operations_Performance_Dashboard_2.png" alt="SitRep"></p>

The most recent vessel completed from each berth is show in the visual below:
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Dashboard_Card_Visual_2.png" alt="Dashboard Card Visual"></p>

### The Bar Charts
The visual below shows the timeline of vessels actively working at the quay with their corresponding Estimated Time of Departure (ETD) and Berth Moves Per Hour (BMPH).
The bar length represents the Estimated Port Stay (i.e time duration between the Actual Time of Arrival (ATA) and Estimated Time of Departure (ETD).
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/screenshots/Dashboard_Bar_Chart.png" alt="Dashboard Bar Chart"></p>

The visual below shows the crane working in each berth with their corresponding Estimated Time Of Completion (ETC) and Crane Moves Per Hour (CMPH)
The bar length represents the Estimated Crane Hours (i.e time duration between the First Container Lift and Last Container Lift.
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/screenshots/Dashboard_Bar_Chart_2.png" alt="Dashboard Bar Chart"></p>

## Data Preparation Process
1.	Data Extraction with SQL: 
    - Write SQL queries to extract raw data from source databases.
    - Perform transformations in SQL.

The following SQL queries were key takeaways from this project.
```sql
SELECT
  A.column1, A.column2, B.column3
FROM TableA AS A
JOIN TableB AS B ON A.key_column = B.key_column
WHERE A.condition_column = 'SomeCondition'
  AND A.id IN (
      -- Retrieve the the most recent vessel in each berth and phase
      SELECT TOP 1 WITH TIES A.id
      FROM TableA AS A
      JOIN TableC AS C ON A.join_key = C.join_key
      WHERE A.phase IN ('40WORKING', '50COMPLETE', '60DEPARTED')
      ORDER BY ROW_NUMBER() OVER (PARTITION BY C.berth, A.phase ORDER BY A.timestamp_column DESC)    
  );
```
2.	Power Query Loading & Transformation
3.	Data Modelling

## Data Model
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/screenshots/Data%20Model.png" alt="Data Model"></p>
