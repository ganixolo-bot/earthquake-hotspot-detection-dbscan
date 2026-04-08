# Earthquake Epicentre Hotspot Detection using DBSCAN

![Python](https://img.shields.io/badge/Python-3.x-blue) ![Colab](https://img.shields.io/badge/Platform-Google%20Colab-orange) ![License](https://img.shields.io/badge/License-MIT-green)

## Overview

This project detects global earthquake epicentre hotspots using **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise). It clusters latitude and longitude coordinates from a historical earthquake dataset to reveal tectonic plate boundaries and identify isolated intraplate seismic events.

The project also compares DBSCAN results with **K-Means (K=10)** to highlight why density-based methods are better suited for geospatial data.

---

## Features

- Exploratory Data Analysis (EDA) of the USGS earthquake dataset
- K-Distance Graph to determine the optimal epsilon for DBSCAN
- DBSCAN clustering — auto-detects cluster count and labels noise
- K-Means clustering for comparison
- World map visualizations with magnitude-scaled point sizes
- Detailed analysis of why K-Means fails on tectonic data

---

## Dataset

**Source:** [USGS Earthquake Database — Kaggle](https://www.kaggle.com/datasets/usgs/earthquake-database)

**File:** `database.csv`

**Columns used:** `Latitude`, `Longitude`, `Magnitude`, `Depth`

> Download the dataset from Kaggle and upload it to Google Colab before running the notebook.

---

## Project Structure

```
earthquake-hotspot-detection-dbscan/
├── earthquake_hotspot_dbscan.ipynb   # Main Colab notebook
├── README.md                          # Project documentation
└── outputs/
    ├── fig5_1_comparison.png          # DBSCAN vs K-Means side-by-side map
    └── fig5_2_noise_vs_clusters.png   # Noise points vs cluster members map
```

---

## How to Run

1. Open [Google Colab](https://colab.research.google.com)
2. Upload `earthquake_hotspot_dbscan.ipynb`
3. Download `database.csv` from [Kaggle](https://www.kaggle.com/datasets/usgs/earthquake-database)
4. Run **Step 0** in the notebook to upload the CSV
5. Run all cells in order (Steps 1 through 7)

---

## Steps in the Notebook

| Step | Description |
|------|-------------|
| 0 | Upload dataset to Colab |
| 1 | Install required libraries (`basemap`) |
| 2 | Load dataset and perform EDA |
| 3 | K-Distance Graph to find optimal epsilon |
| 4 | Apply DBSCAN clustering |
| 5 | Visualize clusters on a world map |
| 6 | Apply K-Means (K=10) for comparison |
| 7 | Final summary visualization and statistics |

---

## Results

| Metric | Value |
|--------|-------|
| Total earthquakes analysed | ~23,000+ |
| Clusters detected (DBSCAN) | ~15 (auto-detected) |
| Isolated noise points | ~X% of total |
| Tectonic alignment | Excellent (Ring of Fire, Mid-Atlantic Ridge, Himalayan Belt) |

---

## DBSCAN vs K-Means

| Property | DBSCAN | K-Means |
|----------|--------|---------|
| No. of clusters | Auto-detected | Fixed (K=10) |
| Cluster shape | Arbitrary / Irregular | Spherical / Convex |
| Noise handling | Yes (labels as -1) | No |
| Tectonic alignment | Excellent | Poor |
| Geospatial suitability | High | Low |

---

## Technologies Used

- Python 3.x
- Google Colab
- pandas, numpy
- matplotlib, seaborn
- scikit-learn (DBSCAN, KMeans, NearestNeighbors)
- basemap (world map plotting)

---

## Academic Context

**Institution:** Marwadi University
**Degree:** B.Tech — Computer Science & Engineering
**Subject:** Machine Learning / Data Mining

---

## License

This project is licensed under the MIT License.
