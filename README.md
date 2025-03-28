# Vessel Operations Performance Dashboard
## Project Overview
This dashboard provides real-time updates on on-going vessel operations and crane activities at the port providing a comprehensive view of key performance indicators related to vessel activity, crane usage, and cargo handling. The primary objective of the dashboard is to enable users to monitor and track the efficiency of ongoing operations, promptly identify bottlenecks or issues, and take immediate remedial actions to optimize vessel port stay and overall port performance.

This dashboard is designed for display on a TV wall in the control room and configured to refresh every 30 minutes.

## Dashboard Walkthrough
Below is the overview page of the Power BI dashboard which shows the performance of vessels currently working at berth. 
The interactive dashboard can be found here.
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Vessel_Operations_Performance_Dashboard.png" alt="Overview Page"></p>

### The Card Visuals
The top card visual shows the vessels actively working at the quay, with each card representing a berth, distinguished by a consistent accent color applied consistently throughout the dashboard.
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Dashboard_Card_Visual.png" alt="Dashboard Card Visual"></p>

Each card displays:
- Vessel information: berth, name of the vessel, service, and shipping line.
- The most critical operational KPI: Port Hours Saved (PHS).
- Other KPIs: Crane Moves Per Hour (CMPH) and Total Moves (Sum of executed and balance), Crane Intensity (CI), Percent of Completion, and Required Time of Departure (RTD) to meet PHS target.

Additionally, each card functions as a navigation button, allowing users to access Vessel Operations Situation Report (SitRep) below:
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Vessel_Operations_Performance_Dashboard_2.png" alt="SitRep"></p>

The most recent vessel completed from each berth is show in the visual below:
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Dashboard_Card_Visual_2.png" alt="Dashboard Card Visual"></p>

### The Bar Charts
The visual below shows the timeline of vessels actively working at the quay with their corresponding Estimated Time of Departure (ETD) and Berth Moves Per Hour (BMPH).
The bar length represents the Estimated Port Stay (i.e time duration between the Actual Time of Arrival (ATA) and Estimated Time of Departure (ETD).
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Dashboard_Bar_Chart.png" alt="Dashboard Bar Chart"></p>

The visual below shows the crane working in each berth with their corresponding Estimated Time Of Completion (ETC) and Crane Moves Per Hour (CMPH)
The bar length represents the Estimated Crane Hours (i.e time duration between the First Container Lift and Last Container Lift.
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Dashboard_Bar_Chart_2.png" alt="Dashboard Bar Chart"></p>

## Data Model
All tables have been aggregated to the highest level of granularity required for the visuals. The relationships between the tables are visually represented in the diagram below:
<p align="left"><img src="https://github.com/dmokafor/Vessel_Operations_Performance_Dashboard/blob/main/Screenshots/Data%20Model.png" alt="Data Model"></p>
