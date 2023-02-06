# API-Challenge
Requirements
The requirements for "Part 1: WeatherPy" are the following
Create Plots to Showcase the Relationship Between Weather Variables and Latitude (30 points)
Use the OpenWeatherMap API to retrieve weather data from the cities list generated in the started code (10 points)

Create a scatter plot to showcase the relationship between Latitude vs. Temperature (5 points)

Create a scatter plot to showcase the relationship between Latitude vs. Humidity (5 points)

Create a scatter plot to showcase the relationship between Latitude vs. Cloudiness (5 points)

Create a scatter plot to showcase the relationship between Latitude vs. Wind Speed (5 points)

Compute Linear Regression for Each Relationship (40 points)
Linear regression scatter plot for Northern Hemisphere: Temperature (C) vs. Latitude (5 points)

Linear regression scatter plot for Southern Hemisphere: Temperature (C) vs. Latitude (5 points)

Linear regression scatter plot for Northern Hemisphere: Humidity (%) vs. Latitude (5 points)

Linear regression scatter plot for Southern Hemisphere: Humidity (%) vs. Latitude (5 points)

Linear regression scatter plot for Northern Hemisphere: Cloudiness (%) vs. Latitude (5 points)

Linear regression scatter plot for Southern Hemisphere: Cloudiness (%) vs. Latitude (5 points)

Linear regression scatter plot for Northern Hemisphere: Wind Speed (m/s) vs. Latitude (5 points)

Linear regression scatter plot for Southern Hemisphere: Wind Speed (m/s) vs. Latitude (5 points)

The requirements for "Part 2: VacationPy" are the following (30 points)
Create a map that displays a point for every city in the city_data_df DataFrame (5 points)

Narrow down the city_data_df DataFrame to find your ideal weather condition (5 points)

For each city in the hotel_df DataFrame, use the Geoapify API to find the first hotel located within 10,000 metres of your coordinates (10 points)

Add the hotel name and the country as additional information in the hover message for each city in the map. (10 points)

__________________________________________________________________________________________________________________________________

Program 1: Weather PY

After importing the different libraries An API call is issued to retrive the current data. 
    There is an except loop present to prevent the call from getting stopped on one location.
    
Then the information that was saved in a json file is converted into a data frame: city_data

The data frame is then exported as a csv and then read as a csv

The date column is then cleaned up and then the process of building and exporting the scatter plots began.

I also imported the seaborn library to make the scatter plots easier to write

I also included an f-string for the title to make sure the chart's title will always display the data that it is currently representing and will change accordingly with a new set of data.

For the linear regression I created a function to call to help simplify the code since most of the other set is also repeatable.

This function would take the data passed to the x and y variables to both create the scatter plot and to create the linear regression line.

The lables names are also passed into the function as well as another f-string to help make it easier when I was constintly repeating the code.

Relationships:
    Latitude vs Max Temp: 
        The r value is much tighter in the Northern Hemisphere then the Southern half. 
        The Northern side also posses a negative corolation while the Southern side is moving in a positive direction. 
            This part was not as suprising since the expected trend was that it was warmer near the equator.
    Humidity vs. Latitude:
        The Northern Hemisphere does have more corrolation but they both have r values less then absolute value(.5)
        Both Hemispheres are trending in the same direction.
            Intresting since that means the Northern Hemisphere tends to get more humid the more north you go, but the south hemisphere does not share that.
    Cloudiness vs. Latitude
         The Southern Hemisphere does have more corrolation but they both have r values less then absolute value(.5)
         I would expect a few outliers to be altering the calculationsl for the Southern set.
    Wind Speed vs. Latitude
        The Southern Hemisphere does have more corrolation but they both have r values less then absolute value(.5)
         I would expect a few outliers to be altering the calculationsl for the Southern set.
         
         
__________________________________________________________________________________________________________________________________

Program 2: Vacation PY

The first part is importing dependencies followed by reading the city data csv that was written in the WeatherPy program and convert it to a data frame.

1) created a hvplot.point to create a interactive over a map based on the given data frame.

2) I narrow down the data frame and remove any incomplete rows.

3) I make a copy of the narrowed data frame to start fresh with specific columns and add a new column.

4) The next step is to make another API call to collect the hotel names with specific parameters and populate the new column.

5) Create another hvplot.point with the given information.

conclusion: I want to look at hotels and vacations near the equator durring the middle of winter
Note( the program was created and run in winter of 2023 so results may vary based on when the programs is run.)
