# The Relationship Between 500hPa Geopotential Height,  Pacific North American (PNA) Pattern and Cold Air Outbreaks 
---
## Katherine Barragan
---

## Introduction
The goal of my CLIM 680 project is to investigate the relationship between the 500hPa geopotential height and 2 meter surface temperature during cold air outbreaks in North America.

The list of cold air outbreaks is from a paper by Erik T. Smith and Scott C. Sheridan from 2019- "The characteristics of extreme cold events and cold air outbreaks in the eastern United States"
Here they investigated cold air outbreaks in the eastern United States and used station data and used a set of critera to define what characterize these events as cold air outbreaks.

I choose this topic because I've have been reading scientific literature on the subject and have wanted to investigate the relationship between surface temperature and 500hPa for myself with the list of cold air outbreaks. 

I also explored the relationship between 500hPa with the Pacific North American (PNA) pattern climate index.

## Data
* NCAR Research Data Archive: ERA Interim Reanalysis- [500hPa (m<sup>2</sup>/ s<sup>2</sup>) ](https://climatedataguide.ucar.edu/climate-data/era-interim)
  - Jan 1, 1979 - Aug 31, 2019
  - Spatial: 0.75°x0.75°
  - Temporal Resolution: daily data taken at 0000 UTC 
  - Northern Hemisphere Latitude 0-90 Longitude (-180)- (180)
* NCAR Research Data Archive: ERA Interim Reanalysis - [2 meter temperature (K) - surface](https://climatedataguide.ucar.edu/climate-data/era-interim)
  - Jan 1, 1979 - Aug 31, 2019
  - Spatial: 0.75°x0.75°
  - Temporal Resolution: daily data taken at 0000 UTC
  - Northen Hemisphere Latitude: (-60)- (90) Longitude: (-180)- (180)
* PNA Index
  - The [PNA Index](https://www.cpc.ncep.noaa.gov/products/precip/CWlink/pna/norm.pna.monthly.b5001.current.ascii.table) is a monthly index, provided by NOAA/ESRL/PSL. It is located in /home/pdirmeye/classes/clim680_2022/CLIM_INDICES/ or on the NOAA Climate Prediciton Center Website.
  - 
* ECMWF Reanalysis v5 (ERA5)- [2 meter temperature (K) - surface](https://www.ecmwf.int/en/forecasts/dataset/ecmwf-reanalysis-v5)
  - Jan 1, 1979 - Aug 31, 2019
  - Spatial: 0.25° x 0.25°
  - Temporal Resolution: Originally 4x's daily data but processed to create a daily mean
  - North America: Latitude: 0-90 Longitude: (-180) - 0

---

## Results and Codes
---
### Function
Created a function to be able to process the monthly climatology and 2 meter temperature anomalies

### Conda Environment

### Analyses and Notebooks
Monthly Mean 500hPa
Link to notebook and describe results
Monthly Mean to T2M

Climatology by day for 500hPa
Link to notebook and describe results
Climatology by day for T2M

Anomalies for 500hPa
Link to notebook and describe results
Anomalies for T2M
Link to notebook and describe results

Calculate Composites between 500hPa and PNA
Link to notebook and describe results My Notebook

Calculate the Mean Difference between Composites with Significance
Link to notebook and describe results


Correlation between T2M and 500hPa anomalies during CAO 

Link to notebook and describe results



## Summary
From doing the analysis on the datasets, ......
I feel like I have a better understanding on how to manipulate climate datasets better. 
