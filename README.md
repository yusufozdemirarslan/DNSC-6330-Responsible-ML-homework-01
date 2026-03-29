# COMPAS Recidivism Risk Score Analysis — R to Python Translation

**DNSC 6330: Responsible Machine Learning**
Individual Homework 1

> **Generative AI Disclosure:** Generative AI tools were used as a learning aid during the development of this work — specifically for brainstorming code structure, translating R syntax to Python, and reviewing outputs for accuracy. All AI-generated content was critically reviewed, validated, and integrated as the author's own intellectual product. This disclosure is made in accordance with GW's Generative AI Use Policy.

## Purpose

This repository contains a Python translation of the ProPublica COMPAS recidivism analysis, originally implemented in R as part of DNSC 6330 Lecture 01 (Foundations of the Alignment Problem). The analysis examines the COMPAS risk assessment tool used in criminal justice settings and evaluates its fairness across racial groups.

The workflow covers:

1. **Data loading and preprocessing** — Loading the Broward County COMPAS dataset, selecting analysis variables, filtering invalid records, and creating derived factors.
2. **Exploratory data analysis (EDA)** — Demographic breakdowns, crosstabulations, correlation analysis, and decile score distributions by race.
3. **Logistic regression model** — Building a binomial GLM (`score_factor ~ gender + age + race + priors_count + crime_type + two_year_recid`) to assess whether race is a significant predictor of receiving a higher COMPAS score.
4. **Model diagnostics and fairness metrics** — Computing confusion matrices overall and by race, with False Positive Rate (FPR) and False Negative Rate (FNR) disparity tables.
5. **Interpretation** — Connecting findings to the Alignment Problem framework from lecture.

## Python Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation and analysis |
| `numpy` | Numerical computations |
| `matplotlib` | Data visualization |
| `seaborn` | Statistical data visualization |
| `statsmodels` | Logistic regression (GLM with binomial family) |
| `scikit-learn` | Confusion matrix and classification metrics |

## Reproducing the Results

### Prerequisites

- Python 3.9 or later
- `pip` package manager

### Steps

1. **Clone this repository:**
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Jupyter Notebook:**
   ```bash
   jupyter notebook compas_analysis.ipynb
   ```
   Alternatively, open `compas_analysis.ipynb` in JupyterLab, VS Code, or Google Colab and run all cells sequentially.

4. **Data source:** The notebook automatically downloads the dataset from the [ProPublica COMPAS Analysis repository](https://github.com/propublica/compas-analysis). No manual data download is required.

## Repository Structure

```
.
├── README.md                # This file
├── requirements.txt         # Python dependencies
└── compas_analysis.ipynb    # Main analysis notebook
```

## Data Source

Broward County COMPAS scores and two-year recidivism outcomes from the [ProPublica Machine Bias investigation](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing) (2016).

- Dataset: [`compas-scores-two-years.csv`](https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv)
- Original R analysis: [ProPublica/compas-analysis](https://github.com/propublica/compas-analysis)
