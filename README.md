🪐 CHAKSHU.AI - Hunting for Exoplanets with AI

Automatically classify exoplanet candidates from NASA’s Kepler/K2/TESS missions as Confirmed, Candidate, or False Positive.
Includes preprocessing, a trained model, per-row CSV generation, and a responsive Streamlit web app for researchers.

🚀 Overview

Thousands of exoplanet signals detected by space telescopes require vetting. Manual classification is slow.
ExoDetect uses a multi-class machine learning model to automatically identify true exoplanets, candidates, and false positives based on transit and stellar parameters from NASA’s open datasets.

Key features:

High-accuracy classification optimized for Confirmed planets.

Preprocessing pipeline handles missing values, scaling, and class imbalance.

Exports each row of the dataset as a single CSV file for per-row analysis.

Responsive Streamlit web app for uploading data, viewing predictions, and downloading results.

Model explainability with feature importance and SHAP visualizations.

📂 Dataset

Source: NASA cumulative exoplanet catalog (cumulative_2025.10.03_23.58.46.csv)

Rows: ~9,500 objects from Kepler, K2, and TESS

Features: Orbital period, transit duration, planetary radius, transit depth, SNR, stellar temperature/radius, etc.

Labels:

Confirmed — validated exoplanet

Candidate — likely exoplanet, still under review

False Positive — signal misidentified as planet

The repository also contains a zipped folder of single-row CSVs, one per object, for researchers who need row-level files.

🧠 Model

Type: Gradient Boosting Classifier (XGBoost or LightGBM)

Objective: Multiclass classification (Confirmed / Candidate / False Positive)

Preprocessing:

Median imputation for missing values

Log transform for skewed features

Standard scaling

Imbalance handling: Class weights / sample weights

Evaluation metrics:

Confirmed precision ≈ 0.81

Confirmed recall ≈ 0.83

Macro F1, per-class F1, confusion matrix

Artifacts saved in models/:

preprocessor.joblib

model.joblib

feature_list.json

label_encoder.json

report.json

🖥 Streamlit Web App

The app lets you:

Upload a CSV file of candidate objects or enter feature values manually.

Get per-row predictions and class probabilities.

See per-row analytics:

Probability bar chart

Feature distributions (boxplots) with selected row marked


Download predictions as a CSV file.

Screenshots
<img width="1893" height="892" alt="image" src="https://github.com/user-attachments/assets/dd50a0e4-5297-431f-8a4b-c82f031f802b" />
<img width="1404" height="855" alt="image" src="https://github.com/user-attachments/assets/963066bb-9b31-45b8-a162-559cbbcdbbf7" />
<img width="1466" height="648" alt="image" src="https://github.com/user-attachments/assets/a0c50e7f-b07f-43d3-90a2-35c10f611fc8" />
<img width="1481" height="629" alt="image" src="https://github.com/user-attachments/assets/342b10df-538e-4128-a36a-844170f38385" />




