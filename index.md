# The Relationship Between 500hPa Geopotential Height,  Pacific North American (PNA) Pattern and Cold Air Outbreaks

---- 
## Katherine Barragan
 ----
 
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
  - Northern Hemisphere Latitude (0)- (90) Longitude (-180)- (180)
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
  - North America: Latitude: (0)- (90) Longitude: (-180)- (0)

---
### Cold Air Outbreaks (CAO) 
Smith et al (2019) used a set of criteria to define what is considered to be a CAO. They used surface temperature data from 20 different stations in the Eastern United States and it spans from 1948- 2016. Using they're criteria they identified 49 CAO within their time span, relevant to ERA Interim there was only about 20. Their criteria for identification was 
 - Daily maximum and minimum temperatures required to be at least 1.25𝜎 below the 67 year daily climatological mean.
 - The duration must be at least 5 days in which the daily maximum and minimum temperatures are at least 1.25𝜎 below the climatological mean.
 - Requires that at least 3 of the 20 stations must simultaneously meet the prior two (2) criteria and be contiguous

### Pacific North American (PNA) Pattern 
A teleconnection pattern of air pressure anomalies at four locations over the Pacific Ocean and North America correlate with temperature anomalies across North America. It influences regional weather by affecting the strength and location of the East Asian jet stream, which leads to changes in the weather North America receives. It can be divided into two (2) phases: Postive phase and Negative phase. In positive (negative) phase there is a higher-than-normal (lower-than-normal) pressure near Hawai'i and over western US and Canada, and lower-than-normal(higher-than-normal) pressure south of Alaska and over the southeastern United States. There is also an increase in above-average (below-average) anomalies western Canada and US, and below-average (above-average) temperatures across south-central and southeastern states. During winter, there is less (more) precipitation in the Pacific Northwest and across the eastern US. 
[(NOAA)](https://www.climate.gov/news-features/understanding-climate/climate-variability-pacific-north-american-pattern)

<img width="552" alt="Screen Shot 2023-11-28 at 11 23 44 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/aa0d9f3c-21e4-4eff-a7c6-b1180a6c5ca1">
_Figure 1: Shown is the typical positive and negative phases of the PNA pattern at the 500-mb height. Taken from [NOAA's Climate Variability Website](https://www.climate.gov/news-features/understanding-climate/climate-variability-pacific-north-american-pattern)_

## Results and Codes
---
### Function
Created a function to be able to process the monthly climatology and 2 meter temperature anomalies

### Conda Environment 
[Environment](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/environment.yml)

### Analyses and Notebooks
**Monthly Mean 500hPa** 
- Calculated the monthly mean for the 2 meter temperature. Started by resampling the daily data to create a new dataset with just months then with the groupby function created a monthly mean and plotted in a multipanel plot display.

<img width="662" alt="Screen Shot 2023-11-28 at 11 12 39 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/7fac5589-1981-4218-8306-1b7d1486d05f">
_Figure 2: Shown is the monthly mean from the daily ERA Interim 500hPa Geopotential Height._

- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_500_MonthlyMean.ipynb)


**Monthly Mean to T2M** 
- Calculated the monthly mean for the 2 meter temperature. Started by resampling the daily data to create a new dataset with just months then with the groupby function created a monthly mean and plotted in a multipanel plot display.

  <img width="637" alt="Screen Shot 2023-11-28 at 11 13 27 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/baa6c07c-0029-4d9f-bc2f-f8e72edd4af1">
_Figure 3: Using the ERA Interim 2 meter temperatured daily data to create a monthly climatology._

- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_t2m_MonthlyMean.ipynb)


**Climatology by day along with Anomalies for 500hPa** 
- Calculated the the climatology using the groupby mean function using day of the year. From there created anomalies by subtracting the day of year groupby from the climatology. Then using a list of predefined Cold Air Outbreaks (CAO's) used then to selected those anomalies and plotted them in a multipanel plot based on the month during the winter season. At the end concatenated the list into one dataset and plotted all the CAO's all together.
- Some appear more intense than others and when comparing with the ranking provided by Smith 2019 some seem not as extreme as ranked using the 500hPA

<img width="568" alt="Screen Shot 2023-11-28 at 10 48 56 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/d74a70cc-edce-44af-92cc-aea6e315924a">
_Figure 4: Shown is the December CAO anomalies of the 500hPa Geopotential height. After creating a daily climatology, the anomalies were calculated then selected dates in December were plotted. List of CAO's based on Smith 2019._



<img width="656" alt="Screen Shot 2023-11-28 at 10 48 24 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/aef99ca1-6488-4f89-b4a8-5d38882a7042">
_Figure 5: Shown is the January CAO anomalies of the 500hPa Geopotential height. After creating a daily climatology, the anomalies were calculated then selected dates in December were plotted. List of CAO's based on Smith 2019._



<img width="652" alt="Screen Shot 2023-11-28 at 10 48 43 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/b2808490-4865-4ed7-aee3-b13d703024ed">
_Figure 6: Shown is the February CAO anomalies of the 500hPa Geopotential height. After creating a daily climatology, the anomalies were calculated then selected dates in December were plotted. List of CAO's based on Smith 2019._



<img width="642" alt="Screen Shot 2023-11-28 at 10 53 25 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/3076e542-1e37-487a-ae4f-468f6705fd63">
_Figure 7: Combining all three months to create a list of the collected CAO's. Using the 500hPa from ERA Interim, created daily climatologies and anomalies for the selected CAO dates from Smith 2019._

- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_Anomalies.ipynb)


**Climatology by day along with Anomalies for T2M** 
- Calculated the the climatology using the groupby mean function using day of the year. From there created anomalies by subtracting the day of year groupby from the climatology. Then using a list of predefined Cold Air Outbreaks (CAO's) used then to selected those anomalies and plotted during the winter season with all the CAO's in one plot. More or less to compare with the 500hPa
- With the temperature the intensity is really displayed better. Something happens with Dec 13, 1985. Doubled check the data and it just seems the values are higher for some reason. From the used the ERA5 dataset to do a similar process as initially and found out what it should about look like with ther ERA Interim dataset. All the other plots seem to match between the ERA Interim and ERA5 except Jan 6 1982. Again went through the climatology and anomalies and it seems when creating the anomalies for that day NaN's appear everywhere.
  
<img width="649" alt="Screen Shot 2023-11-28 at 11 13 44 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/242b13ae-19a5-4cf7-99d3-527264fb5b1c">
_Figure 8: Show is the ERA Interim 2 meter temperature used to create anomalies and shown are the listed CAO's from Smith 2019._

- [Notebook to ERA Interim](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_t2m_AnomFun.ipynb)


<img width="652" alt="Screen Shot 2023-11-28 at 11 12 22 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/ee279eeb-6ae2-40c1-b745-cf8560fce16e">
_Figure 9: Shown is the 2 meter temperature using the ERA5 data. It was used to explore what was going on with ERA Interim anomaly from Dec 12, 1986 (Figure 8) Nan values appear on the CAO 4 when creating the climatology which results in blank map._ 

- [Notebook to ERA 5](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_ERA5_Climatology.ipynb)

  
**Calculate Composites between 500hPa and PNA**
- Created a composite the 500hPa geopotential height and PNA index. After opening the PNA index, divided it into the positive phase and negative phase. From there with the 500hPa created anomalies similar to before and selected the 20 CAO's from Smith 2019. From there created the composite between the positive and negative phase and 500hPa. It appears more CAO's happen during the positive phase of the PNA index even appearing similar to the positive phase in the 500hPa

<p align="center">
 <img width="321" alt="Screen Shot 2023-11-28 at 10 54 04 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/21ae590a-8b66-4572-8a91-5ec62cc42b62">
 </p>
_Figure 10: Created a composite of the selected dates anomalies against the monthly PNA index._

- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_PNA_Composite.ipynb)



**Calculate the Mean Difference between Composites with Significance**
- Doing something similar to creating a composites with 500hPa and PNA but this time indicated a "enhanced" PNA index where anything above 1 would now be positive and below -1 would be negative. All those in between 1 and -1 would be considered neutral. Trying to see if maybe more intensely ranked CAO's are linked to this "enhanced" PNA index. They are not. The ranking is also from Smith 2019.
- Did something similar previously but now able to find the mean diffference between the positive and neutral phase and calculate the statistical significance.

<p align="center">
 <img width="352" alt="Screen Shot 2023-11-28 at 11 18 16 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/e899f6e3-b989-4efe-a5d8-4e5219321134">
</p>
_Figure 11: Shown is the composite of the 500hPa geopotential height and the "enhanced" PNA index to determine if CAO's occur more often during an "enhanced" phase. It unfortunately does not. More often it lands in a "neutral" phase with the "enhanced" positive phase coming in second._


<p align="center">
 <img width="275" alt="Screen Shot 2023-11-28 at 11 18 25 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/6882dbe1-31f8-48f7-9f7f-5b636a392ec6">
</p>
_Figure 12: Following prior image, created a mean difference composite plot between the "ehanced" positive and negative phase against the "neutral" phase._

<p align="center">
 <img width="363" alt="Screen Shot 2023-11-28 at 11 18 32 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/56a83f4a-8191-4d10-bdfe-94c8f3703778">
</p>
_Figure 13: Shown is the statistical significance between the composite difference of the "enhanced" positive phase and "neutral". Since it is using the few CAO's availabile might not have enough values to create a good correlation between the two._
  
- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/EnhancedPNA.ipynb)


**Correlation Map between T2M and 500hPa anomalies during CAO**
- Using many of the techinques from earlier now to create a correltion map between the 2 meter temperature and 500hPa maps during the pre-defined list of CAO's.
- After creating the anomalies for both datasets, created a correlation map and plotted it. From there used the scipy package to be able see the statistical significance between the two maps. From there created double check to make sure the significane was genuine.
- The last plot shows the significane with the majority of it over land in North America during these outbreaks.

<img width="617" alt="Screen Shot 2023-11-28 at 10 33 09 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/cc846160-3fbc-4f94-9939-556c54fcdf5a">
_Figure 14: Shown is the correlation map between 2 meter temperature and the 500hPa Geopotential height during the CAO list._

<img width="621" alt="Screen Shot 2023-11-28 at 10 27 45 PM" src="https://github.com/kmbarragan/Clim680_FinalProject/assets/142943607/94e421fc-a459-40a7-bf6b-331c0b5350d2">
_Figure 15: Shown is the correlation map with statistical significance between 2 meter temperature and the 500hPa Geopotential height during the CAO list. Should have used overall 2 meter temperature and 500hPa anomalies during say winter time._

- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_correlationmap.ipynb)


## Summary
From doing the analysis on the datasets, I feel I was better to understand the purpose of using 500hPa geopotential height to analyze cold air outbreaks. Although it is more likely the North American Oscillation (NAO) plays a role in the CAO's in North America, I wanted to explore it more with the PNA pattern.  
I feel like I have a better understanding on how to manipulate climate datasets better along with calculating statistical significance using python and its packages. One of the problems that came up with the datasets was when the latitude and longitudes did not match and trying to figure out how to use the interpolate function to make sure no Nan values appeared so that a correlation map was able to be created. 
