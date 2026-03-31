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
