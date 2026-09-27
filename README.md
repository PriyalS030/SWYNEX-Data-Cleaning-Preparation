# SWYNEX-Data-Cleaning-Preparation
## FMCG Retail Dataset 2024-2026

## Dataset Overview
- 1800 transaction records across 10 columns
- Countries: Nigeria, United States, United Kingdom, Ghana, Turkey
- Categories: Groceries, Electronics, Home, Fashion

## Issues Found
1. 151 missing emails
2. 141 missing ages
3. 192 missing unit prices (stored as strings with commas!)
4. 180 missing quantities
5. 83 missing transaction dates
6. 161 missing payment methods
7. Inconsistent country names (nigeria/Nigeria, USA/United States)
8. Inconsistent categories (electronics/Electronics)
9. Inconsistent payment methods (card/Card)
10. 70 negative/invalid quantity values

## Cleaning Steps
1. Standardized country names → str.title() + replace()
2. Standardized product categories → str.title()
3. Standardized payment methods → str.title() + filled with mode
4. Fixed unit_price → removed commas, converted to float, filled with mean
5. Removed 70 negative quantity rows
6. Filled missing quantities with median
7. Filled missing ages with mean
8. Removed 83 rows with missing transaction dates
9. Converted transaction_date to datetime format
10. Left missing emails unchanged
11. Created new revenue column (unit_price × quantity)

## Result
- Original: 1800 rows
- Cleaned: ~1647 rows after removing invalid records
- New column added: revenue

## Tools Used
- Python 3
- Pandas
- Google Colab
