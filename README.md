# Analysis of the Change in Biodiversity Intactness Index (BII) Between 2017 and 2020 in Phoenix, Arizona

## About

This project examines how the Biodiversity Intactness Index (BII) changed between 2017 and 2020 within the Phoenix subdivision of Arizona. BII is a measure of how much of an area’s original biodiversity remains despite human pressures. By focusing on Phoenix—a rapidly expanding metropolitan region. This analysis evaluates how urban growth may be influencing ecological integrity over time.

The workflow integrates spatial vector data from the U.S. Census Bureau with raster biodiversity data from Microsoft Planetary Computer. Using Python tools such as `geopandas`, `rioxarray`, and the Planetary Computer STAC API, the project:

- Retrieves BII rasters for 2017 and 2020
- Extracts the Phoenix subdivision boundary
- Clips and analyzes BII values within the subdivision
- Calculates the percentage of land area with BII ≥ 0.75 for both years
- Visualizes Phoenix in its geographic context

This repository was completed as a project for EDS220 course led by Carmen Galaz García at UCSB's Bren School of Environmental Science for the MEDS program.

## Repository Structure

```
bii-change-phoenix/
│── .gitignore
├── data/
│   ├── tl_2024_04_cousub       
│       └── tl_2024_04_cousub.shp  # Census county subdivision shapefile (Arizona)
│
├── bii_change_phoenix.ipynb       # Jupyter notebook
│
└── README.md                      # Project documentation
```
## Data Sources
1. U.S. Census Bureau – County Subdivision Shapefiles (Arizona)
Used to obtain the official Phoenix subdivision boundary. These shapefiles provide authoritative geographic boundaries for county subdivisions across the United States.

Link: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2024.html#list-tab-790442341

2. Microsoft Planetary Computer – Biodiversity Intactness Index (BII)
Provides global BII raster datasets derived from the Integrated Biodiversity Assessment Tool (IBAT). The dataset includes annual BII estimates that can be queried and downloaded via the STAC API.

Link: https://planetarycomputer.microsoft.com/dataset/io-biodiversity

## References
U.S. Census Bureau. *TIGER/Line Shapefiles*. https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html

Microsoft Planetary Computer. *Biodiversity Intactness Index (BII) Dataset*. https://planetarycomputer.microsoft.com/dataset/io-biodiversity

Planetary Computer STAC API documentation. https://planetarycomputer.microsoft.com/docs