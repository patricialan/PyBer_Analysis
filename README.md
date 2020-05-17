# PyBer Analysis Report

## Background and Results

### Purpose
Data from PyBer, a ride-sharing app, was analyzed for trends. Findings will help improve access to ride-sharing services and determine affordability for underserved neighbourhoods.

### Resources
- Data sources: city_data.csv and ride_data.csv
- Software: Jupyter Notebook 6.0.3, conda 4.8.2, Python 3.8.2, pandas 1.0.3, and matplotlib 3.1.3

### Technical Analysis
Ride-sharing data from <[city_data.csv](Resources/city_data.csv)> and <[ride_data.csv](Resources/ride_data.csv)> were used. Data spanned the months of January 2019 to May 2019 and provided information on each ride in that period (fare, city, number of drivers in that city and city type: urban, suburban, or rural). See <[PyBer_Challenge.ipynb](PyBer_Challenge.ipynb)> for the analyses. 

Technical deliverables included a summary dataframe (SD; Table 1) and a multi-line graph (MG; Figure 1). The SD summarizes data for each city type, whereas the MG compares weekly fare for each city type over time. 

To create the SD, data from the two .csv files were merged into one dataframe. Then, values were calculated using pandas library functions groupby(), mean(), and sum().

To create the MG, data was extracted from the merged dataframe, and fares per date were calculated by grouping by date and city type. A pivot table was created to better tabulate the data for plotting. Dates and their corresponding fares were binned into periods of weeks. Finally, this data was plotted as the MG. 

### Results
The SD showed that:
- Total rides, total drivers, and total fares increased in order of these city types: rural, suburban, and urban.
- There was an inverse trend where average fare per ride decreased in order of rural, suburban, and urban city types. 

Table 1. Summary Dataframe
![summary_dataframe.png](summary_dataframe.png)

The MG showed that: 
- Total fares per week did not change much for each city type over the months of January to May 2019.
- Total fares per week were stratified amongst city types in descending order of urban (about $2,000-$2,500), suburban (about $900-$1,400), and rural (less than $500) cities. 

Figure 1
![Fig8.png](Fig8.png)

### Summary
Analysis of ride-sharing data revealed clear stratification in total rides, total drivers, total fares, and average fares according to city type (urban, suburban, and rural). Total fares did not show much change over January to May 2019. 

## Challenges Encountered and Overcome

### Challenges Encountered

* Programming
- Using correct code to graph with the object-oriented method (instead of the MATLAB method).
- Interpreting and applying official documentation for the libraries e.g. for pandas’ resample() function.  

* Data analysis
- Deciding which dataframe to use for a particular analysis e.g. determining the total drivers per city type.
 
* Graphing, etc
- Finding code to prevent labels from cutting off when saving a graph.
- Merging the “FiveThirtyEight” graph style code with other graphing code.  

### Overcoming Challenges & Technical Analyses Used
* Programming
- Internet searches of official documentation, Stack Overflow, and forums were performed to find examples of what code was used and how it was applied, followed by trial and error in Jupyter Notebook.

* Data analysis
- Review of the .csv files clarified that the dataframe created from city_data.csv, and not the merged dataframe, should be used to calculate total drivers per city type.

* Graphing, etc
- Internet search of Stack Overflow provided code to prevent labels from cutting off when saving a graph.
- “FiveThirtyEight” graph style code was incorporated through trial and error in Jupyter Notebook.

## Recommendations and Next Steps
- Further analyses are recommended to determine if there are accessibility and affordability issues in rural and suburban cities for PyBer ride-share. 

* Accessibility 
- Are there enough drivers for each city’s population?
- Are driver locations appropriately matched with areas of higher population density (certain neighbourhoods and areas of high activity e.g. city centers, malls, and transportation centers)

* Affordability 
- Is the higher average fare in rural cities due to farther distances driven? 
- What is the average income for the city types and is that correlated with number of rides?
- If rural cities showed ideal driver:population ratios and driver locations are matched to areas of higher population density, would people in rural cities use ride-share more if the fare was cheaper?

* Other questions
- Are people in rural and suburban cities as familiar with PyBer ride-share as urban cities and would PyBer benefit from increased marketing towards rural and suburban cities?

### Recommendations for Future Analysis

### Additional Analysis 1

* Description of Approach
To answer the question “Are there enough drivers for each city’s population?”, one could just calculate the ratio of drivers per city to city population (driver:population) and compare those values with an ideal or target ratio. City population data would need to be obtained. 

However, correlations between city population, driver count, and number of rides could also be visualized by plotting the three variables on a bubble plot. 

* Technical Steps
1. Population per city would be added to city_data.csv, and a merged dataframe would be created from city_data.csv and ride_data.csv.
2. Driver and ride counts per city would be calculated from the merged dataset using pandas library functions.
3. Matplotlib would be used to plot a bubble graph where the x-axis is city population, y-axis is driver count, and bubble size is ride count.
4. Good accessibility of PyBer services would result in a graph where driver counts and ride counts increase as population increases. This would result in urban cities clustered at the upper right quadrant, rural cities clustered at the lower left, and suburban cities in between. Also, bubbles would be larger in the upper right and smaller in the lower left. Deviation from this trend would indicate a mismatch between driver counts and city population. Cities that deviate from this trend could be identified as targets for marketing strategies. 

### Additional Analysis 2

* Description of Approach
To answer the question, “What is the average income for the city types and is that correlated with number of rides?”, two graphs could be created: a box and whisker graph to compare average income between city types, and a bar graph to assess utilization of PyBer ride-share based on the average income of a city.

* Technical Steps
1. Average income per city would be added to the city_data.csv, and a merged dataframe would be created from city_data.csv and ride_data.csv.

For the box and whisker graph:
2. Average income per city type would be calculated from the merged dataset using pandas library functions.
3. Matplotlib would be used to plot a box and whisker graph where x-axis labels would be city type and y-axis would be average income.
4. The box & whisker graph would allow comparison of average income between city types, help decide whether differences are statistically significant, and allow identification of outliers.

For the bar graph:
5. Pandas library functions would be used to:
6. Group the merged dataframe by city and determine the ride count per city. 
7. Create a new dataframe containing ride count per city and average income per city. 
8. This dataframe would be sorted by average income into bins (income ranges). Each bin would contain an average ride count per city.
9. Matplotlib would be used to plot a bar graph with income ranges as the x-axis and average ride count as the y-axis. There would be no direct comparison between city types. 
10. This graph would show whether there is a trend between the average income of a city and utilization of PyBer ride-share. It could show which cities (based on income) are more likely to use PyBer, which has implications for PyBer’s future expansion. 



