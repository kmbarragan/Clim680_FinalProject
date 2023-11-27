# The Relationship between 500mb Geopotential Height, Pacific North America (PNA) Pattern and Cold Air Outbreaks
----
## Katherine Barragan
----
## Introduction
The goal of my CLIM 680 project is to investigate the relationship between the 500hPa geopotential height and 2 meter surface temperature during cold air outbreaks in North America.

The list of cold air outbreaks is from a paper by Erik T. Smith and Scott C. Sheridan from 2019- "The characteristics of extreme cold events and cold air outbreaks in the eastern United States"
Here they investigated cold air outbreaks in the eastern United States and used station data and used a set of critera to define what characterize these events as cold air outbreaks.

I choose this topic because I've have been reading scientific literature on the subject and have wanted to investigate the relationship between surface temperature and 500hPa for myself with the list of cold air outbreaks. 

I also explored the relationship between 500hPa with the a climate index, Pacific North American (PNA) pattern.

----
## Data
* NCAR Research Data Archive: ERA Interim Reanalysis- [500hPa](https://climatedataguide.ucar.edu/climate-data/era-interim)
  - Jan 1,1979 - Aug 31, 2019
  - Spatial: 0.75°x0.75°
  - Temporal Resolution: daily data taken at 1200 UTC 
  - Northern Hemisphere Latitude 0-90 Longitude (-180)- (180)
* ERA
* PNA Index
  - The [PNA Index](https://www.cpc.ncep.noaa.gov/products/precip/CWlink/pna/norm.pna.monthly.b5001.current.ascii.table) is a monthly index, provided by NOAA/ESRL/PSL. It is located in /home/pdirmeye/classes/clim680_2022/CLIM_INDICES/ or on the NOAA Climate Prediciton Center Website.
----
## Proposed Analysis
I plan to use the data sets above to conduct the following analysis:

Calculate annual monthly mean, climatology and anomalies of 500hPa, and 2 meter surface temperature
Calculate composites of 500hPa based on PNA phases
Calculate the mean difference between composites of positive and negative phases of the PNA index with significance
Calculate and compare composites with the PNA index along with an 'enhanced' PNA index
Calculate the correlation map of 2 meter surface temperature and 500hPa anomalies

---
## Function
---
## Conda Environment
The environment.yml file is provided to show the environment used to run all the codes. 
