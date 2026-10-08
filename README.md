# Project Title : Seattle Baltimore Weather Project

This report aims to determine if it rains more in Seattle than Baltimore, MD. There are different approaches to determine if it rains more in one city versus another. ‘More’ can refer to either the measurement of rainfall or the frequency of days when it rains. However, conceptualizing a given numerical amount of rainfall can be difficult, which makes the measurement of rainfall slightly less applicable. Assuming, in general, the larger the amount of rainfall, the longer the rain event could have occurred, gives the amount of rain more context. It is also important to take into account the number of rainy days or proportion of days with rain. This report aims to compare the rainfall in Baltimore, MD and Seattle, WA by comparing the amount of rainfall and proportion of days with rain over a 5-year period. 

---

## Project Overview


- **Objective:** The objective of this project is to compare the precipitation amount between two cities, Seattle and Baltimore.
- **Domain:** Environmental Studies/Climatology
- **Key Techniques:** Exploratory Data Analysis, t-test, z-test

---

## Project Structure

```
├── data/seattle_rain.csv                      # Raw Seattle, WA data
|   |──/balt_rain.csv                          # Raw Baltimore, MD data
|   |──/clean_seattle_baltimore_weather.csv    # Processed data for Seattle and Baltimore
├── code/Baltimore_Weather.ipynb               # Jupyter notebook contains scripts used to clean data and create visualizations
├── reports/final_report.pdf                   # Generated reports and visualizations
├── requirements.txt                           # Dependencies
└── README.md                                  # Project documentation
```

---

## Data

- **Source:**
- [NOAA National Centers for Environmental Information](https://www.ncei.noaa.gov/cdo-web/)
- **Description:**
- Overview of Raw Data:
    - Contains historical weather related observations for selected locations across the United States. Location information includes: station name, station identification code, and GPS coordinates. Observations include: time of observation, precipitation (inches to hundreths), snowfall (inches), snow depth (inches).
    - Various column abbreviations and meanings:
        - DAPR = Number of days included in the multi-day precipitation total
        - MDPR = Multi-day precipitation total
        - PRCP = Precipitation
        - SNOW = Snowfall 
        - SNWD = Snow depth 
        - WESD = Water equivalent of snow on the ground 
        - WESF = Water equivalent of snowfall
    - seattle_rain.csv
        - Contains 10 columns: Station, Name, Date, DAPR, MDPR, PRCP, SNOW, SNWD, WESD, WESF.
    - balt_rain.csv
        - Contains 8 columns: Station, Name, Date, DAPR, MDPR, PRCP, SNOW, SNWD.
- Processed Data:
    - clean_seattle_baltimore_weather.csv
        - Contains 6 columns: date, city, precipitation, day_of_year, month, any_precipitation.
          
       
- **License:** N/A

---

## Analysis

- Describe the notebooks and/or scripts used to perform the analysis. Specify the order in which the code should be run to reproduce the results.
- Baltimore_Weather.ipynb contains all scripts used to perform the analysis. To reproduce the results, 'Run All' to run the code in the order it appears. If an error appears, it can usually be resolved by running all of the code above the error before re-running the cell. 
- Data Cleaning Process:
    - Standardized column data types and format.
    - Renamed columns for clarity.
    - See Missing Data for handing of null/NA values.
    - Combined Seattle and Baltimore datasets, including only date and precipitation columns
    - Variables added:
        - day_of_year: Each date was given a numerical value (excluding years), ex. January 1st = 1, January 2nd = 2, and so on.
        - month: January = 1, February = 2, and so on. 
- Missing Data:
    - Baltimore, MD dataset had some missing dates as well as precipitation values with no dates assigned to them. As there was no way to be certain which dates these precipitation values were recorded, they were disregarded for this analysis. The missing days in the specified range, January 1st, 2018 to December 31st, 2022, were appended to the data frame with null values for precipitation. Additionally, both data sets for Seattle, WA and Baltimore, MD had missing precipitation entries. In lieu of disregarding these missing entries, the expected precipitation amount per unavailable date was calculated based on the historical precipitation values. Each day of the year, January 1st through December 31st, was assigned a numerical value. Then, each day of the year was assigned an approximate value based on that number date's average precipitation value for available years. This was replicated for the null values for each city.
 
- Analysis:
    - Various styles of graphs were created with for the following topics:
        -  Average precipitation amount by city
        -  Average proportion of days with rain by city


---

## Results

It is difficult to definitively say which city rains more. If we compare overall average rainfall, the answer is Baltimore; if we compare the proportion of days with rainfall, the answer is Seattle. In terms of average amount of rainfall, Baltimore has a higher average daily amount of rainfall and a higher maximum rainfall. Baltimore often tends to have a more consistent monthly average rainfall than Seattle. Additionally, Seattle also exhibits a much wider range of monthly proportions of rainy days. When it rains in Baltimore, it tends to result in a higher amount of rainfall than in Seattle. Seattle appears to be more prone to frequent but lower amounts of rainfall and exhibits more seasonal changes in precipitation. 

---

## Authors

- Sophia Akin [@sophsophiea](https://github.com/sophsophiea)

---

## License

N/A

---

## Acknowledgements

- This project was created as an assignment for DATA 5100-01: Foundations of Data Science at Seattle University.
- In addition to course materials, the following articles contributed to the creation of this report:
    - https://gist.github.com/DomPizzie/7a5ff55ffa9081f2de27c315f5018afc
    - https://hussein16mahdi.medium.com/mastering-pandas-part-3-data-cleaning-merging-joining-817a070147ca
    - https://github.com/matiassingers/awesome-readme
    - https://data.research.cornell.edu/data-management/sharing/readme/
  

