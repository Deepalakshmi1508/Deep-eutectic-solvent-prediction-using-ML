# Thermophysical Properties Prediction: Density, Viscosity, and Conductivity

## 📘 Project Overview

This project aims to accurately predict **density**, **viscosity**, and **conductivity** of chemical systems—especially Deep Eutectic Solvents (DES)—using molecular descriptors and AI models. These thermophysical properties are critical for optimizing solvents used in green chemistry, drug delivery, and materials science.

## 🧪 Dataset Description

* **System:** Deep Eutectic Solvents (HBA + HBD combinations)

* **Features:**

  * Molecular descriptors of HBA and HBD
  * Temperature (25°C to 45°C)

* **Targets:**

  * **Density** (g/cm³)
  * **Viscosity** (mPa·s)
  * **Conductivity** (mS/cm)

* **Data Preprocessing:**

  * Convert HBA/HBD names to SMILES
  * Descriptor generation (Mordred/RDKit)
  * Removal of non-numeric/missing descriptors
  * Feature scaling (StandardScaler / MinMaxScaler)

## 🧬 Molecular Descriptor Calculation

* **Tools:**

  * SMILES generation: PubChem API / Manual
  * Descriptor generation: **Mordred**, optionally **RDKit**

* **Preprocessing Workflow:**

  * Merge descriptors of HBA and HBD
  * Add temperature as input feature
  * Save cleaned dataset for model training

## 🔍 Feature Selection Techniques

To reduce dimensionality and improve model accuracy:

* Variance Threshold
* PCA (Principal Component Analysis)
* Recursive Feature Elimination (RFE)
* Autoencoder-based Feature Compression

## 🤖 Machine Learning & Deep Learning Models

### ML Models Used:

* Linear Regression
* Decision Tree Regressor
* Random Forest Regressor
* XGBoost Regressor
* Support Vector Regressor (SVR)
* K-Nearest Neighbors (KNN)

### Ensemble Learning:

* Bagging and Boosting methods used for performance comparison

## 📊 Performance Evaluation

* **Metrics:**

  * R² Score
  * Mean Absolute Error (MAE)
  * Mean Squared Error (MSE)
  * Root Mean Squared Error (RMSE)

* **Visualization:**

  * Actual vs Predicted plots
  * Model performance comparison plots (bar plots for R² and MAE)
  * Residual plots

## 📈 Results Snapshot

| Property     | Best Model        | R² Score | MAE      |
| ------------ | ----------------- | -------- | -------- |
| Density      | XGBoost Regressor | 0.99     | Very Low |
| Viscosity    | Random Forest     | 0.96     | Low      |
| Conductivity | Neural Network    | 0.94     | Low      |

> The XGBoost model consistently performed best for **density**, while deep learning models showed strong results for **conductivity**.

## 📁 Project Structure

```
thermophysical-properties/
│
├── data/                   # Raw and cleaned datasets
├── descriptors/            # HBA and HBD descriptor files
├── feature_selection/      # Feature selection scripts/results
├── models/                 # Trained models (.pkl, .h5)
├── notebooks/              # Jupyter notebooks for training & EDA
├── results/                # Evaluation plots and metrics
├── utils/                  # Helper functions and utilities
├── README.md               # Project documentation
└── requirements.txt        # Python dependencies
```

## 🛠️ Requirements

* Python ≥ 3.8
* Libraries:

  * `pandas`, `numpy`, `scikit-learn`, `xgboost`, `tensorflow`, `keras`, `matplotlib`, `seaborn`, `mordred`, `rdkit`

Install dependencies:

```bash
pip install -r requirements.txt
```

## 💡 Future Work

* Generalize models for broader temperature and pressure ranges
* Develop a web-based GUI for predicting solvent properties
* Explore graph neural networks for structure-based predictions
* Publish as an API for integration into cheminformatics platforms


