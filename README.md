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
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/solution%20to%20task%202.png)
### Task 3: Countries with Forest Area Greater Than Average High-Income Group
To answer this question effectively, I did a breakdown;
- get "high income"  in income groupclass
- get average of the above
- get name of countries that have a forest area greater than the average above.

-:- Note that this is a case of having a query with  double sub query, I wrote the subquery first following the steps I layed out above

Query to retrieve countries with forest area greater than the average forest area of the "High Income" group:


