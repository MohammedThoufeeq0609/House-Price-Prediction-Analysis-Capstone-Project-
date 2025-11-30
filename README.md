# 🏠 House Price Prediction Analysis

A data-driven approach to real estate valuation, leveraging Python to identify quantifiable patterns in residential property prices.

## 📌 Project Overview
The real estate market is complex, with property values influenced by a myriad of physical, locational, and temporal factors. Traditional valuation often relies on subjective appraisal, leading to market inefficiencies. 

This project analyzes a dataset of **2,919 records** with over **80 explanatory variables** to build a robust pricing model. By transitioning from raw, unstructured data to a clean analytical dataset, this project quantifies the marginal value of specific features (such as basement size and renovation status) to empower stakeholders with data-backed investment decisions.

## 📊 Key Business Insights
Based on extensive Exploratory Data Analysis (EDA) and Statistical Validation, the following key drivers were identified:

* **The "Size vs. Age" Dominance:** Total Basement Square Footage (Correlation: 0.61) and Year Built (0.52) are the strongest predictors.
* **Quantifiable Value of Space:** Regression analysis indicates that, on average, every additional square foot of finished basement adds roughly **$111** to the final sale price.
* **The "Condition Paradox":** Properties with "Average" condition often sell for more than "Good" condition homes, likely due to "Average" homes being newer builds, whereas "Good" homes are often older preservations.
* **The Renovation Premium:** Older homes (1950-1980) see a significant value jump if remodeled after 2000, allowing them to compete with new construction.
* **Zoning Price Ceilings:** Commercial (C) properties struggle to exceed $75k, while Residential Low Density (RL) zones command a median near $200k.

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-Learn (Random Forest Regressor)
* **Environment:** Jupyter Notebook / Google Colab

## ⚙️ Methodology
The project follows a structured Data Science Lifecycle:

1.  **Data Preprocessing:**
    * **Imputation:** Numerical features imputed with Median; Categorical with Mode.
    * **Outlier Detection:** Used IQR method to flag outliers in `LotArea` and `SalePrice`.
    * **Transformation:** Applied `Log(1+x)` transformation to `SalePrice` to normalize right-skewed distributions.

2.  **Feature Engineering:**
    * **Temporal Features:** Created `HouseAge` (Reference Year 2011 - YearBuilt) and `YearsSinceRemodel`.
    * **Encoding:** Converted categorical variables using One-Hot Encoding.

3.  **Model Building:**
    * **Algorithm:** Random Forest Regressor (n_estimators=100).
    * **Evaluation Metrics:** R-Squared ($R^2$) and Root Mean Squared Error (RMSE).

## 📂 Dataset Details
* **Source:** House Price Prediction Dataset.
* **Volume:** 2,919 Records.
* **Features:** 81 distinct features including:
    * **Quantitative:** Lot Area, Total Bsmt SF, Gr Liv Area.
    * **Qualitative:** Zoning, Building Type, Overall Condition.

## 🚀 How to Run
1.  Clone the repository:
    ```bash
    git clone [https://github.com/yourusername/house-price-prediction.git](https://github.com/yourusername/house-price-prediction.git)
    ```
2.  Install dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3.  Open the notebook:
    ```bash
    jupyter notebook House_Price_Prediction.ipynb
    ```

## 📈 Results
The final Random Forest model successfully captures non-linear relationships between property features and price, providing a transparent foundation for Automated Valuation Models (AVMs).
