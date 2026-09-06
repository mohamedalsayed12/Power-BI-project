# Data Jobs Dashboard w/PowerBI
![Dashboard page 1](images/Project%201%20page%201/dashboard-overview.png)
![Dashboard page 2 - Business Analyst drill-through](images/Project%201%20page%202/business-analyst-drillthrough.png)
## Introduction
I built a Power BI project analyzing data job postings for people who are job hunting or thinking about switching roles, tracking job counts and average salaries over time, with a drill-through page for role-specific analysis (business analyst). I enjoy working at the intersection of data modeling and visual storytelling.

## Skills Showcased 
Power BI Desktop, built an interactive report from scratch using Power BI's core interface: importing data, creating visuals, and organizing content across multiple report pages.


Data Visualization, chose and configured chart types (bar, line, card visuals, etc.) to represent job counts and average salary trends clearly.

Report Page Design, designed a multi-page report layout, organizing a general overview page separately from a focused drill-down page for readability and flow.

Drill-Through Functionality, set up a drill-through page so users can click from the general data science jobs view into a filtered, role-specific view (business analyst).

Slicers & Filters, added interactive filters, so viewers can narrow down the data themselves.

Aggregation (built-in, non-DAX), used Power BI's native summarization options (Sum, Average, Count) to calculate job counts and average salaries without writing custom formulas.

Data Modeling (basic), structured the dataset within Power BI so fields could be grouped, filtered, and visualized correctly, even without formal table relationships.

Formatting & Storytelling, applied formatting, titles, and layout choices to make the report understandable to someone seeing the data for the first time.

KPI Indicators (Card Visuals), used KPI/card visuals to highlight key metrics at a glance, such as total job count and average salary, giving viewers an immediate snapshot before they dive into the detailed charts.

Tables, included table visuals to display detailed, row-level data alongside the charts, letting users see exact figures (job titles, counts, salary values) rather than relying on visuals alone.


---

# Jobs Dashboard 2.0 w/PowerBI
![Jobs Dashboard 2.0 overview](images/Project%202/overview.png)

## Introduction
A follow-up to my first data jobs project, this one digs into what skills actually show up in data job postings and how pay stacks up across roles. It pulls in job counts, skill frequency, and salary by role, with slicers so you can filter down to a specific job title or country.

## What I Learned
This project is where Power BI stopped feeling like drag and drop and started feeling like actual data work. The KPI cards and bar charts were the easy part. The real learning happened when I wrote my first percent of total measure in DAX. I wanted a bar chart where each skill's bar showed what share of all job postings mentioned it, not just the raw count, and that meant reaching past the built in aggregations for the first time.

That one measure taught me more about how Power BI actually thinks than anything else in the build. DIVIDE() instead of a plain slash, so a zero denominator doesn't throw an error. CALCULATE() to change the filter context instead of just reading the current one. And ALLSELECTED() specifically, because I needed the denominator to ignore the row level filter on skill but still respect whatever the user picked in the slicers. That distinction didn't click for me until I got it wrong a few times and watched the numbers not add up. I also hit the small stuff that trips everyone up early on, a stray period where a comma should've been, mismatched parentheses, a table name I'd misspelled without noticing. None of it was complicated once I saw it, but it forced me to actually read the DAX error messages instead of guessing.

I also learned not to trust a report just because it looked finished. I had a theme applied where the title text color ended up matching the card background almost exactly, so half my titles were technically there but invisible. Tracking that down meant figuring out where Power BI actually stores title formatting, per visual under Format, but also at the theme level under Customize current theme. A finished looking dashboard still needs a second pass with fresh eyes, not just from me.

Small stuff, a formula here, a color setting there, but it's the difference between knowing where the buttons are and understanding what the report is actually doing underneath.
