# Retail Business Intelligence & Predictive Analytics Model

## Project Overview

This project explores how data analytics and machine learning can support retail business decisions across demand forecasting, pricing analysis, inventory monitoring, and profitability evaluation.

Using a retail dataset containing **76,000 records and 16 variables**, the project combines exploratory data analysis, business analysis, predictive modelling, and illustrative financial calculations to investigate retail performance.

The central objective is to understand how retailers can use data to balance customer demand, sales performance, pricing decisions, inventory allocation, and profitability.

## Business Questions

This project investigates the following questions:

- Which product categories and regions generate the highest demand?
- How are prices, discounts, and promotions associated with demand?
- Can machine learning help estimate retail demand?
- How does estimated profitability differ across product categories and stores?
- What inventory indicators can help identify areas requiring further investigation?
- How can analytical findings be translated into practical management recommendations?

## Project Workflow

| Stage | Notebook | Main Activities |
|---|---|---|
| 01 | Retail Data Exploration | Data inspection, distributions, correlations and exploratory visualisation |
| 02 | Retail Business Analysis | Category, regional, pricing, discount and illustrative profitability analysis |
| 03 | Demand Prediction | Linear Regression, Random Forest, model evaluation and chronological validation |
| 04 | Pricing & Profitability Optimization | Estimated selling prices, hypothetical costs, profit margins and discount analysis |
| 05 | Business Recommendations | Store and category performance, inventory insights, recommendations and executive summary |

## Dataset

The dataset contains 76,000 records and 16 columns.

Important variables include:

- `Date`
- `Store ID`
- `Product ID`
- `Category`
- `Region`
- `Inventory Level`
- `Units Sold`
- `Units Ordered`
- `Price`
- `Discount`
- `Weather Condition`
- `Promotion`
- `Competitor Pricing`
- `Seasonality`
- `Epidemic`
- `Demand`

The dataset covers five product categories, four regions, five stores and twenty product IDs.

**Data provenance:** The dataset source and its definitions should be independently verified before treating the data as representative of real retail operations. The currency and precise meaning of the `Price` variable have not been established.

## Technology Stack

- **Python** — Core programming language
- **Pandas** — Data manipulation and analysis
- **NumPy** — Numerical computation
- **Matplotlib** — Data visualisation
- **Seaborn** — Statistical visualisation
- **Scikit-learn** — Machine learning and model evaluation
- **SciPy** — Scientific computing
- **Jupyter Notebook** — Interactive analysis
- **VS Code** — Development environment

## Machine Learning Results

Two predictive approaches and a baseline model were evaluated.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 26.45 | 34.29 | 0.4676 |
| Random Forest — Random Split | 16.96 | 23.82 | 0.7431 |
| Random Forest — Chronological Split | 16.00 | 22.34 | 0.7432 |
| Dummy Baseline | 35.43 | 44.37 | -0.0131 |

The final Random Forest model was evaluated using a chronological holdout:

- Training period: January 2022 – August 2023
- Testing period: September 2023 – January 2024
- Training records: 60,800
- Testing records: 15,200

The chronological Random Forest model achieved an R² of approximately **0.743** on the test dataset.

This indicates useful predictive performance on the historical holdout, but does not guarantee future forecasting accuracy or operational readiness.

## Key Business Findings

### Demand Analysis
- Groceries recorded the highest average demand among the categories.
- Clothing also showed strong average demand.
- Furniture recorded the lowest average demand.

### Profitability Analysis
Using illustrative category-level cost assumptions:

- Furniture contributed approximately 35.72% of estimated total profit.
- Clothing contributed approximately 24.47%.
- Groceries generated the highest unit sales but had a comparatively lower estimated profit margin.

### Store Performance
- Store S002 recorded the highest average demand and unit sales.
- Store S004 generated the highest estimated profit and estimated profit margin despite having the lowest average demand.

### Inventory Insights
- Furniture had the highest category-level inventory-to-sales ratio.
- Inventory indicators varied across stores and product categories.

These findings identify areas for further investigation; they do not independently establish causation, overstocking or stockout conditions.

## Illustrative Financial Analysis

The pricing and profitability analysis uses:

- Estimated selling price = `Price × (1 − Discount / 100)`
- Estimated sales value = `Estimated Selling Price × Units Sold`
- Estimated profit = `(Estimated Selling Price − Assumed Unit Cost) × Units Sold`

The category-level cost percentages used are hypothetical assumptions, not verified supplier costs or industry benchmarks.

On the 15,200-record chronological test dataset, the illustrative calculations produced:

| Metric | Result |
|---|---:|
| Estimated sales value | 79,642,881.67 |
| Estimated total profit | 21,868,815.74 |
| Estimated weighted profit margin | 27.46% |

**Important:** These figures are not verified actual revenue or profit. The currency is unspecified, the meaning of `Price` has not been confirmed, and operating expenses, taxes, logistics and other costs are not included.

The analysis is therefore an exploratory profitability model, not a validated pricing optimisation system.

## Repository Structure

```text
Retail-Pricing-Demand-Profitability-Model/
│
├── Data/
│   ├── Raw/
│   │   └── retail_demand.csv
│   └── Processed/
│       └── retail_data_analyzed.csv
│
├── Docs/
├── Notebooks/
│   ├── 01_Retail_Data_Exploration.ipynb
│   ├── 02_Retail_Business_Analysis.ipynb
│   ├── 03_Demand_Prediction.ipynb
│   ├── 04_Pricing_Profitability_Optimization.ipynb
│   └── 05_Business_Recommendations.ipynb
│
├── Python/
├── Reports/
│   ├── final_demand_model_comparison.csv
│   └── final_demand_predictions.csv
│
├── Visualizations/
├── .gitignore
└── README.md
```

Additional generated files may be added to the folders as the project is prepared for publication.

## Installation and Setup

Clone the repository:

```bash
git clone <YOUR_REPOSITORY_URL>
cd Retail-Pricing-Demand-Profitability-Model
```

Create and activate a virtual environment on Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Install the required packages:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn openpyxl ipykernel
```

Open the project in VS Code, select the project virtual environment as the Python interpreter and notebook kernel, and execute the notebooks in numerical order.

## Limitations and Future Improvements

Potential improvements include:

1. Verify dataset provenance, variable definitions and feature timing.
2. Obtain actual product-level costs and verified selling prices.
3. Incorporate operating expenses and inventory holding costs.
4. Investigate potential target leakage and validate feature availability at prediction time.
5. Test forecasting performance on newer, unseen data.
6. Incorporate supplier lead times, stockout records and replenishment information.
7. Evaluate pricing changes through controlled experiments.
8. Develop a more comprehensive optimisation framework using verified business data.

## Project Conclusion

This project demonstrates a complete analytical workflow that connects data exploration, business analysis, predictive modelling and management recommendations.

It highlights an important business insight: **high demand and high sales volume do not necessarily translate into the highest profitability.**

By combining demand estimates with pricing, inventory and cost information, retailers can develop a more comprehensive understanding of business performance.

The project is an exploratory retail decision-support prototype and a practical application of Python, data analytics, machine learning and quantitative business modelling.