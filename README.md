# Family Planning Dashboard

![Dashboard Preview](Dashboard%20Preview.png)

## Overview
The **Family Planning Dashboard** is a Power BI analytics solution designed to monitor and evaluate family planning program performance. Leveraging Excel data models and DAX formulas, this dashboard provides interactive visualizations of consumption trends, service delivery metrics, and resource allocation across states and facility types.

---

## Key Features

### 1. **Consumption Analytics**
   - **State-Level Tracking**:  
     - Opening balance, consumed, and lost resources (17.11M total).  
     - Year-over-year comparison (2023 vs. 2024).  
   - **DAX Measures**: Calculates utilization rates and loss ratios dynamically.

### 2. **Service Delivery Insights**
   - **Provider-Type Breakdown**:  
     - Volume and value metrics for 6 service types (e.g., PinnacleCare Centers, CivicHealth Outlets).  
     - Funding source analysis (1M transactions).  
   - **Excel Data Model**: Hierarchical categorizations with drill-down capabilities.

### 3. **Monthly Trends (RPM)**
   - **Time Intelligence**: DAX-powered monthly consumption rates (0.04M–0.3M range).  
   - **Forecasting**: Embedded trend lines for proactive planning.

---

## Technical Implementation

### Tools & Technologies
- **Power BI**: Interactive reports and dashboards.  
- **Excel**: Data modeling and preprocessing.  
- **DAX**: Measures for KPIs (e.g., `Consumption Rate = DIVIDE([Consumed], [Opening Balance])`).  

### Data Pipeline
1. **Source**: Excel files (cleaned and structured).  
2. **Transform**: Power Query for ETL.  
3. **Model**: Star schema with relationships.  
4. **Visualize**: Custom Power BI themes and bookmarks.  

---

## How to Use
1. **Open in Power BI**:  
   - Download `.pbix` file and launch in Power BI Desktop.  
   - Refresh data via **Home > Refresh** if connected to live sources.  
2. **Interact**:  
   - Filter by state, year, or provider type using slicers.  
   - Hover over visuals for tooltip details.  

---

## Setup Instructions
1. **Prerequisites**:  
   - Power BI Desktop (latest version).  
   - Excel (for raw data edits).  
2. **Deployment**:  
   - Clone this repo or download the `.pbix` file.  
   - Connect to your data source (edit in **Power Query Editor** if needed).  

---

## DAX Snippets
```dax
// Example: Monthly Consumption Growth
Growth Rate = 
VAR CurrentMonth = [Total Consumed]
VAR PreviousMonth = CALCULATE([Total Consumed], PREVIOUSMONTH('Date'[Date]))
RETURN DIVIDE((CurrentMonth - PreviousMonth), PreviousMonth)
