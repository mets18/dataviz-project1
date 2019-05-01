-----------------------------------------
# Rutgers Data Science Bootcamp

#### Python Visualization Project ####
#### Yellow Taxi Vs. For Hire Vehicle (FHV)  Trend Analysis in NYC area ####


-----------------------------------------


#### Data Collection

Following Key sets of Data were used for this Analysis:
1. TLC Data - Last 12 months of daily transactions (rides) of both Yellow Taxi and FHV .This file has a connection with TLC Locaton Master on Location ID
2. Average Temp, Perciptation and Snow in NYC for last 12 months from NOAA data
3. TLC - NYC Locations Master
4. Google Api use to find Airports in NC Area with their LAT & LONG

#### Data Wrangling amd Preparation ####

1. Daily TLC Data was cleaned up, primarily removing bad data (such as NULL Values or Duplicate Values or where date of ride was out of last12 months horizon). CLeaned up data was summarized at Month and Ride Tyoe (aka Yellow Taxi and FHV) level
    - As TLC files were huge, a common process (Python Code) was executed by each team member to run the clean and create summary data.
2. Average Temp, Percipitation and Snow ( to analyze weather impact on use of TAxi vs.FHV) 
3. TLC Location master was enriched with the Lat and Long data (for each Location ID. Location ID was the reference key across TLC Transacstion DAta and Location Master)
4. Airports Location Summary was created using Google Places API

#### Analysis ####

Analsis was primarily focussed on: following Questions
1. In which areas are taxis more popular than FHVs?
2. Do places of interest (sports venues/airports) effect the preference of taxi vs. FHV?
3. What effect does weather (Temp, snow, rain) have on usage of yellow or green taxis vs. For-Hire Vehicles (FHVs)?

#### Analysis created ####
1. GoogleMap analysis for "Areas where Taxis are more Popular Vs FHV"  and do places of interests such as SPort Arenas, Airports impact choice of Taxi over FHV
2. Weather Impacts on choice of Taxi over FHV, based on 3 key data points:
    - Snow
    - Rain
    - Temp
    A Null Hyposthesis was created to conclude that:
    - Temp. wouldn't effect the willing people take a FHV or Taxi.
    - Rain would effect the willing people take a FHV or Taxi.
    - In snow days, people would like to choose FHV.

#### Key Conclusion ####
Data points taken were not sufficient to derive unbiased analsis. With additional data points, such as Price Points, Length of trips may show signifcant impact on the Analysis.
