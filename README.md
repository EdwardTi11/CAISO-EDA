# California Renewable Energy EDA

An exploratory data analysis of California's solar/wind production tracking over 315,000 high-frequency environmental observations. This project analyzes how micro-level weather conditions impact utility-scale grid stability and energy consistency.

**Explore the Project:**
* 📓 Interactive Notebook: [`eda.ipynb`](eda.ipynb)
* 📊 Project Dataset: [`Database.csv`](Database.csv)

---

## 📋 Core Objectives

* **Wind Velocity:** Identify optimal wind speeds where the generation curve flattens.
* **Atmospheric Impedance:** Quantify how rising humidity impacts solar and wind yields.
* **Thermal Coefficients:** Assess how ambient temperature spikes impact photovoltaic (PV) efficiency.
* **Irradiance Profiles:** Analyze seasonal changes across DHI, DNI, and GHI metrics.
* **Complementarity:** Identify seasonal supply mismatches relative to baseline grid demand.

## 📊 Key Insights & Takeaways

* **The Winter Deficit:** Renewable output peaks in summer but plunges drastically in winter. Because winter production falls far short of household baseline demand, a mixed grid infrastructure (incorporating nuclear or gas) remains physically necessary for grid stability.
* **Solar vs. Wind Drivers:** GHI (Global Horizontal Irradiance) acts as the dominant predictor for PV production. While wind speed and humidity show positive relationships with wind production, the correlation is significantly weaker and more volatile.
* **Storage Latency:** Sharp seasonal and daily mismatches between peak supply and demand emphasize the physical constraints of short-duration battery storage systems.

---

## 🛠️ Technical Implementation & Architecture

### Data Pipeline & Engineering
The codebase utilizes a custom `pandas` pipeline to ingest 5-minute sampling logs and extract clean trends:
* `process_data()`: Cleans timestamps, handles missing values, and drops duplicates.
* `average()`: Extracts macro trends using daily resampling (`.resample('D').mean()`) paired with a 30-day centered rolling window (`.rolling()`).
* `graph_data()` & `get_correlation()`: Powers a modular visualization engine capable of stacking weather and energy charts onto a single timeline via `matplotlib` axis injection (`sharex=True`).

### Clean Analytics UX
Implemented dynamic title string parsing (`.replace('_', ' ').title()`) to eliminate raw database formatting and added an integrated correlation heatmap to validate mathematical relationships.

---

## 🚀 Environment Setup & Execution

Run the following continuous block of commands in your terminal to set up the isolated virtual environment, install all dependencies, and immediately boot up the interactive notebook:

```powershell
# 1. Create and activate a virtual environment
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# 2. Upgrade pip and install core data science package stack
pip install --upgrade pip
pip install pandas matplotlib seaborn scikit-learn jupyter

# 3. Launch the Jupyter server and open the workspace notebook
jupyter notebook eda.ipynb