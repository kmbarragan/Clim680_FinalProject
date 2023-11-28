# The Relationship between 500mb Geopotential Height, Pacific North America (PNA) Pattern and Cold Air Outbreaks
----
## Katherine Barragan
----
## Introduction
The goal of my CLIM 680 project is to investigate the relationship between the 500hPa geopotential height and 2 meter surface temperature during cold air outbreaks in North America.

The list of cold air outbreaks is from a paper by Erik T. Smith and Scott C. Sheridan from 2019- "The characteristics of extreme cold events and cold air outbreaks in the eastern United States"
Here they investigated cold air outbreaks in the eastern United States and used station data and used a set of critera to define what characterize these events as cold air outbreaks.

I choose this topic because I've have been reading scientific literature on the subject and have wanted to investigate the relationship between surface temperature and 500hPa for myself with the list of cold air outbreaks. 

I also explored the relationship between 500hPa with the Pacific North American (PNA) pattern climate index.

----
## Data
* NCAR Research Data Archive: ERA Interim Reanalysis- [500hPa](https://climatedataguide.ucar.edu/climate-data/era-interim)
  - Jan 1, 1979 - Aug 31, 2019
  - Spatial: 0.75°x0.75°
  - Temporal Resolution: daily data taken at 0000 UTC 
  - Northern Hemisphere Latitude (0) - (90) Longitude (-180)- (180)
* NCAR Research Data Archive: ERA Interim Reanalysis - [2 meter temperature (K) - surface](https://climatedataguide.ucar.edu/climate-data/era-interim)
  - Jan 1, 1979 - Aug 31, 2019
  - Spatial: 0.75°x0.75°
  - Temporal Resolution: daily data taken at 0000 UTC
  - Northen Hemisphere Latitude: (-60)- (90) Longitude: (-180)- (180)
* PNA Index
  - The [PNA Index](https://www.cpc.ncep.noaa.gov/products/precip/CWlink/pna/norm.pna.monthly.b5001.current.ascii.table) is a monthly index, provided by NOAA/ESRL/PSL. It is located in /home/pdirmeye/classes/clim680_2022/CLIM_INDICES/ or on the NOAA Climate Prediciton Center Website.
* ECMWF Reanalysis v5 (ERA5)- [2 meter temperature (K) - surface](https://www.ecmwf.int/en/forecasts/dataset/ecmwf-reanalysis-v5)
  - Jan 1, 1979 - Aug 31, 2019
  - Spatial: 0.25° x 0.25°
  - Temporal Resolution: Originally 4x's daily data but processed to create a daily mean
  - North America: Latitude: 0-90 Longitude: (-180) - 0

----
## Proposed Analysis
I plan to use the data sets above to conduct the following analysis:

* Calculate monthly mean, day of the year climatology and anomalies of 500hPa geopotential height and 2 meter surface temperature

* Calculate composites of 500hPa based on PNA phases

* Calculate the mean difference between composites of positive and negative phases of the PNA index with significance

* Calculate and compare composites with the PNA index along with an 'enhanced' PNA index

* Calculate the correlation map of 2 meter surface temperature and 500hPa anomalies

---
## Function
I created a function to be able to create the day of the year climatology and to be able to create the anomalies for the 2 meter temperature. 
---
## Conda Environment
The environment.yml file is provided to show the environment used to run all the codes. 
