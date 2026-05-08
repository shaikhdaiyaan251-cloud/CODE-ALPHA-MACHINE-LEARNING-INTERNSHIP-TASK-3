# CODE-ALPHA-MACHINE-LEARNING-INTERNSHIP-TASK-4
```markdown
# 🏥 Disease Prediction from Medical Data

> **CodeAlpha Machine Learning Internship – Task 4**  
> Predict the presence of heart disease using patient data with multiple machine learning classifiers, model interpretability, and a live interactive demo – all inside a single Colab notebook.

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/CodeAlpha_DiseasePrediction/blob/main/Disease_Prediction.ipynb)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.5-f7931e)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-2.0-blue)](https://xgboost.readthedocs.io/)

---

## 📖 Table of Contents

- [📌 Project Description](#-project-description)
- [✨ Features](#-features)
- [🛠 Tech Stack](#-tech-stack)
- [📁 Project Structure](#-project-structure)
- [📊 Dataset](#-dataset)
- [🏗️ Model Architecture & Workflow](#️-model-architecture--workflow)
- [🚀 Installation & Setup](#-installation--setup)
- [💻 Usage](#-usage)
- [📈 Performance](#-performance)
- [🖼️ Demo](#️-demo)
- [🔮 Future Improvements](#-future-improvements)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [🙏 Acknowledgements](#-acknowledgements)
- [📬 Contact](#-contact)

---

## 📌 Project Description

**Disease Prediction from Medical Data** builds and compares four machine learning classifiers to predict the likelihood of heart disease based on patient health metrics. The entire process – from data loading to live prediction – runs in a **single Google Colab notebook**, making it fully reproducible without any local setup.

Key highlights:

- Trains **Logistic Regression, Random Forest, XGBoost, and SVM** on the Cleveland Heart Disease dataset.
- Performs comprehensive **EDA, preprocessing, and hyperparameter tuning**.
- Provides **model interpretability** through permutation importance, partial dependence plots, and ICE curves.
- Includes a **live patient simulator** with descriptive sliders and dropdowns to test the model interactively.
- All visualisations (confusion matrices, ROC curves, feature importance, etc.) are generated directly in the notebook.

---

## ✨ Features

- **Multi‑model comparison** – automatically evaluates and ranks four classifiers.
- **Robust preprocessing** – missing value imputation, label encoding, StandardScaler scaling.
- **Stratified train/val/test split** – preserves class balance across splits.
- **Hyperparameter tuning** with `GridSearchCV` (optimising for ROC‑AUC).
- **Model explainability** – permutation importance, partial dependence plots (PDP), and ICE curves.
- **Live prediction interface** – adjust patient parameters via interactive widgets and instantly see the predicted diagnosis.
- **Professional visualisations** – ROC curves, confusion matrices, feature importance bar charts, and a styled metrics comparison table.
- **No external API keys or paid services** – everything runs on Colab’s free CPU/GPU.

---

## 🛠 Tech Stack

| Category             | Tools / Libraries                              |
| -------------------- | ---------------------------------------------- |
| **Language**         | Python 3.8+                                    |
| **Machine Learning** | Scikit‑Learn, XGBoost                          |
| **Data Handling**    | Pandas, NumPy                                  |
| **Visualisation**    | Matplotlib, Seaborn                            |
| **Interpretability** | Scikit‑learn `inspection`, SHAP (optional)     |
| **Interactivity**    | IPywidgets                                     |
| **Environment**      | Google Colab / Jupyter Notebook                |

---

## 📁 Project Structure

```
CodeAlpha_DiseasePrediction/
├── Disease_Prediction.ipynb          # Main Colab notebook (all steps)
├── README.md                         # This file
├── assets/                           # Screenshots and demo images
│   ├── roc_curves.png
│   ├── confusion_matrix.png
│   └── live_prediction.png
└── dataset/                          # (not in repo – uploaded at runtime)
```

---

## 📊 Dataset

We use the **Heart Disease Cleveland** dataset from the UCI Machine Learning Repository.

- **Source**: [Kaggle – Heart Disease Cleveland](https://www.kaggle.com/datasets/ritwikb3/heart-disease-cleveland) (or via `ucimlrepo`)
- **Samples**: ~300 patients
- **Features**: 13 clinical attributes (age, sex, chest pain type, blood pressure, cholesterol, etc.)
- **Target**: `0` (no heart disease) or `1` (heart disease)

> The dataset is **not** stored in the repository. Upload the CSV file when the Colab notebook prompts you – the notebook automatically loads and explores it.

---

## 🏗️ Model Architecture & Workflow

1. **Exploratory Data Analysis (EDA)**  
   - Class distribution, KDE overlays, correlation heatmap.

2. **Preprocessing**  
   - Missing value imputation (median/mode).  
   - Label encoding for categorical features.  
   - `StandardScaler` scaling fitted only on training data.

3. **Model Training**  
   - Train four base models: Logistic Regression, Random Forest, XGBoost, SVM.  
   - Evaluate each on validation set (accuracy, ROC‑AUC).

4. **Hyperparameter Tuning**  
   - `GridSearchCV` on the best performing model (e.g., Random Forest) with stratified 5‑fold CV.

5. **Model Interpretability**  
   - Permutation feature importance.  
   - Partial dependence plots (PDP) for top features.  
   - ICE (Individual Conditional Expectation) curves.

6. **Live Prediction**  
   - `ipywidgets` interface with descriptive dropdowns and sliders.  
   - Preprocesses input identically to training and displays probability gauge.

---

## 🚀 Installation & Setup

### Option 1: Google Colab (Recommended – zero setup)

1. Click the “Open in Colab” badge at the top of this README.
2. Upload the Heart Disease CSV file when prompted (no Google Drive mounting required).
3. Run all cells sequentially – the notebook will install any missing packages automatically.

The notebook runs entirely in your browser; no local environment is needed.

### Option 2: Local machine

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/CodeAlpha_DiseasePrediction.git
   cd CodeAlpha_DiseasePrediction
   ```

2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook Disease_Prediction.ipynb
   ```

4. Place the dataset CSV in the appropriate folder, or modify the upload cell to read from a local path.

---

## 💻 Usage

The notebook is divided into clearly labelled sections. Here’s the flow:

1. **Environment Setup** – imports, style settings, and dataset upload.
2. **Exploratory Data Analysis** – target distribution, feature distributions, correlation matrix.
3. **Preprocessing** – imputation, encoding, scaling, stratified split.
4. **Model Building & Training** – train four classifiers, report validation performance.
5. **Model Evaluation & Comparison** – test set metrics, ROC curves, confusion matrices, feature importance.
6. **Hyperparameter Tuning** – grid search on the best model.
7. **Model Interpretability** – permutation importance, PDP/ICE plots.
8. **Live Prediction** – interactive sliders and dropdowns to simulate a patient and get instant predictions.

All outputs remain visible when you save the notebook (great for sharing).

---

## 📈 Performance

Final evaluation on the held‑out test set (Random Forest model):

| Metric              | Value   |
| ------------------- | ------- |
| Test Accuracy       | 0.XXXX  |
| Precision           | 0.XXXX  |
| Recall              | 0.XXXX  |
| F1‑Score            | 0.XXXX  |
| ROC‑AUC             | 0.XXXX  |

*Replace XXXX with your actual results after training.*  
The model achieves high discriminative power, effectively separating disease from non‑disease cases. Feature importance analysis reveals that `thalach`, `oldpeak`, and `ca` are the most influential predictors.

---

## 🖼️ Demo

![ROC Curves](assets/roc_curves.png)  
*ROC curves comparing all four classifiers on the test set.*

![Confusion Matrix](assets/confusion_matrix.png)  
*Confusion matrix for the best model (Random Forest).*

![Live Prediction](assets/live_prediction.png)  
*Interactive patient simulation: adjusting features instantly updates the disease probability.*

---

## 🔮 Future Improvements

- **Incorporate additional datasets** (e.g., Hungarian, Switzerland, Long Beach) to increase generalisability.
- **Add SHAP** explainability when the library is stable in Colab (already attempted; can be integrated with an upgrade).
- **Try deep learning** – a small multi‑layer perceptron or tabular transformer.
- **Deploy as a web app** – Streamlit or Flask interface for doctors to use.
- **Include more clinical features** (e.g., ECG images, genetic markers) for a more comprehensive model.

---

## 🤝 Contributing

Contributions are what make the open‑source community amazing. Any improvements are welcome!

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/amazing-feature`).
3. Commit your changes (`git commit -m 'Add some amazing feature'`).
4. Push to the branch (`git push origin feature/amazing-feature`).
5. Open a Pull Request.

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for details.

---

## 🙏 Acknowledgements

- **UCI Machine Learning Repository** – for the Cleveland Heart Disease dataset.
- **CodeAlpha** – for the internship and project guidance.
- **Scikit‑learn & XGBoost** communities – for robust machine learning tools.
- All open‑source contributors who make projects like this possible.

---

## 📬 Contact

**DAIYAAN SHAIKH** – [LinkedIn](https://www.linkedin.com/in/daiyaan-shaikh-159909377?utm_source=share_via&utm_content=profile&utm_medium=member_android) – [GitHub](https://github.com/shaikhdaiyaan251-cloud)  
Project Link: [[https://github.com/shaikhdaiyaan251-cloud/CODE-ALPHA-MACHINE-LEARNING-INTERNSHIP-TASK-4](https://github.com/shaikhdaiyaan251-cloud/CODE-ALPHA-MACHINE-LEARNING-INTERNSHIP-TASK-4)]

---

⭐ **If this project helped you learn something, give it a star!** ⭐
```
