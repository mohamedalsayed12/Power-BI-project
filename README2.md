![Jobs Dashboard 2.0 overview](images/Project%202/overview.png)

# Jobs Dashboard 2.0 w/PowerBI

## Introduction
A follow-up to my first data jobs project, this one digs into what skills actually show up in data job postings and how pay stacks up across roles. It pulls in job counts, skill frequency, and salary by role, with slicers so you can filter down to a specific job title or country.

## What I Learned
This project is where Power BI stopped feeling like drag-and-drop and started feeling like actual data work. The KPI cards and bar charts were the easy part — the real learning happened writing my first "percent of total" measure in DAX. I wanted a bar chart where each skill's bar showed what share of all job postings mentioned it, not just the raw count, which meant reaching past the built-in aggregations for the first time.

That one measure taught me more about how Power BI actually thinks than anything else in the build. DIVIDE() instead of a plain "/" so a zero denominator doesn't throw an error. CALCULATE() to change the filter context rather than just reading the current one. And ALLSELECTED() specifically, because I needed the denominator to ignore the row-level filter on skill but still respect whatever the user picked in the slicers — a distinction that didn't click for me until I actually got it wrong a few times and saw the numbers not add up. I also ran into the small stuff that trips everyone up early on: a stray period where a comma should've been, mismatched parentheses, a table name I'd misspelled without noticing. None of it was complicated once I saw it, but it forced me to actually read DAX error messages instead of guessing.

I also learned to stop trusting a report just because it looked finished. I had a report theme applied where the title text color ended up matching the card background almost exactly, so half my titles were technically there but invisible. Chasing that down meant learning where Power BI actually stores title formatting — per-visual under Format, but also at the theme level under Customize current theme — and realizing a "finished" dashboard still needs a pass with fresh eyes, not just from me.

Small formulas and formatting bugs, but they're the kind of thing that separates knowing where the buttons are from understanding what a report is actually doing under the hood.
