# Analysis of the Change in Biodiversity Intactness Index (BII) Between 2017 and 2020 in Phoenix, Arizona

## About this Project

This project examines how the Biodiversity Intactness Index (BII) changed between 2017 and 2020 within the Phoenix subdivision of Arizona. BII is a measure of how much of an area’s original biodiversity remains despite human pressures. This analysis focuses on Phoenix, a rapidly expanding metropolitan region, to evaluate how urban growth may be influencing ecological integrity over time. The workflow integrates spatial vector data from the U.S. Census Bureau with raster biodiversity data from Microsoft Planetary Computer. Using Python tools such as `geopandas`, `rioxarray`, and the Planetary Computer STAC API, the project:

- Retrieves BII rasters for 2017 and 2020
- Extracts the Phoenix subdivision boundary
- Clips and analyzes BII values within the subdivision
- Calculates the percentage of land area with BII ≥ 0.75 for both years
- Visualizes Phoenix in its geographic context

This repository was completed as a project for EDS220 course led by Carmen Galaz García at UCSB's Bren School of Environmental Science in the MEDS program.

## Repository Structure

```
bii-change-phoenix/
│── .gitignore
├── data/                          # Data directory ignored in git
│   └── tl_2024_04_cousub/          # User-downloaded census county subdivision shapefile (Arizona)
│
├── bii_change_phoenix.ipynb       # Jupyter notebook
│
└── README.md                      # Project documentation
```
## About the Data

This analysis uses two datasets:

### Biodiversity Intactness Index (BII)
BII raster data are accessed from the **`io-biodiversity`** collection in the **Microsoft Planetary Computer STAC catalog**. Annual BII rasters for **2017** and **2020** are retrieved and spatially subset to the Phoenix subdivision. 

The STAC query uses the following bounding box: 

[-112.826843, 32.974108, -111.184387, 33.863574]

The BII rasters are retrieved from the Microsoft Planetary Computer and are not stored locally.

### Phoenix Subdivision Shapefile

The 2024 Phoenix subdivision polygon is obtained from the **U.S. Census Bureau TIGER/Line County Subdivision (COUSUB) shapefiles for Arizona**. This polygon is used to clip the BII rasters and summarize biodiversity intactness within the Phoenix subdivision.

## Data Access & Reproducibility

All data required for this analysis are publicly available, but large spatial datasets are not included in the repository and must be obtained separately.

### Vector Data (manual download)
**U.S. Census Bureau – TIGER/Line County Subdivision Shapefiles (Arizona)**

- This dataset is not tracked in the repository and is intentionally listed in `.gitignore` due to its file size
- Users must download the Arizona county subdivision shapefile manually
- Download from: https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html
- Place the extracted files in the `data/tl_2024_04_cousub/` directory

This shapefile is used to extract the Phoenix county subdivision boundary.


### Raster Data Access 
**Biodiversity Intactness Index (BII)**

- This dataset is accessed from the **Microsoft Planetary Computer**
- Retrieved using the Planetary Computer STAC API within the Jupyter notebook
- Years queried: **2017** and **2020**
- Raster data are not stored locally

Access to the Planetary Computer does **not** require an API key. Authentication is handled using the `planetary_computer.sign()` function.

An active internet connection and the required Python packages are needed to reproduce the analysis.

## References

Galaz García, C. (2025). *Final project*. EDS 220: Working with Environmental Datasets. https://meds-eds-220.github.io/MEDS-eds-220-course/assignments/final-project.html

Microsoft Planetary Computer. *io-biodiversity, 2017-2020 (v1) [Dataset]*. Microsoft Planetary Computer STAC Catalog. https://planetarycomputer.microsoft.com/dataset/io-biodiversity

Microsoft Planetary Computer. Planetary Computer STAC API documentation. https://planetarycomputer.microsoft.com/docs

U.S. Census Bureau (2025). *TIGER/Line Shapefiles [Dataset]*. https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html
