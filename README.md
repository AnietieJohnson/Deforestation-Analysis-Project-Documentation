# Global Deforestation-Analysis
## Introduction
This documentation outlines the steps and queries used to analyze deforestation data and country income groups using SQL. The project involves tasks such as determining the number of countries involved in deforestation, categorizing countries by income groups, comparing forest areas among different income categories, and identifying countries with the highest forest areas in each region.
## Data Sources
The following tables where imported and stored in a database called **Deforestation**
1. **Forest Area Data**:  A table named forest area containing information about **_country_code_**, **_country_name_**, **_year and forest_area_sqkm_**
2. **Land Area Data**: A table named Land area containing information about **_country_code_**,	**_country_name_**, **_year and total_area_sq_mi_**
3. **Regions Data**: A table named Regions containing details about **_country_name_**,	**_country_code_**,	**_region_**,	**_income_group_**
### Task 1: Total Number of Countries Involved in Deforestation
