# PyBer Analysis

## Overview of the PyBer Analysis

As we continued study Python, we are able to use different dependencies and modules to process the given data and conduct analysis. In this Module, we used Pandas to process the ride-sharing data and created a new DataFrame that including the summary statistics of the data. Then we used Matplotlib to created charts based on the newly created DataFrame. 

In order to provide additional information to the decision-makers at PyBer we are going to use the same ride-sharing data to conduct a new analysis. We are going to create a summary DataFrame for the total weekly fare by city type, then use this DataFrame to create a multiple-line graph to better present the results. 

## Analysis

1.	Initial Process.
    Imported dependencies, loaded and read in the CSV files of city data and ride data. 

    ![ins1](https://user-images.githubusercontent.com/79289806/112741937-ddbcd980-8f57-11eb-94de-21f61ca0d5d1.png)

    Then merged the two datasets by “city” into one file. Before merge, checked that each “city” has unique record in the city         data file. This merge will be a many to one merge.

    ![ins2](https://user-images.githubusercontent.com/79289806/112741938-ddbcd980-8f57-11eb-84d4-97370a8da54b.png) 

2.	Create the Summary DataFrame by City Type.

    (1) 	Calculated total number of rides, total number of drivers, total amount of fares, average fare per ride, average fare             per driver for each city type respectively. In this calculation, used groupby() function to calculate the values by city           type. Used count() function to get the total numbers, sum() function to get the cumulative numbers, used mean() function           to get the average. 

    ![ins3](https://user-images.githubusercontent.com/79289806/112741939-ddbcd980-8f57-11eb-902b-d3e2cdd982fd.png) 

    (2) 	Used the Series created from the previous steps to create a PyBer summary DataFrame used the DataFrame() function. 

    ![ins4](https://user-images.githubusercontent.com/79289806/112741940-ddbcd980-8f57-11eb-8842-00c3ab025cb6.png) 

    (3)	  Cleaned up the DataFrame by deleting the index name and format each column.

    ![ins5](https://user-images.githubusercontent.com/79289806/112741941-ddbcd980-8f57-11eb-8449-4496e9973821.png) 

3.	Create a multiple line plot that shows the total weekly of the fares for each type of city.

    (1)	  Used the city and ride merged DataFrame from Step1 to create a new DataFrame for the sum of fares by date and city.               Included both “date” and “type” in the groupby() function in order to calculate the fare by both variables. Used the               sum() function to get the total amount of fares. 

    ![ins6](https://user-images.githubusercontent.com/79289806/112741942-de557000-8f57-11eb-945e-63a77d15454d.png) 

    (2)	  Reset the index in this new DataFrame, then used pivot() function to create a pivot table with “date” as the index,               “type” as the columns and “fare” as the values.

    ![ins7](https://user-images.githubusercontent.com/79289806/112741943-de557000-8f57-11eb-91db-253d78c9db79.png) 

    (3)	  Created a new DataFrame by using the loc[] function to select the data with date between 01JAN019 and 29APR2019. 

    ![ins8](https://user-images.githubusercontent.com/79289806/112741944-de557000-8f57-11eb-9bcf-be695b12fd3f.png) 

    (4)	  In order to get the total amount of fare in the date range from step(3), used to_datetime() function to convert the               index “date” to datetime datatype.

    ![ins9](https://user-images.githubusercontent.com/79289806/112741945-de557000-8f57-11eb-8481-8192086aa47a.png) 

    (5)	  Used resample() function by week “W” to get the sum of the fares for each week. 

    ![ins10](https://user-images.githubusercontent.com/79289806/112741928-dc8bac80-8f57-11eb-9465-3a63167d2abe.png) 

    (6)	  Used object-oriented interface create the multiple-line plot of the total amount of fares in each week by city type.

    ![ins11](https://user-images.githubusercontent.com/79289806/112741929-dd244300-8f57-11eb-87b3-7a15478c62b8.png) 

## Results

1.	The city and ride merged dataset contains all the columns from both datasets. In the following sample of the new DataFrame,       “date”, “fare” and “ride_id” are from the ride data, “driver_count” and “type” are from the city data. Column “city” is the       common column exists in both datasets.

    ![ins12](https://user-images.githubusercontent.com/79289806/112741930-dd244300-8f57-11eb-9883-4a1f99bbbbed.png) 

2.	Create the Summary DataFrame by City Type. 

    ![ins13](https://user-images.githubusercontent.com/79289806/112741931-dd244300-8f57-11eb-91d0-6efef4923fb4.png)

    The summary DataFrame showed:

    - 	Urban cities have the largest number of total rides and drivers, as well as the highest number of total fares among all           three city types. 

    - 	Due to the large number of total rides and drivers, Urban cities have the lowest “Average Fare per Ride” and “Average Fare         per Driver” among all three city types. 

    -	  Rural cities have the smallest number of total rides and drivers, as well as the Total Fares. However, these cities have           the highest “Average Fare per Ride” and “Average Fare per Driver” among these three city types. 

    -	  Although the Urban cities have the highest number of rides and drivers, the total number of rides is lower than the total         number of drivers, which is opposite in the other city types. 

3.	Create a multiple line plot that shows the total weekly of the fares for each type of city.

    (1)	  Sample of DataFrame for sum of fares by date and city type:

    ![ins14](https://user-images.githubusercontent.com/79289806/112741932-dd244300-8f57-11eb-92d8-43eb05abc57b.png) 

    The new DataFrame has date as the index, with the three city types as the columns. For each city type, when there is no record     for that date, the value will be filled with “NaN”.

    (2)	  Convert “date” to datetime datatype:

    Before:

    ![ins15](https://user-images.githubusercontent.com/79289806/112741933-dd244300-8f57-11eb-9acf-f9d5a6794d33.png) 

    After:

    ![ins16](https://user-images.githubusercontent.com/79289806/112741934-dd244300-8f57-11eb-93ab-4d2586358e46.png) 

    After conversion, the index “date” type changed to Datetime.

    (3)	  DataFrame for sum of fare by week:

    ![ins17](https://user-images.githubusercontent.com/79289806/112741935-ddbcd980-8f57-11eb-8957-ccec750c5b51.png) 

    (4)	  Multiple line chart:

    ![ins18](https://user-images.githubusercontent.com/79289806/112741936-ddbcd980-8f57-11eb-9016-c5e68b3c3bf9.png) 

    The chart above includes lines for each city type. 

    - 	The urban cities have the highest number of fares for each week between 01JAN2019 and 29APR2019.

    - 	Rural cities have the lowest number of fares for each week between 01JAN2019 and 29APR2019.

    - 	The weeks with the highest fare for each city type are:

        Urban: week of March 10th
        
        Suburban: week of February 24th
        
        Rural: week of April 7th


## Summary: 

The number of rides, drivers and fares varies among each type of cities. The summary statistics and line chart above showed that Urban cities have the largest number of rides and drivers, while Rural cities have the lowest. Here are the recommendations:

1.	Urban cities have the highest number of total rides and total drivers among all three city types, this might due to the size of the population in the Urban cities compared to the cities in the other city types. However, the total number of drivers is larger than the total number of rides in the Urban cities, with the lowest average fare per driver among all three city types. In order to keep the good size of drivers in these cities, the fare per driver could increase based on further analysis. 

2.	Rural cities have the lowest number of total rides and total drivers, however, the average fare for both rides and driver are the highest among all three city types. In order to expand the business in these cities, based on further analysis, the number of drivers could be increased based on promotions. However, the size of the population and the common travel distance in the rural cities are unclear in the current analysis. Further studies might need for the future strategies in these cities.  

3.	Suburban cities are in the middle among all three city types. There is a peak in the last week of February, and then the total fare decreased in March and remain low until the end of April. In order to increase the fare during this time period, the company might need to expand the number of drivers in these cities and lower the rate for ride. However, given that this analysis only focused on the first 4 months of 2019, we might need to collect more months of data to make better decision. 
