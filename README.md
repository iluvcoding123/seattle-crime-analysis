# Seattle Crime Spatiotemporal Analysis

Exploratory data analysis and clustering of Seattle Police Department crime incident data.  

## Dataset
**Source**: Seattle Police Department Open Data Portal  
**Dataset**: [SPD Crime Data (2008–Present)](https://data.seattle.gov/Public-Safety/SPD-Crime-Data-2008-Present/tazs-3rd5/about_data)  
**Download Date**: February 10, 2026  


The dataset contains over 1.5 million reported incidents, including geographic coordinates, temporal information, and crime classifications.

### Data Storage

The raw dataset is not included in this repository because it exceeds GitHub’s file size limits. The `data/` directory is excluded via `.gitignore`.

To run the project locally:
1. Download the dataset from the source link above.
2. Place the CSV file inside a directory named `data/` at the project root.
3. Ensure the filename matches the path referenced in the notebook.

## Methodology Overview

1. Data cleaning and preprocessing
2. Spatial and temporal exploratory analysis
3. Feature engineering and encoding
4. Unsupervised clustering analysis (in progress)