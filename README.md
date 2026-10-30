# Bharat Intern — Machine Learning Internship

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4c72b0)
![Internship](https://img.shields.io/badge/Bharat%20Intern-ML%20Internship-orange)

Tasks completed during the **Machine Learning internship at Bharat Intern**: regression and classification models built in Jupyter notebooks.

---

## Tasks at a Glance

| # | Task | Type | Notebook | Status |
|---|---|---|---|---|
| 1 | House Price Prediction | Regression | `House_Price_Prediction.ipynb` | ✅ Complete |
| 2 | Wine Quality Prediction | Regression | `Wine Quality Prediction.ipynb` | ✅ Complete |
| 3 | Iris Flower Classification | Multiclass classification | `Iris Flower Dataset Classification.ipynb` | ✅ Complete |

## Workflow

```mermaid
flowchart LR
    A[CSV dataset] --> B[EDA<br/>shape, dtypes, nulls, duplicates]
    B --> C[Preprocessing<br/>encoding / column cleanup]
    C --> D[Visualisation<br/>heatmap, box plots, pairplot]
    D --> E[Train/test split 70/30]
    E --> F[Model training]
    F --> G[Evaluation<br/>R², MAE / accuracy, confusion matrix]
```

---

## Task 1 — House Price Prediction

*A machine learning model that predicts house prices with linear regression.*

- **Dataset:** `Housing.csv`, 545 rows × 13 columns: `price`, `area`, `bedrooms`, `bathrooms`, `stories`, `mainroad`, `guestroom`, `basement`, `hotwaterheating`, `airconditioning`, `parking`, `prefarea`, `furnishingstatus` ([source link](https://drive.google.com/file/d/1LHaqSqbMvTMHDAx_rlhoqs52m1M09x5c/view?usp=drive_links))
- **Approach:** null and duplicate checks (none found), label-encode the seven categorical columns, correlation heatmap, 70/30 split (381 train / 164 test), `LinearRegression`
- **Results (notebook output):**

| Metric | Value |
|---|---|
| R² | 0.644 |
| MAE | 925,543.55 |

## Task 2 — Wine Quality Prediction

*A machine learning model that predicts wine quality with linear regression, compared against a random forest.*

- **Dataset:** `winequality.csv`, 1,599 rows with 11 physicochemical features (`fixed acidity`, `volatile acidity`, `citric acid`, `residual sugar`, `chlorides`, `free sulfur dioxide`, `total sulfur dioxide`, `density`, `pH`, `sulphates`, `alcohol`) and the target `quality` ([source link](https://drive.google.com/file/d/1CfwNyFVI7yfT_jL9sRiqSmCuqLjnlBSE/view?usp=drive_link))
- **Approach:** null check (none), drop 240 duplicate rows (1,359 remain), target distribution and correlation heatmap, 70/30 split (951 train / 408 test, `random_state=42`), `LinearRegression` and `RandomForestRegressor(n_estimators=200)`
- **Results (notebook output, test set):**

| Model | R² | MAE | Exact score when rounded |
|---|---|---|---|
| Linear Regression | 0.382 | 0.494 | 60.5% |
| Random Forest | 0.437 | 0.473 | 65.7% |

Alcohol, sulphates and volatile acidity are the strongest signals. Most wines score 5 or 6, so the extreme grades (3, 4, 8) are rarely predicted well.

## Task 3 — Iris Flower Classification

*Predicts the species of an iris flower from the length and width of its petals and sepals.*

- **Dataset:** `iris-flowers.csv`, 150 rows, 4 features (`Sepal.Length`, `Sepal.Width`, `Petal.Length`, `Petal.Width`), 3 balanced classes (setosa, versicolor, virginica; 50 each) ([source link](https://drive.google.com/file/d/1Ioe3_LFo-2BoCBkycM1xZzply1Sepdch/view?usp=drive_link))
- **Approach:** drop the index column, check for outliers with box plots, histograms, pairplot by species, 70/30 split (105 train / 45 test, no fixed seed, so a re-run gives slightly different scores), four classifiers compared
- **Results (notebook output, test accuracy):**

| Model | Accuracy |
|---|---|
| Logistic Regression | 97.78% |
| Support Vector Machine (SVC) | 97.78% |
| K-Nearest Neighbors (k=5) | 95.56% |
| Gaussian Naive Bayes | 95.56% |

---

## Tech Stack

- **Language:** Python
- **Libraries:** pandas, NumPy, scikit-learn, Matplotlib, Seaborn
- **Environment:** Jupyter Notebook

## Project Structure

```
Bharat-Intern/
├── House_Price_Prediction.ipynb
├── Housing.csv
├── Iris Flower Dataset Classification.ipynb
├── iris-flowers.csv
├── Wine Quality Prediction.ipynb
├── winequality.csv
├── requirements.txt
├── .gitignore
└── README.md
```

## How to Run

```bash
git clone https://github.com/Gonugunta-Venkata-Jayanth/Bharat-Intern.git
cd Bharat-Intern
pip install -r requirements.txt
jupyter notebook
```

The notebooks read the CSVs by relative path, so start Jupyter from the repository folder.

## Author

**Jayanth Gonugunta Venkata** · [GitHub](https://github.com/Gonugunta-Venkata-Jayanth)
