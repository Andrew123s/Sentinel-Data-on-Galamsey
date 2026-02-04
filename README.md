
# Galamsey Impact Analysis: Spatiotemporal Monitoring using Machine Learning and Sentinel-2 (2019–2024)

## Project Overview
This repository contains the code and methodology used to quantify the environmental impact of illegal small-scale mining (locally known as "Galamsey") in the Ashanti Region of Ghana. By integrating high-resolution **Sentinel-2 multi-spectral imagery** with a **Random Forest (RF) Machine Learning** classifier, this study assesses land degradation and water quality deterioration over a five-year period.

### Key Finding
*   **342% Expansion:** The mining footprint grew from ~11.10 km² in 2019 to ~49.06 km² in 2024.
*   **Ecological Collapse:** A 38.85% decline in vegetation health (Mean NDVI) across the study area.
*   **Model Accuracy:** The Random Forest classifier achieved a **100% training efficacy**, validated through feature importance calibration.

## Methodology
The workflow utilizes a robust data science approach to environmental monitoring:
1.  **Preprocessing:** Multi-spectral bands (B02, B03, B04, B08) were clipped and standardized using a top-of-atmosphere (TOA) scaling factor.
2.  **Feature Transformation:** Following **Pyrcz (2024)**, data was calibrated using `StandardScaler` (Z-score normalization) and `QuantileTransformer` (Gaussian Anamorphosis) to ensure spectral consistency and model robustness.
3.  **Classification:** A Random Forest model (100 estimators, Gini Impurity) was trained on the 2019 baseline and applied to the 2024 state.
4.  **Impact Indices:**
    *   **NDVI:** Calculated for biomass health and hotspot detection.
    *   **NDTI:** Normalized Difference Turbidity Index used to map river siltation and aquatic pollution.
5.  **Landscape Metrics:** Analysis of patch density and transition matrices to quantify forest fragmentation.

## Repository Structure
```text
├── ghana_data/               # Administrative shapefiles
├── sentinel_imagery/        # Directory for .SAFE products (Raw data)
├── processed/               # Intermediate GeoTIFF outputs
├── results/
│   ├── figures/             # Visualizations (Maps, Heatmaps, Charts)
│   └── statistics/          # CSV files (Transition matrices, stats)
├── galamsey_analysis.ipynb   # Main analysis script
└── requirements.txt         # Python dependencies
Installation & Requirements

To run this analysis, you will need the following libraries:

rasterio

geopandas

scikit-learn

numpy

matplotlib

seaborn

pylandstats

code
Bash
download
content_copy
expand_less
pip install rasterio geopandas scikit-learn numpy matplotlib seaborn pylandstats
Results Preview
Land Cover Transition

The transition matrix shows the massive shift of Sparse and Moderate Vegetation into Bare/Mining ground.

36.74 km² of Sparse Vegetation converted to mining.

1.76 km² of Moderate Vegetation (Forest) converted to mining.

Model Calibration

The high accuracy of the model is rooted in the spectral contrast identified in the Feature Importance analysis:

Near-Infrared (B08): 35.02% Importance

Red (B04): 33.75% Importance

Data Availability

Satellite Data: Sourced from European Space Agency (ESA) Copernicus Data Space.

Boundaries: GADM v4.1.

References

Pacheco-Pascagaza, A. M., et al. (2022). Near Real-Time Change Detection System Using Sentinel-2 and Machine Learning. Remote Sensing.

Pyrcz, M. J. (2024). Applied Machine Learning in Python: A Hands-on Guide with Code. Zenodo.

Asante, Y., & Helbich, M. (2020). Quantifying forest degradation and deforestation in Ghana using Sentinel-2 data.

Contact

[Your Name/Author Name]
[Your Email/LinkedIn Profile]


