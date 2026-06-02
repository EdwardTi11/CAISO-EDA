# California Renewable Energy EDA

An exploratory data analysis of California's solar/wind production tracking over 315,000 environmental observations. This project analyzes how micro-level weather conditions impact utility-scale grid stability and energy consistency.

## 📋 Core Objectives
1. **Wind Velocity:** Identify optimal wind speeds where generation curve flattens.
2. **Atmospheric Impedance:** Quantify how rising humidity drops solar and wind yields.
3. **Thermal Coefficients:** Assess how ambient temperature spikes impact photovoltaic efficiency.
4. **Irradiance Profiles:** Analyze seasonal changes across DHI, DNI, and GHI metrics.
5. **Complementarity:** Identify seasonal supply mismatches relative to baseline grid demand.

## 📊 Key Takeaways
* **The Winter Deficit:** Renewable output peaks in summer but plunges drastically in winter. Because winter production falls far short of household baseline demand, a mixed grid infrastructure (incorporating nuclear or gas) is physically necessary for grid stability.
* **Storage Latency:** Seasonal and daily mismatches between peak supply and demand emphasize the physical constraints of short-duration battery storage systems.

## 🛠️ Technical Implementation
* **Data Engineering:** Built a custom pandas pipeline to ingest 5-minute sampling logs and extract clean trends using daily resampling (`.resample('D').mean()`) and a 30-day centered rolling window (`.rolling()`).
* **Modular Visuals:** Engineered a flexible visualization engine capable of stacking weather and energy charts onto a single timeline via matplotlib axis injection (`sharex=True`).
* **Clean Analytics UX:** Implemented dynamic title string parsing (`.replace('_', ' ').title()`) to eliminate raw database formatting and added an integrated correlation heatmap to validate mathematical relationships.
