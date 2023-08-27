# Global Deforestation Analysis
## Introduction
This documentation outlines the steps and queries used to analyze deforestation dataset using SQL. The project involves tasks such as determining the number of countries involved in deforestation, categorizing countries by income groups, comparing forest areas among different income categories, and identifying countries with the highest forest areas in each region.
## Data Sources
The following tables where imported and stored in a database called **Deforestation**
1. **Forest Area Data**:  A table named forest area containing information about **_country_code_**, **_country_name_**, **_year and forest_area_sqkm_**
2. **Land Area Data**: A table named Land area containing information about **_country_code_**,	**_country_name_**, **_year and total_area_sq_mi_**
3. **Regions Data**: A table named Regions containing details about **_country_name_**,	**_country_code_**,	**_region_**,	**_income_group_**
## Questions And Solutions to Project Task
### Task 1: Total Number of Countries Involved in Deforestation
- Deforestation occurred in different years
- Some countries were involved in deforestion in different years
- Hence they appear as duplicate in the **_country_name_** column
- To find actual number of countries involved, the count of distinct countries are expected.
Query to find the total number of countries involved in deforestation:
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/SOLUTION%20TO%20QUESTION%20ONE.png)
### Task 2: Income Groups of Countries with Specific Total Area Range
Query to identify countries with total area between 75,000 and 150,000 and their income groups:
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/solution%20to%20task%202.png)
### Task 3: Countries with Forest Area Greater Than Average High-Income Group
To answer this question "Retrieve the names of countries that have a forest area (in square kilometers) greater than the average forest area of all countries in the _'High Income'_ income group"
effectively, I did a breakdown;
- Get "high income"  in income group
- Get average of the above
- Get name of countries that have a forest area greater than the average above.

-:- Note that this is a case of having a query with  double subquery

Query to retrieve countries with forest area greater than the average forest area of the "High Income" group:
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/soluton%20to%20task%203.png)
### Task 4: Average Total Area for Different Income Groups
Calculate the average total area (in square miles) for countries in the "Upper Middle Income" income group? 
compare the result with the rest of the income categories.
- In this case comparism of individual results for average of area is expected, so I wrote a subquery that allows me to see all the income group by joining Land area table and Region table, then I queried the subquery(seeing it as a table) to give the the average total of the different groups by using the aggregate function **AVERAGE**

Query to calculate the average total area for different income groups:
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/SOLUTION%20TO%20TASK%204%20(2).png)

From the above query, the income group with the highest Average Total Area is the unknown income group, followed by the upper middle income group.
### Task 5: Total Forest Area for Different Income Groups
- I followed same procedure as in TASK 4
- Joined the forest area table and region table
- This time the aggregate function **SUM**
  
Query to calculate the total forest area for different income groups:
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/SOLUTION%20TO%20TASK%205.png)

From the above query, the income group with the highest Total forest area is the unknown income group, followed by the upper middle income group
### Task 6: Countries with Highest Total Forest Area by Region/Continent
To answer this question
(6): "What are the countries from each region or continent having the highest total forest area?"
- I wrote a subquery to join forest and regions table to get the neccesary column that is important to my solution
- I went further to write a second query to rank each country by region using the total_forest_area_sqkm as reference(rank was in decending order showing the highest as rank 1)
- Then I set the above as a table using CTE (common table expressions) and selected for countries that ranked top in each region

Query to find countries with the highest forest area in each region:
![](https://github.com/AnietieJohnson/Deforestation-Analysis-Project-Documentation/blob/main/solution%20to%20task%206.png)

## Conclusion
In this project, I delved into the analysis of global deforestation patterns and their correlation with country income groups. By utilizing SQL queries on the provided datasets, I was able to gain valuable insights into the extent of deforestation, income-based categorization, and distribution of forest areas across regions. The project's findings shed light on important aspects of environmental and socioeconomic dynamics. This project serves as a stepping stone for further research and actions to mitigate deforestation and promote sustainable land use practices worldwide.

## Insights
- **Extent of Deforestation:**
By calculating the total number of countries involved in deforestation, we gained a basic understanding of the global scale of deforestation. This metric serves as a starting point for further investigations into specific regions or income groups.
- **Income Group Analysis:**
The analysis of income groups in relation to forest area and deforestation showcased the diversity of trends. I found that some high-income countries exhibited forest area levels below average, hinting at varying conservation strategies or resource management practices.
- **Forest Area Comparisons:**
Exploration of forest areas across different income groups offered a comprehensive view of their distribution. It's clear that countries' income levels play a role in their forest areas, but there are exceptions that underline the importance of targeted policies.
- **Regional Forest Area Leaders:**
Identifying the countries with the highest forest areas in each region highlighted significant contributors to global forest cover. This information can aid conservation efforts and encourage collaboration among nations for sustainable forest management.
## Limitations
- The analysis relies heavily on the accuracy and completeness of the provided datasets. Any inaccuracies or missing data points could impact the results.
- The income group categorization might not encompass all nuances of economic disparities, and factors beyond income alone can influence deforestation rates.
- The analysis doesn't take into account other potential variables that might influence deforestation, such as government policies, climate conditions, and cultural practices since analysis was done based on data provided.
## Future Considerations
While this project provides a foundation for understanding deforestation and income group dynamics, future work could include:
- Integration of additional datasets: Consider incorporating datasets related to climate change and economic factors
- Time series analysis: Explore deforestation trends over time to identify patterns, changes, and potential causal factors.
