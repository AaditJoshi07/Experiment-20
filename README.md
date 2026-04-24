
## Aim
To perform a comprehensive exploratory data analysis (EDA) on global COVID-19 datasets using Python to identify infection trends, recovery rates, and geographical distributions across various countries and Indian states.

---

## Theory of the Code
The analysis follows a systematic data science workflow using **Pandas**, **NumPy**, and **Plotly**:

* **Data Preprocessing**: The notebook begins by importing essential libraries and loading the raw CSV data. It performs "data cleaning" by dropping redundant columns like `SNo` and `Last Update` to focus on core metrics.
* **Feature Engineering**: A new metric, `Active` cases, is calculated using the formula: $Active = Confirmed - Recovered - Deaths$. This provides a more accurate picture of the current pandemic burden than total cases alone.
* **Temporal Filtering**: The code utilizes the `.max()` function on the `ObservationDate` column to filter the dataset, allowing for a focused analysis on the most recent status available in the record (e.g., December 31, 2020).
* **Data Aggregation**: Using `.groupby()` and `.sum()`, the script consolidates data from multiple provinces into unified country-level totals. This is used to identify top-performing and high-risk regions globally, such as the US, India, and Brazil.
* **Geospatial Visualization**: The `plotly.express.choropleth` function is used to create interactive world maps. These maps use color scales (like 'Reds' for confirmed cases and 'Greens' for recoveries) to visualize the intensity of the pandemic across different continents.
* **Regional Deep-Dive (India)**: The script specifically filters for "India" to analyze state-wise performance. It handles missing values in the `Province/State` column by filling them with "Unknown" and then ranks states like Maharashtra and Karnataka by their total confirmed cases.

---

## Conclusion
The analysis successfully demonstrates that data-driven visualization can pinpoint global hotspots and recovery trends. By processing over 300,000 records, the project highlights that while countries like the US and India faced the highest confirmed case counts, localized state-level analysis (such as in Maharashtra) is crucial for understanding the specific impact of the virus within a high-population nation.

