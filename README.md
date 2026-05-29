# Using BOM Data to Identify Optimal Locations for a Solar Farm in SA

A data-driven analysis of South Australian climate data to identify the most suitable location for a large-scale solar farm.

**Authors:** Cayden Mecham, Janay Will, Jingwen Liu, Royce Butler | Centaur Group  
**Institution:** Adelaide University — Engineering Data Analytics

---

## Table of Contents

- [Overview](#overview)
- [Objective](#objective)
- [Data](#data)
- [Methodology](#methodology)
- [Key Results](#key-results)
- [Recommended Site](#recommended-site)
- [Limitations and Future Work](#limitations-and-future-work)
- [Conclusion](#conclusion)
- [Data Sources](#data-sources)

---

## Overview

South Australia has seen a rapid uptake in renewable energy, driven by government policy and rising demand from electric vehicle adoption. With high solar intensity and low population density, the region is well suited to solar farm development. This report evaluates candidate sites across four climate variables to recommend the best location for a new solar farm.

---

## Objective

To determine the most suitable location for a solar farm in South Australia by analyzing historical climate data — specifically solar exposure, rainfall, rainy-day frequency, and temperature — across BOM weather stations spanning a 30-year period (1995–2025).

---

## Data

Climate data was sourced from the Australian Bureau of Meteorology's Climate Data Online service. Key variables considered:

| Variable | Rationale |
|---|---|
| Solar exposure | Higher values mean more power generation potential |
| Location | Proximity to electrical infrastructure is critical |
| Rainfall | Periodic rain helps wash dust off panels; too much rain reduces sun exposure |
| Days of rain | Fewer rainy days with higher rainfall per event is the ideal scenario |
| Temperature | Panel efficiency drops 0.2–0.5% for every degree over 25°C |

Stations were plotted geographically — the final selected station is marked with a green star on a BOM station map.

---

## Methodology

A multi-stage analytical pipeline was used:

### Statistical Tests

| Technique | Purpose |
|---|---|
| **Linear Regression** | Model the temporal trend of annual standard deviation and interquartile range of daily solar exposure (1995–2025) |
| **Kruskal-Wallis Test** | Non-parametric comparison of solar exposure distributions across stations (data was non-normal per QQ-plot analysis) |
| **Scatterplot Analysis** | Bivariate comparison of climate variables (rainfall vs. solar exposure, temperature vs. rainfall, etc.) |
| **Boxplot Analysis** | Single quantitative variable comparison across stations |

### Hypothesis Test

For solar exposure distribution across stations:

- **H₀:** All stations have the same solar data distribution
- **Hₐ:** At least one station has a different distribution

The Kruskal-Wallis test returned a p-value well below 1%, strongly rejecting the null hypothesis. Follow-up pairwise comparisons showed 13 out of 78 station pairs (16.7%) had statistically similar distributions, which was deemed acceptable.

---

## Key Results

### Trend Analysis

Linear regression on 30-year data revealed:

- **Annual standard deviation** of daily solar exposure showed a significant negative trend — variability declined consistently over the study period.
- **Annual interquartile range** also decreased significantly, though with a weaker relationship.
- Overall, South Australia's solar climate became more stable between 1995 and 2025.

### Variable Analysis

- **Rainfall and rainy days:** Naracoorte and Padthaway had much higher rainfall and were excluded. Arkaroola was ruled out as a wilderness protection area. Ernabella and Tarcoola were less favourable due to more rainy days. Mulka had too few rainy days.
- **Solar exposure:** Lower exposure was observed for south-eastern stations (Naracoorte, Padthaway). All other stations clustered around 20 MJ/m².
- **Temperature:** All median values fell within the 20–30°C range. Stations with temperatures outside the optimum window were excluded during bivariate analysis.

---

## Recommended Site

### Top 5 Stations by Solar Exposure

| Station | Solar Exposure (MJ/m²) | Rainfall (mm) | Days of Rain | Max Temp (°C) |
|---|---|---|---|---|
| Ernabella | 20.9 | 220.4 | 48 | 27.6 |
| **Oodnadatta** | **20.9** | **155.3** | **33** | **29.0** |
| Marla | 20.7 | 161.9 | 31.5 | 28.6 |
| Mulka | 20.7 | 137.25 | 18.5 | n/a |
| Moomba | 20.7 | 155.6 | 27 | 29.6 |

**Winner: Oodnadatta** — selected over Moomba based on its slightly higher maximum yearly rainfall amount, providing a better balance of solar exposure and precipitation for panel maintenance.

---

## Limitations and Future Work

- Cloud coverage data was not included in this analysis and would provide a more complete picture
- The feasibility threshold ("red square") in the bivariate analysis was chosen arbitrarily and could be refined
- Infrastructure access, investment cost, and terrain were acknowledged as important but were outside the report's scope
- Only South Australian stations were studied — other locations across Australia could be investigated
- A full project feasibility study would need to assess grid connection and capital investment

---

## Conclusion

Using BOM climate data and a multi-method statistical approach, the report identifies Oodnadatta in central-northern South Australia as the most suitable site for a solar farm among the stations analyzed. The methodology demonstrates how public climate data can be applied to renewable energy site selection and is broadly transferable to other energy types and regions.

---

## Data Sources

- Australian Bureau of Meteorology — [Climate Data Online](https://reg.bom.gov.au/climate/data/index.shtml)
- Department for Environment and Water, SA Government — [Arkaroola wilderness area](https://www.environment.sa.gov.au/our-places/arkaroola)
- Energy Matters — [Optimal temperature for solar panels](https://www.energymatters.com.au/renewable-news/whats-the-optimal-temperature-for-solar-panels/)
- Government of South Australia — [Leading the green economy](https://www.energymining.sa.gov.au/industry/hydrogen-and-renewable-energy/leading-the-green-economy)
- IEA — [Global EV Outlook 2025](https://www.iea.org/reports/global-ev-outlook-2025)
- ANU Institute for Climate, Energy & Disaster Solutions — [Solar land use study](https://iceds.anu.edu.au/news-events/news/no-threat-farm-land-just-1200-square-kilometres-can-fulfil-australia)
