# 🚦 Urban Traffic Pattern Mining Using Unsupervised Learning

![Python](https://img.shields.io/badge/Python-3.10-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen.svg)
![Dataset](https://img.shields.io/badge/Dataset-METR--LA-orange.svg)

> **Discovering hidden traffic congestion patterns in Los Angeles highway network
> using HDBSCAN clustering and PCA — without any labelled data.**

---

## 📋 Table of Contents

- [About The Project](#-about-the-project)
- [Problem Statement](#-problem-statement)
- [Dataset](#-dataset)
- [Notebooks Overview](#-notebooks-overview)
- [Visualizations](#-visualizations)

---

## 🎯 About The Project

Traffic data from urban highways exhibits **recurring spatio-temporal patterns**.
Without labelled congestion events, discovering these patterns through
**unsupervised learning** can significantly aid urban planning, incident
detection, and traffic management.

This project analyzes **4 months of speed data** from **207 highway sensors**
across Los Angeles using **density-based clustering (HDBSCAN)** and
**dimensionality reduction (PCA)** to automatically discover:

- ✅ Distinct traffic states (free flow, congestion, rush hour, moderate traffic)
- ✅ Recurring daily and weekly traffic patterns
- ✅ Anomalous traffic events (potential accidents, unusual conditions)
- ✅ Actionable insights for traffic management

**No labels or supervised training required** — the algorithm discovers
everything on its own.

---

## 🔍 Problem Statement

Traffic congestion costs Los Angeles approximately $19.2 billion annually.
Traffic authorities collect millions of speed readings from highway sensors,
but this data is UNLABELLED — no one has manually tagged timestamps as
"congested" or "free flow."

CHALLENGE: How can we automatically discover meaningful traffic patterns
from raw speed data without any human-provided labels?

SOLUTION: Apply unsupervised machine learning (HDBSCAN clustering) on
engineered temporal and statistical features to group similar traffic
states and detect anomalies


---

## 📊 Dataset

| Property | Details |
|----------|---------|
| **Name** | METR-LA (Metropolitan Traffic, Los Angeles) |
| **Source** | [DCRNN Repository](https://github.com/liyaguang/DCRNN) |
| **Type** | Traffic speed readings (mph) |
| **Sensors** | 207 loop detectors on LA county highways |
| **Duration** | March 1, 2012 — June 30, 2012 (4 months) |
| **Granularity** | Every 5 minutes |
| **Total Timestamps** | ~34,272 rows |
| **Total Data Points** | ~7.1 million speed readings |
| **File Format** | HDF5 (.h5) |
| **File Size** | ~53 MB |

### Sample Data Structure
Timestamp Sensor_1 Sensor_2 Sensor_3 ... Sensor_207
2012-03-01 00:00:00 65.2 61.8 67.1 ... 59.4
2012-03-01 00:05:00 64.8 62.1 66.9 ... 60.1
2012-03-01 00:10:00 65.0 61.5 67.3 ... 58.7

### Installation

**Step 1: Clone the repository**

`'' bash
git clone https://github.com/YOUR_USERNAME/urban-traffic-pattern-mining.git
cd urban-traffic-pattern-mining
'''

**Step 2: Create a virtual environment

**Step 3: Install all dependencies

**Step 4:Dataset Download


### WE Run notebooks in sequential order!

Step 1 ──► Step 2 ──► Step 3 ──► Step 4 ──► Step 5
  │           │          │          │          │
  ▼           ▼          ▼          ▼          ▼
Clean      Engineer   Cluster   Visualize  Interpret
Data       Features   Patterns  Results    & Ethics

## 📓 Notebooks Overview :

### Notebook 1: Data Understanding & Preprocessing
- Loads METR-LA dataset (207 sensors, 34K timestamps)
- Handles missing values using forward-fill and interpolation
- Removes zero-speed anomalies (sensor errors)
- Generates initial EDA plots (distributions, heatmaps)
- Saves cleaned dataset for next step

### Notebook 2: Feature Engineering
- Creates 31 features from raw speed data
- Network statistics: mean, std, min, max, range, CV
- Temporal: cyclical hour/day encoding, peak flags, weekend flag
- Rolling windows: 30min, 1hr, 2hr moving averages and deltas
- Congestion indicators: % sensors congested, severe count
- Standardizes all features using StandardScaler

### Notebook 3: Unsupervised Modelling
- Applies PCA to reduce 31 features → ~10 components (95% variance)
- Tunes DBSCAN using k-distance plot and grid search
- Runs HDBSCAN as primary clustering model
- Compares both models using Silhouette and Davies-Bouldin scores
- Profiles and names each discovered cluster
- Identifies anomalies (noise points = unusual traffic events)

### Notebook 4: Visualization & Analysis
- 20+ plots covering temporal patterns, clusters, and anomalies
- Speed timeline colored by cluster
- 24-hour speed profiles and cluster heatmaps
- Anomaly highlighting and transition probability matrix
- Summary dashboard combining all key visuals

### Notebook 5: Interpretation & Ethical Relevance
- Interprets each cluster (free flow, rush hour, moderate, anomaly)
- Provides 7 traffic management recommendations
- Discusses societal benefits (emissions, safety, economy)
- Addresses ethical concerns (privacy, bias, transparency)
- Lists limitations and future work directions


## 📊 Visualizations

All plots saved to `outputs/figures/`

| # | Plot | What It Shows |
|---|------|---------------|
| 1 | `speed_distribution.png` | Histogram of all speed readings across sensors |
| 2 | `network_avg_speed_timeline.png` | 4-month speed trend across entire network |
| 3 | `speed_heatmap_hour_day.png` | Average speed by hour and day of week |
| 4 | `feature_correlation_matrix.png` | Relationships between engineered features |
| 5 | `pca_variance_analysis.png` | Scree plot showing variance per component |
| 6 | `k_distance_plot.png` | Elbow plot for DBSCAN epsilon selection |
| 7 | `hdbscan_clusters_pca2d.png` | Clusters visualized in 2D PCA space |
| 8 | `dbscan_vs_hdbscan_comparison.png` | Side-by-side model comparison |
| 9 | `speed_timeline_by_cluster.png` | Speed over time colored by cluster |
| 10 | `hourly_speed_profile_by_cluster.png` | 24-hour speed curve per cluster |
| 11 | `cluster_heatmaps_hour_day.png` | When each cluster is most active |
| 12 | `anomaly_timeline.png` | Unusual traffic events highlighted in red |
| 13 | `boxplots_by_cluster.png` | Speed and variability distributions |
| 14 | `weekly_recurring_pattern.png` | Weekday vs weekend pattern comparison |
| 15 | `one_week_detail.png` | Zoomed view of one representative week |
| 16 | `cluster_transition_matrix.png` | Probability of switching between states |
| 17 | `analysis_dashboard.png` | Combined summary of all key insights |

