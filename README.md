# KrishnaTK_bitsom_ba_2511994_part1_data_cleaning
# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Project Overview

This project focuses on cleaning, validating, and preparing retail sales data for business reporting. The original dataset contained multiple data quality issues including inconsistent text formatting, missing values, duplicate records, invalid discounts, incorrect dates, and calculation mismatches.

The objective was to transform the raw dataset into a clean, analysis-ready dataset while documenting every cleaning decision and generating summary reports for business stakeholders.

---

# Repository Structure

```
part1_data_cleaning/
│
├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
│
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
│
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
│
└── README.md
```

---

# Problem Summary

The retail company exported order-level data from multiple internal systems. The exported data contained numerous quality issues affecting reporting accuracy and business decision-making.

This project cleansed and validated the dataset before producing business summary reports.

---

# Dataset Description

The dataset includes:

* Order Information
* Customer Information
* Product Information
* Category & Sub-Category
* Sales
* Cost
* Profit
* Discount
* Shipping Details
* Order Status
* Payment Status
* Geographic Information

---

# Tools Used

* Microsoft Excel 2019
* Excel Formulas
* Pivot Tables
* Conditional Formatting
* Data Validation
* Find & Replace
* Flash Fill
* Text to Columns

---

# Data Cleaning Steps

## Step 1

Preserved the original dataset as:

```
raw_orders.xlsx
```

---

## Step 2

Cleaned text fields

* Customer Name
* Segment
* Region
* State
* City
* Category
* Sub-Category
* Ship Mode
* Payment Status
* Order Status

using:

* TRIM()
* PROPER()
* SUBSTITUTE()
* Find & Replace
* Flash Fill

---

## Step 3

Validated dates

* Order Date
* Ship Date

Converted all valid dates into a consistent format.

Flagged:

* Missing dates
* Invalid dates
* Ship dates earlier than order dates

---

## Step 4

Handled duplicate records

* Removed exact duplicate rows.
* Flagged duplicate Order IDs containing conflicting information.

---

## Step 5

Applied business rules

* Missing Region → Unknown
* Missing Ship Mode → Unknown
* Missing Discount → 0 (when valid)
* Invalid Discount → Flagged
* Cancelled Orders excluded from completed sales
* Failed Payments excluded from completed sales
* Refunded Orders summarized separately
* Invalid shipping records flagged

---

## Step 6

Created calculated columns

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

---

# Business Rules Applied

* Missing Region replaced with **Unknown**.
* Missing Ship Mode replaced with **Unknown**.
* Missing Discount treated as **0** only when sales fields were valid.
* Negative Discount flagged as invalid.
* Discount above allowed range flagged as invalid.
* Cancelled Orders excluded from completed sales reports.
* Failed Payments excluded from completed sales reports.
* Refunded Orders summarized separately.
* Ship Date before Order Date flagged as invalid.

---

# Data Quality Issues Found

The following issues were identified during cleaning:

* Missing values
* Duplicate records
* Duplicate Order IDs
* Invalid discounts
* Invalid dates
* Shipping date issues
* Calculation mismatches
* Inconsistent text formatting

---

# Reports Generated

## Data Quality Report

Includes:

* Missing Value Summary
* Duplicate Summary
* Invalid Discount Summary
* Date Issue Summary
* Order Status Summary
* Sales & Profit Validation
* Final Clean vs Flagged Records

---

## Pivot Reports

Generated business summaries include:

* Sales and Profit by Region
* Sales and Profit by Category
* Sales and Profit by Sub-Category
* Order Count by Ship Mode
* Profit Margin by Customer Segment
* Refunded/Cancelled/Failed Orders by Region
* Monthly Sales Trend

---

# Key Business Insights

* Regional sales performance varies significantly.
* Product profitability differs across categories and sub-categories.
* Some shipping methods process substantially more orders than others.
* Cancelled, refunded, and failed-payment orders should be excluded from completed sales reporting.
* Data cleaning significantly improved reporting accuracy.

---

# Assumptions

* Discounts are represented as decimal values.
* Unknown values are acceptable replacements for missing Region and Ship Mode.
* Duplicate Order IDs with conflicting information require manual review.
* Cost represents the total order cost.

---

# Limitations

* Manual verification is required for conflicting duplicate Order IDs.
* Source-system errors cannot always be corrected automatically.
* Business rules may require revision if organizational policies change.

---

# Screenshots Included

* Raw Dataset Preview
* Cleaned Dataset Preview
* Pivot Summary 1
* Pivot Summary 2

---

# Conclusion

The dataset has been successfully cleaned, validated, standardized, and transformed into an analysis-ready format. Comprehensive data quality reporting, business rule validation, calculated metrics, and pivot summaries have been created to support reliable business analysis and decision-making.
