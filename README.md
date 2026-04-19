# project-completion-dashboard
Power BI dashboard analyzing project completion data 2019–2020

# Project Completion Dashboard 2019–2020

A Power BI dashboard analysing project completion data across 2019 and 2020,
built as part of my Google Data Analytics Certificate portfolio.

## Overview

This project analyses 42 projects completed across a two-year period, covering
project volume by work type, resource hours, employee output, and year-on-year
trends. The dashboard is designed to answer four specific business questions
using interactive visuals, DAX measures, and slicers.

## Business Questions Answered

1. How did the number of projects by Work Type Code compare in 2019 vs 2020?
2. Which were the top 3 projects by hours spent in Q3 and Q4?
3. How many projects did employee Big Bird complete, and which three required
   the least hours?
4. What was the average number of projects completed across both years?

## Key Findings

| Metric | Value |
|---|---|
| Total projects (2019) | 22 |
| Total projects (2020) | 20 |
| Average projects per year | 21 |
| Big Bird total projects | 8 |
| Highest hours project (Q3–Q4) | Cities of Gold — 500.76 hrs |
| Sharpest year-on-year decline | Development: 20 → 9 projects (−55%) |

## Dashboard Visuals

- **KPI 1** — Clustered bar chart: project count by Work Type Code, 2019 vs 2020
- **KPI 2** — Horizontal bar chart: top 3 projects by Sum of Hours in Q3 & Q4,
  with supporting data table
- **KPI 3** — Horizontal bar chart: Big Bird's 3 projects with least hours,
  with supporting data table
- **KPI 4** — Column chart with average reference line: project count by year

## Tools & Techniques

- **Power BI Desktop** — report building, visual formatting, slicers
- **DAX** — calculated columns (Year, Quarter), measures (Avg Projects,
  Distinct Count), AVERAGEX with CALCULATE for correct filter context
- **Microsoft Excel** — source data (Raw Data sheet)
- **Power Query** — data type validation and loading

## DAX Measures Used

```dax
-- Year column
Year = YEAR('Raw Data'[Date])

-- Quarter column
Quarter = QUARTER('Raw Data'[Date])

-- Average projects per year (correct filter context)
Avg Projects =
AVERAGEX(
    VALUES('Raw Data'[Year]),
    CALCULATE(DISTINCTCOUNT('Raw Data'[Project Code]))
)
```

## Insights & Recommendations

- Development and Preventive work categories declined significantly in 2020
  (−55% and −71% respectively), signalling a shift away from proactive work
  that may increase corrective demand in future periods.
- Three projects dominated hours in Q3–Q4, each exceeding 450 hours — a
  concentration that warrants review of project scoping and hour budgeting.
- Formalising projects into effort tiers (minor / standard / major) would
  improve capacity planning and reporting accuracy.

## About This Project

This dashboard is part of my portfolio as I transition from a 15-year career
in oil and gas engineering (CAD drafting to Senior Engineer) into data
analytics and data engineering. I completed the Google Data Analytics
Certificate in 2026 and am currently working toward IBM Data Engineering
Professional Certificate and PRINCE2 Foundation.

Connect with me on [LinkedIn](#) <!-- replace # with your LinkedIn URL -->
