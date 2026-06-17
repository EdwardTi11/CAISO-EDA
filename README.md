# California Renewable Energy EDA

An exploratory data analysis of California renewable energy production using more than **315,000 high-frequency environmental observations**. This project investigates how weather variables influence solar and wind generation and examines seasonal patterns that affect energy availability and grid reliability.

---

## Repository Structure

```text
California-Renewable-Energy-EDA/
│
├── eda.ipynb          # Main analysis notebook
├── Database.csv       # Renewable energy dataset
├── requirements.txt
├── README.md
│
└── images/
    ├── seasonality.png
    ├── correlation.png
    └── solar_ghi.png
```

---

## Project Objectives

This analysis explores several questions regarding renewable energy behavior:

* At what wind speeds does generation begin to plateau?
* How does humidity affect solar and wind output?
* What impact does temperature have on photovoltaic efficiency?
* How do irradiance metrics (GHI, DNI, DHI) vary seasonally?
* How well does renewable production align with electricity demand?

---

## Dataset Overview

The dataset contains approximately **315,000 observations collected at 5-minute intervals**.

### Features

| Variable         | Description                   |
| ---------------- | ----------------------------- |
| Temperature      | Ambient air temperature       |
| Humidity         | Relative humidity             |
| Wind Speed       | Wind velocity                 |
| GHI              | Global Horizontal Irradiance  |
| DNI              | Direct Normal Irradiance      |
| DHI              | Diffuse Horizontal Irradiance |
| Solar Production | Solar energy output           |
| Wind Production  | Wind energy output            |
| Timestamp        | Observation date and time     |

The combination of environmental measurements and production metrics enables correlation analysis and long-term trend discovery.

---

## Analysis Pipeline

### 1. Data Cleaning

* Timestamp normalization
* Duplicate removal
* Missing value handling
* Data type validation

### 2. Feature Aggregation

Because observations occur every five minutes, broader trends are extracted using:

* Daily resampling
* Mean aggregation
* 30-day centered rolling averages

### 3. Exploratory Analysis

The notebook investigates:

* Seasonal production cycles
* Weather-production relationships
* Correlation structures
* Long-term trends
* Renewable generation variability

### 4. Visualization

Custom plotting functions are used to compare:

* Environmental variables
* Solar production
* Wind production
* Demand estimates

using synchronized timelines and shared axes.

---

## Key Findings

### Seasonal Production Imbalance

Renewable generation peaks during summer months and declines during winter, creating a mismatch between energy availability and baseline demand.

### Solar Production Drivers

Global Horizontal Irradiance (GHI) exhibits the strongest relationship with photovoltaic output and serves as one of the most important predictors in the dataset.

### Wind Production Characteristics

Wind speed and humidity show positive relationships with wind generation, though these effects are more variable than solar irradiance metrics.

### Grid Reliability Challenges

Daily and seasonal fluctuations highlight the importance of energy storage, demand-response strategies, and supplemental generation sources.

---

## Example Visualizations

### Seasonal Production Trends

```text
images/seasonality.png
```

### Correlation Heatmap

```text
images/correlation.png
```

### Solar Irradiance Relationships

```text
images/solar_ghi.png
```

---

## Installation

### Clone the repository

```bash
git clone https://github.com/your-username/california-renewable-energy-eda.git
cd california-renewable-energy-eda
```

### Create a virtual environment

```bash
python -m venv .venv
```

Activate it:

**Windows**

```bash
.venv\Scripts\activate
```

**Linux / macOS**

```bash
source .venv/bin/activate
```

### Install dependencies

```bash
pip install -r requirements.txt
```

---

## Running the Analysis

Launch Jupyter Notebook:

```bash
jupyter notebook eda.ipynb
```

Then run all cells sequentially to reproduce the analysis and visualizations.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Jupyter Notebook

---

## Limitations

* This analysis is observational and does not establish causation.
* Results are specific to the provided dataset.
* Demand comparisons rely on estimated baseline demand.
* Battery dispatch and storage optimization are not modeled.
* External market and policy factors are outside the scope of this study.

---

## Future Improvements

* Time-series forecasting models
* Renewable production prediction with machine learning
* Battery storage simulations
* CAISO demand integration
* Interactive dashboards using Plotly or Dash
* Weather-normalized production analysis

---

## License

This project is intended for educational and research purposes via the MIT License.