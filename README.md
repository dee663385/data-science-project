# data-science-project
# Analysis of European Cities Starting with the Letter "Z"

## 1. Problem / Research Question

This project explores a global cities population dataset to answer a focused research question:

**How are European cities whose names start with the letter "Z" distributed across the continent, and can we visualize their spatial pattern using geospatial analysis?**

The analysis also compares the size of the European subset against the global dataset and demonstrates interactive and Voronoi-based mapping techniques for urban geography.

---

## 2. Dataset Source and Usage Permissions

- **Dataset name:** `world_cities_pop.csv` (world cities population dataset)
- **Source:** Public world cities database (a common open dataset containing city names, country codes, coordinates, regions, and population figures)
- **License / Permission:** Public domain / free for educational and non-commercial use. No personally identifiable information (PII) is included.
- **Note:** Population values for some small cities are recorded as `NaN` (missing), which is preserved as-is in the analysis.

> If you obtained this dataset from a specific mirror (e.g., Kaggle or GitHub), replace the Source line above with that URL.

---

## 3. Methods and Tools

### Tools
- **Language:** Python 3.x
- **Environment:** Jupyter Notebook / VS Code
- **Libraries:**
  - `pandas` — data loading, filtering, transformation
  - `geopandas` — geospatial data handling
  - `matplotlib` — static and interactive plotting
  - `shapely` — geometric operations (points, boxes, Voronoi diagrams)
  - `IPython.display` — inline animation of frames in Jupyter

### Methods
1. **Data loading and inspection** — read the CSV with `pandas`, rename `Latitude`/`Longitude` to `lat`/`lon`.
2. **Filtering by continent** — use a manually defined list of European country codes to extract the European subset.
3. **Filtering by city name** — extract European cities whose names start with "Z".
4. **Geospatial construction** — build a `GeoDataFrame` with `Point` geometries using EPSG:4326.
5. **Dot density visualization** — scatter plot of Z-cities with a hover-style tooltip annotation.
6. **Voronoi diagram** — compute Voronoi cells clipped to a bounding envelope and overlay city points.
7. **Interactive filter layer** — simulate stepping through starting letters (A–F) by redrawing the map frame-by-frame in the notebook.

---

## 4. Key Findings and Limitation

### Key Findings
- The full dataset contains **3,173,958** city records, of which **898,604** are European cities (about **28%** of the global dataset).
- Among European cities, only a small fraction have names starting with the letter **"Z"**, and these are concentrated in a few countries rather than evenly spread across the continent.
- The **Voronoi visualization** shows that Z-cities are spatially sparse, with each Voronoi cell covering a relatively large area — reflecting low urban density for this naming subset.
- Population values for many small Z-cities are **missing (`NaN`)**, which limits any population-based comparison.

### Limitation
The analysis is limited by the dataset's **missing population values** for many small cities and by the use of a **hard-coded country-code list** to define "Europe," which may exclude or misclassify some territories. The interactive visualization is also simulated frame-by-frame in the notebook and is not truly interactive outside an interactive matplotlib backend.

---

## 5. How to Run the Analysis

### Step 1 — Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/data-science-project.git
cd data-science-project
