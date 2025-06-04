# Fire Radiative Power as an Indicator for Forest Fire Prediction: A Study of Machine Learning Architectures

## Abstract

This research project investigates the use of **Fire Radiative Power (FRP)** as a predictive variable for estimating the intensity of forest fires through the application of machine learning techniques to spatiotemporal data. The methodology integrates data preprocessing strategies, spatial encoding, and the evaluation of different models, aiming to support early warning systems and improve the understanding of fire behavior in sensitive biomes.

---

### Data Processing

The FRP time series underwent several preprocessing steps:

- **Temporal Interpolation**: Missing values were filled using interpolation based on the time index to preserve temporal structure.
- **Backfill Imputation**: Remaining gaps were handled with backward filling to ensure completeness.
- **Outlier Treatment**: Values above the 99th percentile were clipped to reduce the influence of extreme observations.
- **Logarithmic Transformation**: A `log1p` transformation was applied to the FRP values to mitigate skewness and improve model learning.
- **Geospatial Transformation**: Latitude and longitude coordinates were converted to radians and projected onto a unit sphere using 3D Cartesian coordinates (`x`, `y`, `z`) to encode spatial information continuously and without discontinuities.

### Feature Engineering

In addition to the transformed FRP, the dataset includes:

- Temporal features (e.g., day of year, hour, seasonality via sine/cosine encoding);
- Categorical variables (e.g., biome, region);
- Spatial embeddings (`x_coord`, `y_coord`, `z_coord`).

---

## Predictive Models

The following machine learning models were trained and evaluated for the regression task of predicting `FRP_log`:

- **TabNet**: A deep learning model for tabular data, employing sequential attention mechanisms.
- **Prophet**: A modular time series forecasting model capable of capturing trends and seasonality.
- **Multilayer Perceptron (MLP)**: Fully connected neural networks evaluated with different architectures and regularization techniques.
- **XGBoost Regressor**: A gradient-boosted decision tree algorithm optimized for structured data.

---

## Objectives

- To assess the predictive power of FRP as an indicator of fire intensity using advanced machine learning techniques;
- To explore the effectiveness of combining temporal, spatial, and environmental features in fire modeling;
- To compare the performance of distinct model architectures in a real-world environmental prediction context.

---

## Relevance

The outcomes of this study have direct applications in:

- Environmental risk monitoring and forecasting;
- Decision support for disaster prevention and mitigation;
- Scientific understanding of fire dynamics in ecological systems.

---