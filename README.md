# Global Deforestation-Analysis
## Introduction
This documentation outlines the steps and queries used to analyze deforestation data and country income groups using SQL. The project involves tasks such as determining the number of countries involved in deforestation, categorizing countries by income groups, comparing forest areas among different income categories, and identifying countries with the highest forest areas in each region.
## Data Sources
The following tables where imported and stored in a database called **Deforestation**
1. **Forest Area Data**:  A table named forest area containing information about **_country_code_**, **_country_name_**, **_year and forest_area_sqkm_**
2. **Land Area Data**: A table named Land area containing information about **_country_code_**,	**_country_name_**, **_year and total_area_sq_mi_**
3. **Regions Data**: A table named Regions containing details about **_country_name_**,	**_country_code_**,	**_region_**,	**_income_group_**
## Solutions to Project Task
### Task 1: Total Number of Countries Involved in Deforestation
Query to find the total number of countries involved in deforestation:
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/task%20one%20solution.png)
### Task 2: Income Groups of Countries with Specific Total Area Range
Query to identify countries with total area between 75,000 and 150,000 and their income groups:
