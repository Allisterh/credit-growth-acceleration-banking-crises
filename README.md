# Credit Growth and Acceleration as Predictors of Banking Crises

This repository contains the data, code, figures, and final report for an empirical study on the role of **credit growth** and **credit acceleration** as early warning indicators of **systemic banking crises**.

The analysis follows a macroprudential *early warning* framework widely used in the
literature and by international financial institutions.

---

## Study Overview

**Title:**  
*Credit Growth and Acceleration as Predictors of Systemic Banking Crises*

The study examines whether:

- **Credit growth (Δ Credit)** and  
- **Credit acceleration (Δ² Credit, second difference)**  

significantly increase the probability of systemic banking crises.

The empirical strategy combines panel data econometrics with predictive performance
evaluation, drawing on international macro-financial databases.

---

## Research Objective

To evaluate whether credit growth and, in particular, credit acceleration provide
statistically and economically meaningful signals of impending banking crises using:

- Logit and Probit models  
- Fixed and Random Effects specifications  
- Out-of-sample predictive evaluation via ROC curves  

---

## Main Findings

### Key Results

- Both **credit growth** and **credit acceleration** are statistically significant predictors of banking crises.
- **Credit acceleration** is a **more informative early warning indicator** than simple credit growth.
- The preferred specification achieves an **AUROC = 0.81**, indicating strong discriminatory power.
- Average marginal effects indicate that:
  - +1 p.p. in credit growth → **+0.025 p.p.** increase in crisis probability
  - +1 p.p. in credit acceleration → **−0.057 p.p.** change in crisis probability

### Robustness

- Results are robust to alternative lags (t−1, t−2).
- Consistent across Logit, Probit, Fixed Effects, and Random Effects models.
- Hausman tests favor Random Effects specifications in the baseline sample.

---

## Data Sources

The analysis combines multiple international datasets:

- **BIS Credit Statistics**
- **IMF Global Macro Database**
- **World Bank (WDI)**
- **Systemic Banking Crises Database**  
  Laeven & Valencia (2020)

The final dataset is a balanced/unbalanced country-year panel covering advanced and emerging economies.

---

## Repository Structure

```text
credit-growth-acceleration-banking-crises/
|
|-- README.md
|-- LICENSE
|-- .gitignore
|-- reports/
|   `-- credit-growth-and-acceleration-as-predictors-of-banking-crises.pdf
|-- src/
|   |-- master_credit_growth_banking_crises.do
|   |-- 01_data_preparation.do
|   |-- 02_descriptive_statistics.do
|   |-- 03_panel_logit_models.do
|   `-- 04_robustness_checks.do
|-- data/
|   |-- bis_credit.csv
|   |-- crisis_laeven_valencia.csv
|   |-- macro_controls.csv
|   `-- panel_final.dta
`-- figures/
    |-- fig1_credit_panel.png
    |-- fig2_credit_acceleration.png
    |-- fig_roc_curve.png
    `-- ...
```

---

## Reproducibility

The master script:

```text
src/master_credit_growth_banking_crises.do
```

executes the full workflow:

- Data loading and panel construction.
- Credit growth and acceleration computation.
- Econometric estimation using Logit, Probit, Fixed Effects, and Random Effects models.
- Hausman tests and robustness checks.
- Out-of-sample ROC evaluation.
- Export of tables and figures.

All results reported in the paper can be reproduced by running the master do-file.

---

## Figures Included

- Credit dynamics over time.
- Growth versus acceleration comparisons.
- Crisis-event windows before, during, and after banking crises.
- ROC curve with AUROC = 0.81.

All figures are available in the `figures/` directory.


---

## References

- Borio, C., Drehmann, M., & Tsatsaronis, K. (2014, 2018)
- Drehmann, M. & Juselius, M. (2014)
- Schularick, M. & Taylor, A. (2012)
- Laeven, L. & Valencia, F. (2020)
- BIS Credit Statistics
- IMF Global Macro Database

---

## License

This project is released under the MIT License, allowing free academic and research use,
replication, and adaptation.

---

## Author

Julián Alberto Delgadillo Marín  
M.Sc. in Applied Economics (candidate)  
University of Buenos Aires (UBA)
