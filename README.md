# Telco Customer Churn Analysis

## Project Overview
This project focuses on analyzing customer churn for a telecommunications company. The primary goal is to understand the factors contributing to customer attrition and to build a predictive model that can identify customers at high risk of churning. The analysis provides actionable business insights and strategic recommendations to improve customer retention.

## Features
-   **Data Loading and Cleaning**: Ingesting the raw customer data and handling missing values.
-   **Exploratory Data Analysis (EDA)**: Visualizing and understanding the distribution of key features and their relationship with churn.
-   **Feature Engineering**: Creating new, more informative features from existing ones.
-   **Machine Learning Model Building**: Developing predictive models to forecast customer churn.
-   **Model Evaluation**: Assessing the performance of the churn prediction models using various metrics.
-   **Business Insights & Recommendations**: Deriving actionable strategies based on the analysis to reduce churn and mitigate revenue loss.

## Dataset
The analysis utilizes the `WA_Fn-UseC_-Telco-Customer-Churn.csv` dataset. This dataset contains information about a fictional telecommunications company's customers, including their services, account information, and whether they churned or not. It comprises 7,043 rows and 21 columns.

Key columns include:
-   `customerID`: Unique customer identifier.
-   `gender`, `SeniorCitizen`, `Partner`, `Dependents`: Demographic information.
-   `tenure`: Number of months the customer has stayed with the company.
-   `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`: Services subscribed by the customer.
-   `Contract`, `PaperlessBilling`, `PaymentMethod`: Account information.
-   `MonthlyCharges`, `TotalCharges`: Billing information.
-   `Churn`: The target variable, indicating whether the customer churned (Yes/No).

## Methodology

### Data Preprocessing
-   **Missing Values**: Handled blank strings in `TotalCharges` by converting them to `NaN` and then filling them with the median value.
-   **Feature Encoding**: Categorical variables were encoded for model compatibility.
-   **Feature Engineering**: New features such as `Service_Count` (total number of services), `Customer_Segment`, `Value_Score`, and `Risk_Category` were created to enrich the dataset for better predictive power and business interpretation.

### Exploratory Data Analysis (EDA)
Extensive EDA was performed to uncover patterns and relationships. Key insights included:
-   Customers on month-to-month contracts have significantly higher churn rates.
-   Fiber optic internet service users show a higher propensity to churn.
-   Senior citizens have a higher churn rate compared to non-senior citizens.
-   Electronic check is the payment method most associated with churn.

### Machine Learning Models
Two classification models were implemented and evaluated:
-   **Logistic Regression**
-   **Random Forest Classifier**

Models were trained to predict the `Churn` variable based on the processed features.

### Model Evaluation
Model performance was evaluated using:
-   **Accuracy Score**
-   **ROC-AUC Score**
-   **Classification Report** (Precision, Recall, F1-Score)
-   **Confusion Matrix**

### Feature Importance
The Random Forest model identified the following as top features influencing churn:
-   `tenure`
-   `Contract`
-   `MonthlyCharges`
-   `InternetService`
-   `TotalCharges`

## Key Findings & Business Insights

1.  **Top Churn Drivers**:
    -   **Contract Type**: Month-to-month contracts have a 3-4x higher churn rate than 1-year or 2-year contracts.
    -   **Internet Service**: Fiber optic internet users exhibit the highest churn rate.
    -   **Payment Method**: Electronic checks are strongly linked to higher churn.
    -   **Senior Citizens**: Churn rate for senior citizens is significantly higher (41.7%) compared to non-seniors (23.6%).

2.  **High-Risk Customer Profile**:
    -   **Average Tenure**: ~18 months (vs. 37.6 months for retained customers).
    -   **Average Monthly Charge**: ~$74.44 (vs. $61.27 for retained customers).
    -   **Top Contract Type**: Month-to-month (88.6% of churned customers).
    -   **Top Payment Method**: Electronic check.

3.  **Revenue Impact Estimation**:
    -   **Monthly Revenue Lost to Churn**: ~$139,130.85 (30.5% of total monthly revenue).
    -   **Monthly Revenue at Risk (High Risk tier)**: ~$105,222.75 (23.1% of total monthly revenue).
    -   **Projected Annual Revenue at Risk**: Up to $1.67 million if current churn rates persist.

## Strategic Retention Recommendations

1.  **Target Month-to-Month Customers**: Offer incentives to upgrade to longer-term contracts.
2.  **Address Fiber Optic Internet Users**: Investigate service quality, pricing, or competition issues for this segment.
3.  **Promote Automatic Payments**: Encourage customers using electronic checks to switch to auto-pay methods, possibly with discounts.
4.  **Improve Onboarding for New Customers**: Implement loyalty perks or enhanced support for customers within their first year (0-12 months tenure).
5.  **Proactive Outreach to High-Risk Segment**: Engage with identified high-risk customers (e.g., top 500 churners) with personalized offers.

## Model Summary

-   **Best Model**: Random Forest Classifier
-   **Accuracy**: 77.4%
-   **ROC-AUC**: 84.2%
-   **Top Features**: tenure, Contract, MonthlyCharges, InternetService, TotalCharges

## Repository Contents
-   `data analysis of a Telco-Customer-Churn.ipynb`: The Jupyter Notebook containing the complete data analysis, model building, and insights.
-   `churn_predictions_output.csv`: CSV file containing customer IDs, their predicted churn probabilities, and risk categories.
-   `WA_Fn-UseC_-Telco-Customer-Churn.csv`: The raw dataset used for the analysis.

## Technologies Used
-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Seaborn
-   Scikit-learn

## Usage
To replicate the analysis or explore the code:
1.  Clone this repository.
2.  Ensure you have Python and the listed libraries installed.
3.  Open and run the `data analysis of a Telco-Customer-Churn.ipynb` Jupyter Notebook.

## Author
Manus AI
