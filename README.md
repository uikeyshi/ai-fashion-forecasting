# AI Fashion Forecasting — Trend Intelligence Pipeline

An end-to-end machine learning project that models and forecasts **fashion trend momentum** using quantitative behavioral, market, and contextual signals.  
The project compares multiple modeling approaches to understand how different algorithms capture seasonality, consumer demand, and non-linear trend dynamics.

This repository mirrors how fashion, retail, and consumer-analytics teams prototype forecasting systems before deploying them on proprietary data.

---

## Project Overview

The goal of this project is to simulate a **trend intelligence system** that predicts a composite **trend heat score (0–100)** representing overall trend strength and adoption potential.

Rather than relying on a single algorithm, the pipeline evaluates multiple model families and selects the best performer using empirical metrics.

### What the project does
- Loads a structured fashion trend dataset
- Preprocesses categorical and numerical features
- Trains and compares:
  - Linear Regression
  - Ridge Regression
  - Decision Tree Regression
  - Neural Network (MLP)
- Evaluates models using **MAE, RMSE, and R²**
- Produces visualizations to support model selection decisions

---

## Dataset

### Raw Data
Located in: data/raw/fashion_trends_project.csv

Each row represents a trend observation for a specific time period, category, and region.

### Feature Groups

**Behavioral & Demand Signals**
- `social_buzz` — normalized social media engagement signal
- `search_interest` — consumer demand signal (0–100 scale)
- `influencer_posts` — volume of creator-driven content

**Market & Brand Signals**
- `price_index` — relative pricing pressure
- `sustainability_score` — sustainability alignment score

**Contextual Signals**
- `season` — winter / spring / summer / fall
- `category` — fashion segment (streetwear, luxury, athleisure, etc.)
- `region` — geographic market

### Target Variable
- `trend_score (0–100)` — a composite **trend momentum index** used to rank trends internally for design, inventory, and marketing decisions.

---

## Processed Data

Located in:data/processed/


Includes:
- `fashion_trends_processed.csv`
- `X_train.csv`, `X_test.csv`
- `y_train.csv`, `y_test.csv`

These files reflect one-hot encoded features and an 80/20 train-test split.

---

## Modeling Approach

The project intentionally compares different model families to highlight tradeoffs:

| Model | Purpose |
|-----|--------|
| Linear Regression | Baseline, high interpretability |
| Ridge Regression | Regularized linear model |
| Decision Tree | Captures non-linear rules |
| Neural Network (MLP) | Captures complex feature interactions |

Models are evaluated using:
- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**
- **R² (Explained Variance)**

---

## Results & Outputs

Generated outputs include:
- `model_results.csv` — model comparison metrics
The full analysis is contained in: notebooks/ai_fashion_forecasting_end_to_end.ipynb


The notebook includes:
- Data loading
- Preprocessing
- Model training and evaluation
- Visualization
- Final conclusions

---

## Automation (GitHub-Only Workflow)

This repository supports a **GitHub-only workflow**:
- All data and artifacts are stored directly in the repo
- A GitHub Actions workflow can execute the notebook automatically on push
- Results can be reviewed via the GitHub Actions artifacts

No Google Colab or local Jupyter setup is required.

---

## How to Reproduce (Optional)

If running locally or in GitHub Codespaces:

```bash
pip install -r requirements.txt
jupyter notebook
```

Then run:

```bash
notebooks/ai_fashion_forecasting_end_to_end.ipynb
```
