# XAI3 — Partial Dependence Plots

**Course:** Evaluación, Despliegue y Monitorización de Modelos (EDM) — Universitat Politècnica de València  
**Authors:** Robert Torres Mingarro, Joel Porcar Sales, Maria Porta Molina  

---

## Project Overview

This repository presents a comprehensive analysis of **model-agnostic interpretability** techniques, specifically focusing on **Partial Dependence Plots (PDP)**.

While highly accurate, non-parametric machine learning models like Random Forests are often considered "black boxes" due to their complex internal structures. PDPs address this limitation by showing the marginal effect of one or two features on the predicted outcome. By averaging out the influence of all other features, PDPs isolate the learned relationship between the features of interest and the model's predictions, enabling robust, global interpretation.

---

## Analysis Scope

The project applies PDP methodology to two distinct real-world predictive modeling scenarios:

### 1. Bike Rental Demand Forecasting
A Random Forest model is trained on the [Capital-Bikeshare dataset](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset) (`day.csv`) to predict daily bike rental volume. The analysis includes:
- **1D Partial Dependence**: Evaluating four key drivers of demand:
  - **Temporal Trend (Days since 2011)**: Capturing service growth and adoption phases.
  - **Temperature**: Identifying the optimal, non-linear thermal comfort zone.
  - **Humidity**: Revealing a strict threshold effect above 60% humidity.
  - **Wind Speed**: Demonstrating a continuous, linear negative impact.
- **2D Partial Dependence**: Generating a joint heatmap for temperature and humidity, which reveals a critical interaction: high humidity suppresses demand most severely on warm days when baseline demand would otherwise be at its peak.

### 2. House Price Prediction
To demonstrate the versatility of the approach across domains, the methodology is applied to the [King County house sales dataset](https://www.kaggle.com/harlfoxem/housesalespredictions) (`kc_house_data.csv`). A second Random Forest model predicts property values, and 1D PDPs are utilized to isolate the marginal pricing impacts of `bedrooms`, `bathrooms`, `sqft_living`, and `floors`.

---

## Repository Structure

```
XAI3-Partial-Dependence-Plots/
├── XAI3_PDP_Report.Rmd          # Main R Markdown source (PDF output)
├── XAI3_PDP_Report.pdf          # Rendered PDF report
├── XAI3_PDP_Report_HTML.Rmd     # HTML version (all code visible)
├── XAI3_PDP_Report_HTML.html    # Rendered HTML report
├── day.csv                      # Bike sharing dataset
├── kc_house_data.csv            # King County house prices dataset
└── README.md
```

---

## How to Reproduce

1. Open `XAI3_PDP_Report.Rmd` (or the HTML version) in RStudio.
2. Ensure the following R packages are installed:
   ```r
   install.packages(c("dplyr", "ggplot2", "randomForest", "pdp", "gridExtra", "scales"))
   ```
3. Place `day.csv` and `kc_house_data.csv` in the same directory as the `.Rmd` file.
4. Click **Knit** in RStudio.

---

## Branch Structure

- `main` — stable, final version of the report
- `development` — working branch with incremental changes and draft versions
