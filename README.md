# 📈 Google Trends Time Series Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange?style=flat)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter)

> Exploring whether **Google Search volume** can predict or correlate with real-world financial and economic data - including Tesla stock prices, Bitcoin prices, and the U.S. unemployment rate.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Project Structure](#-project-structure)
- [Datasets](#-datasets)
- [Key Analyses](#-key-analyses)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Results](#-results)
- [Author](#-author)

---

## 🔍 Overview

Google Trends provides an estimate of search volume for any keyword over time. This project investigates whether those search trends correlate with real-world data by answering:

- Does searching for **"Tesla"** precede or follow changes in TSLA stock price?
- Does interest in **"Bitcoin"** news track BTC price movements?
- Does searching for **"Unemployment Benefits"** reflect the actual U.S. unemployment rate?

---

## 📁 Project Structure

```
Google-Trends-Time-Series-Analysis/
|
+-- Google_Trends_and_Data_Visualisation.ipynb   # Main analysis notebook
|
+-- Bitcoin Search Trend.csv                     # Monthly BTC Google search volume
+-- Daily Bitcoin Price.csv                      # Daily BTC closing prices
+-- TESLA Search Trend vs Price.csv              # Monthly TSLA search + stock price
+-- UE Benefits Search vs UE Rate 2004-19.csv    # Search vs unemployment rate (2004-2019)
+-- UE Benefits Search vs UE Rate 2004-20.csv    # Search vs unemployment rate (2004-2020)
|
+-- README.md
```

---

## 📊 Datasets

| File | Source | Key Columns | Frequency |
|------|--------|-------------|-----------|
| `Bitcoin Search Trend.csv` | Google Trends | `MONTH`, `BTC_NEWS_SEARCH` | Monthly |
| `Daily Bitcoin Price.csv` | Crypto Market Data | `DATE`, `CLOSE` | Daily |
| `TESLA Search Trend vs Price.csv` | Google Trends + Yahoo Finance | `MONTH`, `TSLA_WEB_SEARCH`, `TSLA_USD_CLOSE` | Monthly |
| `UE Benefits Search vs UE Rate 2004-19.csv` | Google Trends + FRED | `MONTH`, `UE_BENEFITS_WEB_SEARCH`, `UNRATE` | Monthly |
| `UE Benefits Search vs UE Rate 2004-20.csv` | Google Trends + FRED | `MONTH`, `UE_BENEFITS_WEB_SEARCH`, `UNRATE` | Monthly |

---

## 🔬 Key Analyses

### 1 - Tesla Stock Price vs. Search Volume
- Dual-axis line chart comparing TSLA closing price against web search interest
- Custom formatting with axis labels, colors, tick locators, and figure DPI

### 2 - Bitcoin Price vs. Search Volume
- Daily BTC price resampled to monthly using `.resample('ME')`
- Dual-axis chart with dashed lines and markers for clearer data points

### 3 - Unemployment Benefits Search vs. U.S. Unemployment Rate
- Google search interest in "Unemployment Benefits" plotted against the FRED U/E rate
- 3-month and 6-month rolling averages applied to smooth noise and reveal trends

### Data Cleaning
- Detected and removed `NaN` values from the Bitcoin price dataset
- Converted all `MONTH` and `DATE` columns from strings to `datetime` objects
- Resampled daily BTC price data down to monthly frequency

---

## 🛠 Tech Stack

| Tool | Purpose |
|------|---------|
| **Python 3** | Core language |
| **Pandas** | Data loading, cleaning, resampling, rolling averages |
| **Matplotlib** | Dual-axis time series charts with date formatting |
| **Jupyter Notebook** | Interactive development environment |

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install pandas matplotlib notebook
```

### Clone the Repository

```bash
git clone https://github.com/Vaishvi-chaudhari/Google-Trends-Time-Series-Analysis.git
cd Google-Trends-Time-Series-Analysis
```

### Run the Notebook

```bash
jupyter notebook Google_Trends_and_Data_Visualisation.ipynb
```

> **Note:** Make sure all CSV files are in the same folder as the notebook before running any cells.

---

## 📈 Results

| Analysis | Finding |
|----------|---------|
| **Tesla** | Strong positive correlation between search interest and stock price - especially during peak media attention periods |
| **Bitcoin** | Search volume spikes closely mirror BTC price surges - suggesting search interest as a potential leading or lagging indicator |
| **Unemployment** | Search volume for "Unemployment Benefits" tracks the official U/E rate closely - with a dramatic spike during the 2020 COVID-19 pandemic in the extended dataset |

---

## 👩‍💻 Author

**Vaishvi Chaudhari**

- GitHub - [@Vaishvi-chaudhari](https://github.com/Vaishvi-chaudhari)

---

*Data Sources - [Google Trends](https://trends.google.com) - [Yahoo Finance](https://finance.yahoo.com) - [FRED - Federal Reserve Bank of St. Louis](https://fred.stlouisfed.org)*
