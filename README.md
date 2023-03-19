# sqlalchemy-challenge
 
## Part 1: Analyzing and Exploring the Climate Data

In this section, I use Python and SQLAlchemy to do a basic climate analysis and data exploration of climate database. Specifically, I use SQLAlchemy ORM queries, Pandas, and Matplotlib. 
1. I use the files 'climate_starter.ipynb' and 'hawaii.sqlite' to complete the climate analysis and data exploration.
2. I use the SQLAlchemy 'create_engine()' function to connect to the SQLite database.
3. I use the SQLAlchemy 'automap_base()' function to reflect the tables into classes, and then save references to the classes named station and measurement.
4. I link Python to the database by creating a SQLAlchemy session.

### Precipitation Analysis
Steps:
1. Finding the most recent date in the dataset.
2. Using that date, to get the previous 12 months of precipitation data by querying the previous 12 months of data.
3. Selecting only the "date" and "prcp" values.
4. Loading the query results into a Pandas DataFrame, and setting the index to the "date" column.
5. Sorting the DataFrame values by "date".
6. Plotting the results by using the DataFrame plot method, as the following image shows:
<img width="468" alt="precipitation" src="https://user-images.githubusercontent.com/114604829/226149061-27fa8c84-daaa-425b-9ac4-3d2c3b6d6435.png">
7. Using Pandas to print the summary statistics for the precipitation data.

### Station Analysis
Steps:
1. Designing a query to calculate the total number of stations in the dataset.
2. Designing a query to find the most-active stations (that is, the stations that have the most rows) by:
   - Listing the stations and observation counts in descending order.
   - Finding out which station id has the greatest number of observations.
3. Designing a query that calculates the lowest, highest, and average temperatures that filters on the most-active station id found in the previous query.
4. Designing a query to get the previous 12 months of temperature observation (TOBS) data by:
   - Filtering by the station that has the greatest number of observations.
   - Querying the previous 12 months of TOBS data for that station.
   - Plottting the results as a histogram with bins=12, as the following image shows:
   <img width="478" alt="station-histogram" src="https://user-images.githubusercontent.com/114604829/226149073-f9a38187-5a61-48ca-b2a3-337d318b4bd4.png">


## Part 2: Design Your Climate App

After completing the initial analysis, I design a Flask API based on the queries that I just developed. To do so, I use Flask to create the routes as follows:
1. /
  Start at the homepage.
  List all the available routes.

2. /api/v1.0/precipitation
  Convert the query results from your precipitation analysis (i.e. retrieve only the last 12 months of data) to a dictionary using date as the key and prcp as the
  value.
  Return the JSON representation of your dictionary.

3. /api/v1.0/stations
  Return a JSON list of stations from the dataset.

4. /api/v1.0/tobs
  Query the dates and temperature observations of the most-active station for the previous year of data.
  Return a JSON list of temperature observations for the previous year.

5. /api/v1.0/<start> and /api/v1.0/<start>/<end>
  Return a JSON list of the minimum temperature, the average temperature, and the maximum temperature for a specified start or start-end range.
  For a specified start, calculate TMIN, TAVG, and TMAX for all the dates greater than or equal to the start date.
  For a specified start date and end date, calculate TMIN, TAVG, and TMAX for the dates from the start date to the end date, inclusive.
range.
For a specified start, calculate TMIN, TAVG, and TMAX for all the dates greater than or equal to the start date.
For a specified start date and end date, calculate TMIN, TAVG, and TMAX for the dates from the start date to the end date, inclusive.
