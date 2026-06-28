# Cleaning Log

## Project Information

**Project:** Business Data Cleaning, Validation & Excel Reporting

**Dataset:** Retail Order-Level Sales Data

**Tool Used:** Microsoft Excel 2019

---

# Objective

The objective of this project was to clean, validate, standardize, and prepare the retail order dataset for business reporting and analysis. The cleaned dataset improves data quality, supports accurate reporting, and ensures that business decisions are based on reliable information.

---

# Issues Found

During data exploration, the following issues were identified:

## Text Data Issues

* Leading and trailing spaces in text fields.
* Multiple consecutive spaces between words.
* Mixed uppercase and lowercase values.
* Inconsistent spellings of categories and sub-categories.
* Inconsistent customer, city, and state names.
* Missing values in Region.
* Missing values in Ship Mode.

---

## Date Issues

* Multiple date formats.
* Missing Order Date values.
* Missing Ship Date values.
* Ship Date earlier than Order Date.
* Invalid text values stored as dates.

---

## Duplicate Issues

* Exact duplicate records.
* Duplicate Order IDs containing conflicting business information.

---

## Discount Issues

* Missing Discount values.
* Negative Discount values.
* Discount values greater than the allowed business limit.

---

## Calculation Issues

* Sales values inconsistent with Quantity × Unit Price × Discount.
* Profit values inconsistent with Sales − Cost.
* Profit Margin not matching calculated profit.

---

# Cleaning Actions Performed

The following cleaning activities were completed:

* Preserved the original dataset as **raw_orders.xlsx**.
* Created a separate working file named **cleaned_orders.xlsx**.
* Removed unnecessary spaces using **TRIM()**.
* Standardized text formatting using **PROPER()**, **SUBSTITUTE()**, and Find & Replace.
* Corrected inconsistent category and sub-category names.
* Converted Order Date and Ship Date into a consistent Excel Date format.
* Filled missing Region values with **"Unknown"**.
* Filled missing Ship Mode values with **"Unknown"**.
* Replaced missing Discount values with **0** only when Quantity, Unit Price, and Cost were available.
* Flagged invalid discount values.
* Calculated Shipping Delay Days.
* Created calculated Sales, Profit, Profit Margin, Order Month, and Order Year columns.
* Removed exact duplicate records.
* Retained duplicate Order IDs with conflicting information and flagged them for manual review.
* Applied business validation rules to identify invalid records.

---

# Business Rules Applied

| Business Rule                     | Action Taken                                           |
| --------------------------------- | ------------------------------------------------------ |
| Missing Region                    | Replaced with "Unknown" and reported                   |
| Missing Ship Mode                 | Replaced with "Unknown" and reported                   |
| Missing Discount                  | Treated as 0 only when sales-related fields were valid |
| Negative Discount                 | Flagged as Invalid                                     |
| Discount Above Allowed Range      | Flagged as Invalid                                     |
| Cancelled Orders                  | Excluded from completed sales summaries                |
| Failed Payments                   | Excluded from completed sales summaries                |
| Refunded Orders                   | Reported separately                                    |
| Ship Date Earlier Than Order Date | Flagged as Invalid Shipping Record                     |
| Duplicate Order IDs               | Retained and flagged for manual review                 |
| Exact Duplicate Records           | Removed after verification                             |

---

# Calculated Columns Created

* cleaned_discount
* calculated_sales
* calculated_profit
* profit_margin
* shipping_delay_days
* order_month
* order_year
* data_quality_flag

---

# Assumptions Made

* Discounts are stored as decimal values between **0 and 1**.
* Unit Price represents the selling price per item.
* Cost represents the total order cost.
* Missing Region and Ship Mode values are replaced with **Unknown**.
* Duplicate Order IDs with conflicting information require manual business verification.
* Refunded and Cancelled orders remain in the dataset for reporting but are excluded from completed sales summaries.

---

# Records Removed

* Exact duplicate rows were removed after verification.
* No conflicting duplicate Order IDs were deleted automatically.

---

# Records Flagged

The following records were flagged for review:

* Duplicate Order IDs with conflicting information.
* Invalid Discount values.
* Missing dates.
* Invalid dates.
* Ship Date earlier than Order Date.
* Sales and Profit calculation mismatches.
* Invalid business rule violations.

---

# Limitations

* Conflicting duplicate Order IDs require manual review.
* Business rules cannot automatically resolve all source-system inconsistencies.
* Some missing values may require confirmation from operational systems.
* Historical data quality depends on source system accuracy.

---

# Output Files Generated

* cleaned_orders.xlsx
* data_quality_report.xlsx
* pivot_summary.xlsx
* cleaning_log.md

---

# Conclusion

The dataset has been cleaned, validated, and standardized for business reporting. All major data quality issues were documented, business rules were applied consistently, calculated fields were created, and summary reports were generated to support further business analysis.

