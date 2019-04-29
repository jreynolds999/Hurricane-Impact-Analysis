# Predicting the Economic Loss due to Natural Disasters
Prepared by Chen Chen Chen, Matt Andrecovich and Jon Reynolds


## Table of Contents
- [Problem Statement](#Problem-Statement)
- [Data Dictionary](#Data-Dictionary)
- [Executive Summary](#Executive-Summary)
- [Conclusion and Recommendations](#Conclusion-and-Recommendations)

### Problem Statement 
Natural disasters are becoming more economically devastating to the areas that they affect. Given data from job sites such as Indeed and Glassdoor, is it possible to build a predictive model to estimate the economic losses for an area affected by a natural disaster? 

### Data Dictionary 
| Column Name                              | Description                                                                                                              |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Area Name                                | County Name                                                                                                       |
| Quarter                                  | The Quarter in 2017                                                                                            |
| No. Of Establishments                      | An establishment is an economic unit, such as a farm, mine, factory, or store, that produces goods or provides services. |
| Employment                               | Number of persons employed for the third month of the quarter selected.                                                  |
| One-Year Employment Gain/Loss (Percent)  | Percent change calculated from data for one-year prior.                                                                  |
| Average Weekly Wages                     | These are the total wages for all employees as submitted by employer reports. The unit is dollars.                       |
| On-Year Weekly Wages Gain/Loss (Percent) | Percent change calculated from data for one-year prior.                                                                  |
| Industry                                 | Industry of the respective data.                                                                                               |
| FIPS                                     | State code for first two digits, County code for last 3 digits. |
|Economic Value Quarterly                  | The total wage within a quarter.             | 
|Change EV(2~3)                            | The economic value change during second to third quarter.        |
|Change EV(2~3)                            | The economic value change during third to fourth quarter.        |



### Executive Summary 
Note: Reference 'Wage Loss by Industry and County' first, before proceeding to the 'Wage Loss Quarter Over Quarter' notebook. In our effort to make this as clear as possible, the notebooks have been labeled FIRST and SECOND

In regards to the natural disaster, we selected hurricanes and defined economic losses specifically as “wage losses”. We isolated the state of Texas and the impact it endured from Hurricane Harvey in August of 2017. Our goal was to analyze the impact of Harvey on a county by county, industry by industry basis in order to generate a predictive model that would be able to take inputs for each of the aforementioned variables and generate a range of predicted economic losses. We chose Harvey due to the massive damage that was inflicted on one section of Texas and the range of affected industries that occupied that zone. 

As our team dove into the above problem statement, we started with high hopes about this topic due to its scope and level of historical economic impact. Almost immediately however, we came to the conclusion that this was more difficult than we could have imagined for multiple reasons. First and foremost the two sources that were recommended in the prompt both have strict, explicit rules in their terms of service agreements about data collection. This included all of the methods that we were to attempt, making it clear that we were to come up with alternative data sources that not only were robust but also allowed the analysis of their data.

Our second foray into data collection involved public government data, specifically from FEMA, the US Census Bureau, and the US Bureau of Labor Statistics. According to the FEMA impact analysis, 41 out of the 254 counties in Texas were impacted to an extent such that they required federal aid. This represents approximately 16% of Texas. As we did the necessary EDA and data munging, we realized that it would be impractical to merge these different sources of data, as they were all missing key elements in relation to one another. For example, although FEMA’s dataset was robust, the different types of data such as “Public Assistance”, “Mitigation Assistance”, “Individual Assistance”, and “Disaster Type” were not within the scope of our timeframe for analysis and for that reason we moved away from FEMA. 

At the end of the EDA, it was clear that our best option was to move forward with the Bureau of Labor Statistics as the data was codified in a way that able for analysis. Specifically, the BLS data included industry specific changes, including average wages, employment numbers and county for each of those metrics. One downside to this choice was that we didn’t have truly granular data, as the BLS data was quarterly. This led to issues with our ability to identify and quantify trends, as hurricane impact typically last for a max of three months and didn’t make much of an impact on a quarterly analysis. Additionally, outside research into other hurricanes proved that the economic impact is widely varied, according to the geographic location that is hit as well as the population and average wages of the area. 

### Conclusion and Recommendations 
Despite our shortcomings in generating a working model, we did uncover some interesting short term trends in the aftermath of Hurricane Harvey. Interestingly, certain industries experienced wage increases while most others suffered. For example, the Mining and Professional Services industries both saw gains of approximately 1.7%, while other industries such as Education and Health Services saw a drop in weekly wages of 1.3%. Harris County was one of the most impacted, as they bore the brunt of the losses in both Construction as well as Leisure and Hospitality ($10 million and $2 million, respectively).

As we transitioned from predicting the economic losses to analyzing Harvey, we did outside research on historical hurricanes’ strength in Category ranking and their associated normalized economic impact. What we found was that there is an extremely large amount of variance in the economic losses sustained by hurricane-hit locations. As discussed prior, we believe that this is directly impacted by not only the strength of the hurricane, but also the amount of rain, geographic location, industries affected and finally population size and density. 

In attempting to build a predictive model, we recommend obtaining more granular data from other hurricanes, in regards to timeframe and storm details such as quantified wind and rain measurements. Ideally it would consist of all the available data for all known hurricanes, not limited to the US. Additionally, we theorized that clustering the locations prone to hurricanes would yield more actionable information. In total, this equates to nearly an entire overhaul of the current hurricane measurement system, which we believe to be severely lacking in its singular measurement of peak sustained wind speed.

