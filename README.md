# Awesome-Chocolates
HR Analytics Dashboard

## Awesome Chocolates — HR Data Analytics Project
A structured, end-to-end data analytics project using Microsoft Excel to explore, clean, analyze, and visualize HR staff data across two regions: New Zealand (NZ) and India (IND).

![HR_Analytics](https://github.com/user-attachments/assets/801afde1-8924-4ae9-8b25-23f63b97bd92)

## Dataset Overview
Property        Detail
Total Records   212 rows (184 usable after cleaning)
Columns         Name, Gender, Department, Age, Date Joined, Salary, Rating, Country, Tenure, Bonus
Countries       New Zealand (NZ), India (IND)
Departments     Procurement, Website, Finance, Sales, HR

## Problems Identified and How They Were Solved
### Problem 1: 
- Two Separate Datasets Could Not Be Analyzed Together
### Situation: 
-The raw data came in two separate columns within the same sheet — NZ staff on the left, IND staff on the right — with no shared structure. This made cross-country analysis impossible.
### Problem: 
You cannot run pivot tables, filters, or aggregations across a side-by-side layout. Excel treats them as unrelated ranges.
Solution: Used Power Query to unpivot and stack both tables into a single unified dataset (StaffData sheet) with a Country column added to distinguish the source. This is the correct normalization approach — every row represents one employee, every column one attribute.
### Result: 184 clean records in one table, enabling all downstream analysis.

### Problem 2: Missing Gender Values (8 Records)
### Situation: 
-8 employees had no Gender entry — roughly 4.3% of the dataset.
### Problem: 
Ignoring this silently skews gender ratio calculations. Dropping rows loses legitimate salary and department data.
### Solution: 
Introduced an "Other" category rather than imputing or dropping. This preserves the data while making the gap transparent.
## Outcome:
-Gender         Count
-Male           90
-Female         86
-Other / Blank  8
