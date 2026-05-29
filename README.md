# EDA-

# Using BOM Data to Identify Optimal Locations for a Solar Farm in South Australia

## Project overview
This project investigates the most suitable location for a solar farm in South Australia using climate data from the Bureau of Meteorology (BOM). The analysis focuses on solar exposure, rainfall, temperature, and rain frequency to compare potential locations. 

## Objective
The main objective of this project is to evaluate the climatological stability and solar resource potential of South Australia over a 30-year period.

## Data source
Data was obtained from the Australian Bureau of Meteorology (BOM)

## Repository contents
- `data/` raw and cleaned solar exposure datasets
- `scripts/` R scripts used for data cleaning, analysis, and plotting
- `outputs/` figures, tables, and other final outputs
- `report/` final report document
- `README.md` project summary and instructions

## Software and packages used
This project was completed in RStudio using R.

Main packages used:
- tidyverse
- dplyr
- ggplot2
- tidyr
- stringr
- readr

## Methods summary
The data was imported from multiple station folders, filtered to the years 1995-2025, cleaned by removing missing values, and merged into a master dataframe. Annual variability was assessed using Standard Deviation (SD) and Interquartile Range (IQR). Ordinary least squares linear regression was then used to test whether these variability measures changed significantly over time.

## How to run the project
1. Download or clone this repository.
2. Open the R project or script files in RStudio.
3. Ensure the required packages are installed.
4. Run the data cleaning script first.
5. Run the analysis script to generate the figures and results.

## Outputs
The main outputs include:
- annual boxplots of solar exposure
- regression plots for annual standard deviation
- regression plots for annual interquartile range
- summary statistics and final report findings

## Key finding
The analysis found a significant decline in annual variability of solar exposure between 1995 and 2025, while the overall solar resource remained commercially viable.

## Author
Jingwen Liu
