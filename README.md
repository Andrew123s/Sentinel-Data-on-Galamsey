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
