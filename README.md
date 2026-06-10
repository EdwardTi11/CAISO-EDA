# California Renewable Energy EDA

An exploratory data analysis of California's solar and wind energy production using over **315,000 high-frequency environmental observations**. This project investigates how weather conditions influence renewable energy generation and explores seasonal patterns that affect grid reliability and energy consistency.

**Explore the Project**
- 📓 Interactive Notebook: [`eda.ipynb`](eda.ipynb)
- 📊 Dataset: [`Database.csv`](Database.csv)

---

# 📋 Project Objectives

This analysis focuses on understanding the relationship between environmental conditions and renewable energy production.

### Key Questions

- **Wind Velocity:** At what wind speeds does energy generation begin to plateau?
- **Atmospheric Conditions:** How does humidity influence solar and wind production?
- **Thermal Effects:** How do temperature fluctuations affect photovoltaic efficiency?
- **Irradiance Profiles:** How do DHI, DNI, and GHI vary throughout the year?
- **Grid Complementarity:** How well does renewable generation align with baseline electricity demand?

---

# 📊 Dataset Overview

The dataset contains approximately **315,000 observations** collected at **5-minute intervals**.

### Example Features

| Variable | Description |
|-----------|-------------|
| Temperature | Ambient air temperature |
| Humidity | Relative humidity |
| Wind Speed | Wind velocity measurements |
| GHI | Global Horizontal Irradiance |
| DNI | Direct Normal Irradiance |
| DHI | Diffuse Horizontal Irradiance |
| Solar Production | Solar energy output |
| Wind Production | Wind energy output |
| Timestamp | Observation date and time |

The combination of environmental and production metrics enables both correlation analysis and long-term trend discovery.

---

# 🔬 Methodology

The analysis pipeline consists of several stages:

### 1. Data Cleaning

- Timestamp normalization
- Duplicate removal
- Missing value handling
- Type conversion and validation

### 2. Feature Aggregation

Because raw observations occur every five minutes, data is aggregated to reveal broader trends:

- Daily resampling
- Mean value aggregation
- 30-day centered rolling averages

### 3. Exploratory Analysis

The notebook investigates:

- Seasonal production cycles
- Correlation structures
- Weather-production relationships
- Long-term trends
- Renewable generation variability

### 4. Visualization

Custom plotting functions are used to compare:

- Environmental variables
- Solar production
- Wind production
- Demand estimates

using synchronized timelines and shared axes.

---

# 🛠️ Technical Implementation

## Data Processing Pipeline

The project utilizes a modular Pandas workflow.

### `process_data()`

Responsible for:

- Timestamp conversion
- Duplicate removal
- Missing value handling
- Dataset preparation

### `average()`

Generates smoothed macro-level trends using:

```python
.resample('D').mean()
.rolling(window=30, center=True)
```

### `graph_data()`

Creates synchronized visualizations using:

```python
matplotlib
sharex=True
```

allowing direct comparison between environmental variables and generation outputs.

### `get_correlation()`

Calculates correlation matrices and supports heatmap generation for relationship analysis.

---

# 📈 Key Findings

## Seasonal Production Imbalance

Renewable generation peaks during summer months and declines significantly during winter.

This creates a noticeable seasonal mismatch between energy availability and baseline demand levels.

## Solar Production Drivers

Global Horizontal Irradiance (GHI) demonstrates the strongest relationship with photovoltaic output, making it one of the most important predictors in the dataset.

## Wind Production Characteristics

Wind speed and humidity exhibit positive relationships with wind generation, although the relationships are more variable and less predictable than solar irradiance metrics.

## Energy Storage Challenges

Daily and seasonal production fluctuations highlight the importance of energy storage, demand-response strategies, and supplemental generation resources for maintaining grid stability.

---

# 📂 Repository Structure

```text
California-Renewable-Energy-EDA/
│
├── eda.ipynb
├── Database.csv
├── README.md
│
└── images/
    ├── seasonality.png
    ├── correlation.png
    └── solar_ghi.png
```

---

# ⚠️ Limitations

Several considerations should be noted when interpreting results:

- This analysis is observational and does not establish causation.
- Findings are specific to the provided dataset.
- Demand comparisons are based on estimated baseline demand rather than full utility dispatch data.
- Energy storage feasibility is discussed conceptually and is not modeled through battery dispatch simulations.
- External factors such as transmission constraints, market conditions, and policy decisions are outside the scope of this project.

---

# 🚀 Environment Setup

Create an isolated environment and install dependencies:

```powershell
# Create and activate virtual environment
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# Upgrade pip
pip install --upgrade pip

# Install dependencies
pip install pandas matplotlib seaborn scikit-learn jupyter
```

---

# ▶️ Running the Analysis

Launch the notebook:

```powershell
jupyter notebook eda.ipynb
```

Then execute all cells sequentially to reproduce the analysis and visualizations.

---

# 🔁 Reproducing Results

1. Clone the repository.
2. Ensure `Database.csv` is located in the project root directory.
3. Create and activate the virtual environment.
4. Install required dependencies.
5. Launch `eda.ipynb`.
6. Run all notebook cells from top to bottom.

The generated plots and statistics should match the results documented in this repository.

---

# 🧰 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Jupyter Notebook

---

# 📌 Future Improvements

Potential extensions include:

- Time-series forecasting models
- Renewable generation prediction using machine learning
- Battery storage simulations
- CAISO demand integration
- Interactive dashboards using Plotly or Dash
- Weather-normalized production analysis

---

# Summary

This project demonstrates how exploratory data analysis can be used to uncover meaningful relationships between weather conditions and renewable energy production. Through data cleaning, aggregation, correlation analysis, and visualization, the notebook identifies key drivers of solar and wind generation while highlighting seasonal patterns that impact energy availability and grid planning.
