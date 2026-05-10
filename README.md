# XAI3 — Partial Dependence Plots

**Course:** Educational Data Mining (EDM) — Universitat Politècnica de València  
**Authors:** Robert Torres Mingarro, Joel Porcar Sales, Maria Porta Molina  

---

## Overview

This repository contains the third XAI (Explainable Artificial Intelligence) assignment, focused on **model-agnostic interpretability** using **Partial Dependence Plots (PDP)**.

PDPs show the marginal effect of one or two features on the predicted outcome of a previously fitted model. By averaging out the influence of all other features, they isolate the learned relationship between the feature(s) of interest and the model's predictions.

---

## Exercises

### Exercise 1 — 1D PDP: Bike Rental Demand
A Random Forest model is trained on the [Capital-Bikeshare dataset](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset) (`day.csv`) to predict daily bike rentals. One-dimensional PDPs are computed for four key features:
- **Days since 2011** — captures temporal growth and adoption trends
- **Temperature** — reveals an S-shaped comfort-zone effect
- **Humidity** — shows a threshold effect above ~60%
- **Wind speed** — demonstrates a roughly linear negative relationship

### Exercise 2 — 2D PDP: Joint Effect of Temperature and Humidity
A two-dimensional PDP is generated for temperature and humidity, revealing their joint interaction on predicted bike demand. High humidity suppresses demand most strongly on warm days, an interaction not visible in the 1D plots.

### Exercise 3 — 1D PDP: House Price Prediction
The same methodology is applied to the [King County house sales dataset](https://www.kaggle.com/harlfoxem/housesalespredictions) (`kc_house_data.csv`). A Random Forest predicts house prices, and PDPs are computed for `bedrooms`, `bathrooms`, `sqft_living`, and `floors`.

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
