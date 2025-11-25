# 🛒 BigMart Sales Prediction

## 📄 Project Overview
This project focuses on building a machine learning model to predict the **Item Outlet Sales** of various products across different BigMart stores. By analyzing factors such as item properties (weight, visibility, fat content) and store characteristics (establishment year, size, location type), the model aims to provide accurate sales forecasts to assist in inventory management and business strategy.

## 💾 Dataset
The dataset comprises sales data for **1559 products** across **10 stores**, totaling **8523 records**.

* **Source:** BigMart Sales Data
* **Target Variable:** `Item_Outlet_Sales`
* **Key Features:**
    * `Item_MRP`: Maximum Retail Price of the product.
    * `Item_Visibility`: The percentage of total display area of all products in a store allocated to the particular product.
    * `Outlet_Type`: The category of the store (e.g., Grocery Store, Supermarket Type1).
    * `Outlet_Establishment_Year`: The year in which the store was established.

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Libraries:**
    * **Data Processing:** Pandas, NumPy
    * **Visualization:** Matplotlib, Seaborn
    * **Machine Learning:** Scikit-Learn
    * **Gradient Boosting:** XGBoost (Code included, requires library installation)

## 📊 Project Workflow

### 1. Data Cleaning
* **Missing Values:**
    * `Item_Weight`: Imputed using the **median** value.
    * `Outlet_Size`: Missing values were replaced with a new category label **'Missing'**.
* **Data Correction:**
    * Standardized `Item_Fat_Content` categories (e.g., merging 'LF', 'low fat' into 'Low Fat').
    * Handled zero values in `Item_Visibility` by replacing them with the median of non-zero values.

### 2. Feature Engineering
* **`Outlet_Age`**: Created a new feature derived from the establishment year to capture the longevity of the store ($2025 - \text{Year}$).
* **`Item_Type_Combined`**: Simplified 16 different item types into 3 broad categories: **Food**, **Drinks**, and **Non-Consumable**.
* **Encoding**:
    * **Label Encoding** for ordinal features like `Item_Fat_Content`.
    * **One-Hot Encoding** for nominal features like `Outlet_Identifier` and `Outlet_Type`.

### 3. Exploratory Data Analysis (EDA)
* Visualized distributions of numerical features to identify skewness and outliers.
* Analyzed categorical features to understand the balance of classes.
* **Key Insight:** Sales are significantly higher in **Supermarket Type1** stores compared to Grocery Stores.

## 🤖 Model Building & Results
Three regression models were successfully trained and evaluated.

| Model | RMSE | $R^2$ Score |
| :--- | :--- | :--- |
| **Random Forest Regressor** | **1058.39** | **0.6001** |
| Decision Tree Regressor | 1071.74 | 0.5899 |
| Linear Regression | 1097.86 | 0.5697 |

🏆 **Best Model:** The **Random Forest Regressor** achieved the highest accuracy, explaining approx. **60%** of the variance in the target variable.

## 🚀 Future Improvements
* **Hyperparameter Tuning:** Apply Grid Search or Randomized Search to optimize the Random Forest parameters.
* **XGBoost Implementation:** Run the XGBoost model (included in the notebook) to potentially outperform the Random Forest model.
* **Feature Selection:** Analyze feature importance to remove less impactful features and reduce overfitting.

## 📝 How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/nikhilvish201/Sales_Forecasting_Using_Machine_Learning.git](https://github.com/your-username/BigMart-Sales-Prediction.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn xgboost
    ```
3.  **Run the Notebook:**
    Open `Sales_Prediction.ipynb` in Jupyter Notebook or Jupyter Lab and execute the cells.

---
*Created by [Nikhil_Vishwakarma]*
