#TEAM-5
# Ceramic 3D Printing Dimensional Error Prediction

## Project Overview
This project investigates the predictability of dimensional error in ceramic extrusion-based 3D printing using machine learning. The main conclusion is a **reproducible negative result**: the recorded process parameters contain no learnable signal for predicting the target.

## Repository Structure
project/
├── data/
│ └── ceramic_3d_printing_data.csv # Main dataset (1000 records, 10 features + target)
├── notebooks/
│ └── ceramic_3d_printing_ml.ipynb # Fully executed notebook with outputs
├── requirements.txt # Python dependencies
└── README.md # This file

text

## Dependencies (Requirements)
To run this notebook locally, install the required libraries using:
```bash
pip install -r requirements.txt
How to Run / Reproduce Results
Option 1: Run on Google Colab (Recommended for Review)
Click the badge below to open the notebook directly in Google Colab. All cells are pre-executed, but you can re-run them via Runtime > Run all.

https://colab.research.google.com/github/hesamsany-hue/Ceramic-3DP-ML/blob/main/notebooks/ceramic_3d_printing_ml.ipynb 

Option 2: Run Locally
Clone this repository:

bash
git clone https://github.com/hesamsany-hue/Ceramic-3DP-ML.git
cd Ceramic-3DP-ML
Install dependencies:

bash
pip install -r requirements.txt
Launch Jupyter Notebook and open notebooks/ceramic_3d_printing_ml.ipynb.

Run all cells sequentially.

Data Access
The dataset is read directly from the data/ folder using a relative path (pd.read_csv('data/ceramic_3d_printing_data.csv')). No manual download or mounting is required when opened via the Colab link, as Colab automatically clones the repository.

Reproducibility Settings
Random Seed: Fixed at 42 for all splitting, model initialization, and cross-validation shuffles to ensure identical results.

Test Set: The test set (15%) is held out from the very beginning and is only used for final evaluation, preventing any data leakage.

Preprocessing: Scaling and encoding are encapsulated inside a sklearn.pipeline.Pipeline and fitted only on the training folds during cross-validation.

Expected Outputs (Key Results)
Upon running the notebook, you should observe the following main outputs:

Best Model Test Performance: XGBoost achieves MAE ≈ 1.205 mm and R² ≈ -0.007 (indicating performance worse than the mean baseline).

Diagnostic Plots: SHAP Summary Plot, Permutation Importance, Learning Curve, and Correlation Matrix confirm the absence of a meaningful signal.

Synthetic Benchmark: The same pipeline achieves R² ≈ 0.99 on a synthetic target with a physical relationship, proving the pipeline is mathematically sound and the limitation lies in the real dataset.

Notes
This project intentionally publishes a negative result to emphasize the gap between data acquisition and model tuning in manufacturing ML workflows.

For any questions, please refer to the main project report.
