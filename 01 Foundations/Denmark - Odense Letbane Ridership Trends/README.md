# Odense Letbane Ridership Analysis (2022–2024)

## Project Overview
This project analyzes monthly ridership data for the Odense Letbane (light rail) between 2022 and 2024.  
The aim is to understand growth patterns, seasonal contributions, and recurring anomalies, and to build a foundation for future forecasting.

---

## Dataset
- **Source**: Simulated dataset designed to reflect realistic ridership patterns in Odense.  
- **Columns after cleaning in Power Query**:
  - `Date` – constructed from Year + Month (set to the first of each month).  
  - `Year` – used for grouping and filtering.  
  - `Month` – numeric month.  
  - `YearMonth` – text field for chronological axis labels (e.g., 01-2022).  
  - `Season` – Winter, Spring, Summer, Autumn (based on Danish calendar months).  
  - `SeasonOrder` – numeric helper column to sort seasons correctly.  
  - `Total Ridership` – monthly ridership count.  

### Notes on Data
The dataset was created for learning and portfolio purposes, with an emphasis on being realistic and defensible.  
Here is how the numbers were estimated:

- **Baseline (2022):**  
  Starting ridership was set at approximately 3.3 million annual passengers. This figure was chosen because it is in line with early operational expectations reported in Danish transport planning documents for new light rail systems of similar size.  

- **Growth assumptions (2022–2024):**  
  Ridership was modeled to grow at about 50–60 percent year-on-year in the first years, reflecting the typical adoption curve of new public transport systems (rapid early growth as awareness increases, then stabilizing).  

- **Seasonal patterns:**  
  - Spring and Summer months were given higher ridership values, reflecting stronger use during milder weather and higher student activity.  
  - Winter was modeled to remain strong due to commuting demand, but slightly below spring/summer.  
  - Autumn was modeled as slightly weaker, reflecting university transitions and fewer major events.  
  - December dips were built in to reflect holiday closures and reduced student commuting, a known feature in Danish mobility data.  

- **Distribution method:**  
  The annual totals were divided into monthly figures using these seasonal weights, ensuring consistency in both overall growth and seasonal variation.

This process created a dataset that is not official Odense Letbane data, but is structured and scaled in a way that makes analysis realistic and portfolio-ready.

---

## Data Preparation
Steps carried out in Power Query:
- Combined Year and Month into a single `Date` column.  
- Created a `Season` column using conditional logic.  
- Added `SeasonOrder` to allow sorting in the correct seasonal sequence.  
- Renamed columns for clarity (for example, `Letbane_Ridership` → `Total Ridership`).  

---

## Visuals and Measures
**1. Monthly Ridership Line Chart**  
- X-axis: `Date`  
- Y-axis: `Total Ridership`  
- Includes forecast to project the next 12 months.  
- Highlights overall growth and recurring December dips.  

**2. KPI Card – Percentage Increase Since 2022**  
- Custom DAX measure comparing the latest year to the 2022 baseline.  
- Shows overall growth of approximately 112 percent.  

**3. Seasonal Contribution to Ridership (Table)**  
- Ridership totals grouped by `Season`.  
- Includes a “% of Total” measure to show each season’s contribution.  
- Demonstrates that ridership gains are spread across all seasons.  

**4. Season Slicer**  
- Allows users to filter visuals by season to isolate seasonal performance.  

---

## Key Findings
- Ridership increased by approximately 112 percent from 2022 to 2024.  
- Seasonal contributions remain relatively balanced, with each season representing between 21 and 29 percent of ridership.  
- A consistent dip is visible each December, likely reflecting holiday travel patterns and university breaks.  
- Growth appears broad-based, suggesting system-wide adoption rather than dependence on one season or event.  

---

## Tools and Skills
- Power BI Desktop  
- Power Query for cleaning and transformation  
- DAX for creating measures (percentage increase, seasonal shares)  
- Dashboard design with consistent layout and formatting  
- Analytical storytelling through visuals and supporting text  

---

## Possible Extensions
- Combine ridership data with infrastructure expansion information (e.g., stops, new lines).  
- Add external context such as weather patterns, events, or population growth to explain seasonal variations.  
- Compare Odense with other Danish cities to provide benchmarks.  

---

## Author
Victoria Gardner  
Business Intelligence and Analytics Portfolio Project  
