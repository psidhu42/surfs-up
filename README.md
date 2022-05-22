# Surfs-up Hawaii Weather Data Analysis

## Overview of Project

Use SQLalchemy in Jupyter Notebook to view/interact with the 'hawaii.sqlite' database.

### Purpose

Extract the temprature data for June and December of every year available in the 'hawaii.sqlite' database using Jupyter Notebook and determine the summary statistics for both months. Analyse the summaries in order to determine if the surf and ice cream shop business is sustainable year-round.

## Results of Analysis

* The amount of temprature readings in December are lower than June by 183.

* There is an 8 degree diffrence in the minimum temperature reading between June and December, June being 64 and Decmber being 56.

* The averages of temprature for June and December is only 3.9 degrees diffrent.

!["June Temps"](https://github.com/psidhu42/surfs-up/blob/main/resources/june_temps.PNG) !["December Temps"](https://github.com/psidhu42/surfs-up/blob/main/resources/dec_temps.PNG)

## Summary

Looking at the results for June and December the average temprature only has a diffrence of about 4 degrees. June has an average of about 75 degrees where as December has an average of about 71 degrees. Based on this information it would be relatively safe for Mr. Avy to invest in and open the surf and ice cream shop. However two additional querries could be done to help improve the decision making. One querry could be looking at the percipitation for June and December. Another querry could be to look at a weather station near the location of the proposed shop, to get a more percise understaing of the weather in that location.

Examples of the results and code for the precipitation queries are provided below, one for June and one for December.

### June Precipitation

!["June Precipitation"](https://github.com/psidhu42/surfs-up/blob/main/resources/June_Precipitation.PNG)

```
# Write a query that filters the Measurement table to retrieve the precipitation for the month of June.

june_rain = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()

#Create a DataFrame from the list of precipitation for the month of June.

june_rain_df = pd.DataFrame(june_rain, columns=['Date','June Precipitation'])

june_rain_df.describe()
```

### December Precipitation

!["December Precipitation"](https://github.com/psidhu42/surfs-up/blob/main/resources/Dec_Precipitation.PNG)

```
# Write a query that filters the Measurement table to retrieve the precipitation for the month of December.

dec_rain = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()

#Create a DataFrame from the list of precipitation for the month of December.

dec_rain_df = pd.DataFrame(dec_rain, columns=['Date','December Precipitation'])

dec_rain_df.describe()
```