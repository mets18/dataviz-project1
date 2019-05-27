-----------------------------------------
# Rutgers Data Science Bootcamp

#### Python Visualization Project ####
#### Yellow Taxi Vs. For Hire Vehicle (FHV)  Trend Analysis in NYC area ####


-----------------------------------------
#### Overall Project Approach ####
- Identify Parallel units of work, which can be developed and executed independently, without dependencies
- This approach also provides incremental insights into data and incremental delivery of analysis
- Final consolidation of the analysis in Project Presentation

#### Data Collection

Following Key sets of Data were used for this Analysis:
1. TLC Data (https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page) - Last 12 months of daily transactions (rides) of both Yellow Taxi and FHV .This file has a connection with TLC Locaton Master on Location ID
2. Average Temp, Perciptation and Snow in NYC for last 12 months from NOAA data
3. TLC - NYC Locations Master
4. Google Api use to find Airports in NC Area with their LAT & LONG

#### Data Wrangling and Preparation ####

1. Daily TLC Data was cleaned up, primarily removing bad data (such as NULL Values or Duplicate Values or where date of ride was out of last12 months horizon). CLeaned up data was summarized at Month and Ride Tyoe (aka Yellow Taxi and FHV) level
    - As TLC files were huge, a common process (Python Code) was executed by each team member to run the clean and create summary data.
2. Average Temp, Percipitation and Snow ( to analyze weather impact on use of TAxi vs.FHV) 
3. TLC Location master was enriched with the Lat and Long data (for each Location ID. Location ID was the reference key across TLC Transacstion DAta and Location Master)
4. Airports Location Summary was created using Google Places API

#### Steps to Prepare Data ####
1. Download data files on local machine (files sizes too big to fit into github allowble limit) from TLC for last 1 year for Yellow, Green and FHV Rides
2. Run TLC_rawdata_month_clean.ipynb for each monthly rides files for Taxis (Green and Yellow) and FHV. This process can be run in parallel across multiple machines. D not run parallel process on same machine as it hogs lot of resources to just process one file and may lead to memory issues.
3. Run combine_several_datasets.ipynb to aggregate data across Taxi (Yellow and Green Taxi combined under Taxi category) and FHV for each monthin one Data File.
4. TLC Location Master Enrichment process (TLCLocations.ipynb) can be run in parallel to the monthly rides files processed.
5. Run find_airport.ipnyb to collect all Airports Name and LAt, Long from Google Plcaes API. This process can alspobe run in parallel to monthly rides file processing and TLC Locations data enrichment.
6. Sports arena information was collected manually and stored in a file (sportsVenues.csv).


#### Analysis ####

Analsis was primarily focussed on: following Questions
1. In which areas are taxis more popular than FHVs?
2. Do places of interest (sports venues/airports) effect the preference of taxi vs. FHV?
3. What effect does weather (Temp, snow, rain) have on usage of yellow or green taxis vs. For-Hire Vehicles (FHVs)?

#### Analysis created ####
#### Running Taxi_vs_FHV_Analysis.ipynb ####
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
