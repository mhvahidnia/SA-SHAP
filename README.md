# SA-SHAP: for Polygon-Based Spatial Vector Data (NOTEBOOK:  _SA-SHAP-Case-Study.ipynb_)

This repository provides an implementation of **SA-SHAP** for real-world spatial datasets. The code is designed to run in **Google Colab** or **Jupyter Notebook** and can be easily adapted for your own polygon-based datasets.

---

## Requirements

The implementation requires Python 3 and the necessary geospatial and machine learning libraries (see the notebook or installation section if provided).

The code has been tested in:

- Google Colab
- Jupyter Notebook

---

## Using Your Own Dataset

### Step 1. Specify the input dataset

Locate the following line in the notebook:

```python
geojson_path = "/content/drive/MyDrive/GWR/Ride.geojson"
```

Replace the path with the location of your own **polygon GeoJSON** dataset.

For example:

```python
geojson_path = "/path/to/your/data.geojson"
```

---

### Step 2. Specify the output directory

Locate:

```python
out_dir = "./sa_shap_results"
```

Replace it with your preferred output directory.

Example:

```python
out_dir = "./results"
```

All generated outputs will be saved in this folder.

---

### Step 3. Specify the target and predictor variables

By default, the script assumes that:

- the **first non-geometry column** is the target (dependent) variable,
- all remaining non-geometry columns are predictor (independent) variables.

This is controlled by the following lines:

```python
target_col = non_geom_cols[0]
feat_cols = non_geom_cols[1:]
```

If your dataset uses a different column arrangement, simply modify these lines.

For example:

```python
target_col = "HousePrice"

feat_cols = [
    "Population",
    "Income",
    "RoadDensity",
    "Elevation"
]
```

---

### Step 4. Adjust optional parameters

Other model and analysis parameters can also be modified according to your application.

Please refer to the comments in the notebook for additional customization options.

---

## Input Data

The implementation expects a **polygon GeoJSON** dataset containing:

- one geometry column,
- one target variable,
- one or more predictor variables.

---

## Citation

If you use this implementation in your research, please cite:

> Vahidnia, M.H. (2026). *From local to global XAI: Do local regression contributions correspond to spatially adjusted SHAP (SA-SHAP)?*. Machine Learning with Applications.


---

## Data Source

The example dataset (`Ride.geojson`) is **not an original contribution of this repository**.

It was obtained from the repository accompanying the following work:

https://github.com/Ziqi-Li/SHAP_spatial_data_paper

Please cite the original authors if you use this dataset in your research.

---

## License

Unless otherwise stated, this repository contains only the implementation of the SA-SHAP framework.

The example dataset remains subject to the license and terms specified in the original repository.
