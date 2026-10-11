# Aviation Accident Analysis

# Aviation Accident Safety Analysis

## Overview

I reviewed the aviation accident data and compared the number of fatalities/serious injuries to the number of aircraft destroyed by each weather condition and number of engines. The project will include two Jupyter notebooks: One to clean the data and one to analyze the data.

## Project files

- `Aviation_Accidents_Cleaning.ipynb` — cleans and filters the accident data, and calculates derived measures.

- `Aviation_Accidents_Data_Analysis.ipynb` — summarizes and visualizes the accident outcome.

data/AviationData.csv: This is the source dataset that is provided for the course, and is needed to run the cleaning notebook.

data/AviationData_cleaned.csv: Cleaned dataset, produced by the cleaning notebook and applied to the analysis notebook.

Data preparation and measures.

I limited the data to accidents on or after 1 January 1983 and those which involved a non-amateur-built airplanes. If all four injury counts were available, I calculated the number of occupants by adding together the number of occupants that were fatally injured, seriously injured, and injured, and the number of uninjured occupants. To determine the fatal/serious injury fraction, the numbers of fatal and serious injuries were divided by the estimated number of occupants. If the damage reported is “Destroyed” I recorded that damage as destroyed.

Accidents with 1-20 occupants reported are considered “Small”, and accidents with more than 20 occupants are considered “Large” in the notebooks. This is based on occupants reported for each accident, not the aircraft’s seating capacity, so it may not accurately represent aircraft size.

## Comparisons

### Weather conditions

I compared injury fractions and destruction rates of accidents reported under instrument meteorological conditions (IMC) and visual meteorological conditions (VMC):

- The mean injury fraction was **65.5% for IMC** (878 records) and **27.6% for VMC** (14,014 records).

- The destruction rate was **37.84% for IMC** (983 records) and **7.77% for VMC** (16,506 records).

IMC observed more injuries and more destruction in these accident records than did VMC.

### Number of engines

I made a comparison of 1-engine and 2-engine aircraft:

- The mean injury fraction was **30.3% for one-engine aircraft** (13,178 records) and **32.9% for two-engine aircraft** (2,096 records).

- The destruction rate was **8.20% for one-engine aircraft** (15,529 records) and **19.32% for two-engine aircraft** (2,179 records).

In these accident stats, the injury fraction and destruction rate observed for two-engine aircraft was greater than that observed for one-engine aircraft.

The sample sizes vary as some records do not contain injury and aircraft-damage data, therefore each comparison is based upon records that contain the data of interest.

## How to run

Step 1: Copy the file `AviationData.csv` to the folder `data/`.

Install the following packages: pandas, numpy, matplotlib and seaborn.

To produce `data/AviationData_cleaned.csv`, run all cells in the notebook ‘Aviation_Accidents_Cleaning.ipynb’ from top to bottom.

Add the line `MAKE_MIN_N = 50` with near the imports at the top of the file Aviation_Accidents_Data_Analysis.ipynb and execute all the cells from top to bottom.

## Limitations

These comparisons refer to accidents that have been reported and do not represent estimates of the risk of an accident on a particular flight. Some data is missing, resulting in varying sample sizes for each outcome. Results can also differ depending on the aircraft type, size, usage and severity of the incident. These findings are only correlative and not indicative of cause. Aircraft may be misclassified by the occupant-based size grouping, and use of recommendations based on that grouping should be used with caution.