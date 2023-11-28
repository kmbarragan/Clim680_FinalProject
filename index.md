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
  - Northern Hemisphere Latitude 0-90 Longitude (-180)- (180)
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

---

## Results and Codes
---
### Function
Created a function to be able to process the monthly climatology and 2 meter temperature anomalies

### Conda Environment 
[Environment](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/environment.yml)

### Analyses and Notebooks
Monthly Mean 500hPa
- Calculated the monthly mean for the 2 meter temperature. Started by resampling the daily data to create a new dataset with just months then with the groupby function created a monthly mean and plotted in a multipanel plot display.
- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_500_MonthlyMean.ipynb)

Monthly Mean to T2M 
- Calculated the monthly mean for the 2 meter temperature. Started by resampling the daily data to create a new dataset with just months then with the groupby function created a monthly mean and plotted in a multipanel plot display.
- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_t2m_MonthlyMean.ipynb)

Climatology by day along with Anomalies for 500hPa
- Calculated the the climatology using the groupby mean function using day of the year. From there created anomalies by subtracting the day of year groupby from the climatology. Then using a list of predefined Cold Air Outbreaks (CAO's) used then to selected those anomalies and plotted them in a multipanel plot based on the month during the winter season. At the end concatenated the list into one dataset and plotted all the CAO's all together.
- Some appear more intesne than others and when comparing with the ranking provided by Smith 2019 some seem not as extreme as ranked using the 500hPA
- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_Anomalies.ipynb)

Climatology by day along with Anomalies for T2M
- Calculated the the climatology using the groupby mean function using day of the year. From there created anomalies by subtracting the day of year groupby from the climatology. Then using a list of predefined Cold Air Outbreaks (CAO's) used then to selected those anomalies and plotted during the winter season with all the CAO's in one plot. More or less to compare with the 500hPa
- With the temperature the intensity is really displayed better. Something happens with Dec 13, 1985. Doubled check the data and it just seems the values are higher for some reason. From the used the ERA5 dataset to do a similar process as initially and found out what it should about look like with ther ERA Interim dataset. All the other plots seem to match between the ERA Interim and ERA5 except Jan 6 1982. Again went through the climatology and anomalies and it seems when creating the anomalies for that day NaN's appear everywhere. 
- [Notebook to ERA Interim](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_t2m_AnomFun.ipynb)
- [Notebook to ERA 5](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_ERA5_Climatology.ipynb)
  
Calculate Composites between 500hPa and PNA
- Created a composite the 500hPa geopotential height and PNA index. After opening the PNA index, divided it into the positive phase and negative phase. From there with the 500hPa created anomalies similar to before and selected the 20 CAO's from Smith 2019. From there created the composite between the positive and negative phase and 500hPa. It appears more CAO's happen during the positve phase of the PNA index even appearing similar to the positive phase in the 500hPa
- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_PNA_Composite.ipynb)

Calculate the Mean Difference between Composites with Significance
- Doing something similar to creating a composites with 500hPa and PNA but this time indicated a "enhanced" PNA index where anything above 1 would now be positive and below -1 would be negative. All those in between 1 and -1 would be considered neutral. Trying to see if maybe more intensely ranked CAO's are linked to this "enhanced" PNA index. They are not. The ranking is also from Smith 2019.
- Did something similar previously but now able to find the mean diffference between the positive and neutral phase and calculate the statistical significance.
- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/EnhancedPNA.ipynb)

Correlation Map between T2M and 500hPa anomalies during CAO 
- Using many of the techinques from earlier now to create a correltion map between the 2 meter temperature and 500hPa maps during the pre-defined list of CAO's.
- After creating the anomalies for both datasets, created a correlation map and plotted it. From there used the scipy package to be able see the statistical significance between the two maps. From there created double check to make sure the significane was genuine.
- The last plot shows the significane with the majority of it over land in North America during these outbreaks. 
- [Notebook](https://github.com/kmbarragan/Clim680_FinalProject/blob/main/CAO_correlationmap.ipynb)


## Summary
From doing the analysis on the datasets, ......
I feel like I have a better understanding on how to manipulate climate datasets better. 
