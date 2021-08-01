# PyBer_analysis

## Table of Contents

- [Overview of PyBer Analysis](#overview-of-pyber-analysis)
- [Analysis Results](#analysis-results)
  * [Data Summary](#data-summary)
  * [Weekly Fares by City Type](#weekly-fares-by-city-type)
- [Summary](#summary)

## Overview of PyBer Analysis

The purpose of this analysis is to analyze ridership in different types of cities. Data such as city name, city type (i.e. urban, suburban and rural), number of drivers and total fares was retrieved and used for this analysis. The goal was to visualize and compare the ridership data based on city type. The client would like to improve access to ride sharing services and determine affordability for different types neighbourhoods.


## Analysis Results

**_Please refer to PyBer_Challenge.ipynb file for full code_**

### Data Summary

For the analysis, two sets of data, `city_data_df` and `ride_data_df`, were merged to form one complete `pyber_data_df` dataframe. To get an holistic overview of the data, a summary dataframe was created as seen in the figure below

**_FIGURE 1_ PyBer Summary DataFrame**

<img width="589" alt="Figure 1 PyBer Summary DataFrame" src="https://user-images.githubusercontent.com/86085601/127746522-749e2564-792c-4833-804f-f1a5fc8eae48.png">

As expected, there are more rides taken and drivers the more urban the city is. This then correlates to cheaper fares per ride on average. The table also shows that drivers in more urban areas have a lower average fare than their rural counterparts. A phenonemon like this is likely due to many factors such as larger driving options.

### Weekly Fares by City Type

The client requested to view the trends of total fares per city every week and would also like view the city types' trends relative to each other. To help visualize this, the first course of action was to convert the time data provided in the csv file using the code below
```
pyber_data_df['date']= pd.to_datetime(pyber_data_df['date'])
```

Having a proper date format for pandas, the time stamps were grouped into weeks using the following code
```
trips_df = trips_2019.resample('W').sum()
```

Now having all the data in a clean format, a line graph was created using the object oriented method to allow the client having a understanding of the trends of total fares trends of each city type while also being able to compare the trends of all the city types. The PyBer fare summary graph below shows the resulting graph from the analysis.

**_FIGURE 2_ PyBer Fare Summary**

![PyBer_fare_summary](https://user-images.githubusercontent.com/86085601/127746828-d3f9c2e3-6a6f-4714-bd1a-bb46394af329.png)

As expected, more drivers and rides in urban cities would result in more total fares every week. Although every city has its own unique trend, the line graph shows that the last week of February and the first week of April seem to be high points across the board. Now, further analysis would be show the reason for such a trend such possible beginning of March break at the end of February or the ending of school in April.


## Summary






