📈 Rossmann Sales - Machine Learning for Demand Forecasting
Predict daily sales for Rossmann stores and get familiar with time-series forecasting.

📌 Problem Statement
The goal of this machine learning project is to build a model that accurately predicts the daily sales for any given Rossmann store up to six weeks in advance. Accurate sales forecasting is crucial for optimizing staffing, inventory management, and promotional strategies.

🗂️ Dataset Description
The dataset is provided by the Rossmann Store Sales Kaggle competition. It includes:

train.csv – Historical sales data, including store ID, date, and promotions (1,017,209 rows).

test.csv – Data to generate predictions on (41,088 rows).

store.csv – Supplemental information about each store, such as type and competition distance.

Key Columns:
| Column | Description |
| :--- | :--- |
| Sales | The turnover for a given day (Target variable) |
| Store | A unique ID for each store |
| DayOfWeek | Day of the week (1=Monday, 7=Sunday) |
| Promo | Indicates if a store is running a promotion |
| StateHoliday | Indicates a state holiday (0, a, b, c) |
| SchoolHoliday| Indicates if the day is a school holiday |
| StoreType | Differentiates between 4 store models (a, b, c, d) |
| Assortment | Describes assortment level (a, b, c) |
| CompetitionDistance| Distance to the nearest competitor store |
| Promo2 | Indicates if a store participates in a continuing promotion |

🔍 Data Preprocessing & Feature Engineering
Steps performed:

Merged train.csv/test.csv with store.csv.

Imputed missing values in CompetitionDistance and other columns.

Encoded categorical variables: StoreType, Assortment, StateHoliday.

Created new features:

CompetitionAge: Years since a competitor opened.

IsPromoMonth: Binary flag if Promo2 is active for the current month.

Time-based features: Month, Year, WeekOfYear.

Cyclical features: Sin/Cos transformations for Month and DayOfWeek.

🤖 Models Used
Linear Regression (as a baseline)

Decision Tree Regressor

XGBoost Regressor with hyperparameter tuning

🧪 Model Evaluation
Models were evaluated using:

R-squared (R 
2
 ) Score

Root Mean Squared Error (RMSE) on log-transformed sales.

Actual vs. Predicted scatter plots to visualize performance.

📤 Submission
Predictions were made on test.csv, and results were saved in submission.csv with the format:
| Id | Sales |
| :--- | :--- |
| 1 | 4715.068 |
| 2 | 7179.256 |
| ... | ... |
Submitted to the Rossmann Store Sales Kaggle competition.

✅ Best Score
Kaggle Public Leaderboard Score: 0.12984 (RMSPE)
Achieved using an XGBoost Regressor + extensive time-series feature engineering.

🚀 How to Run
1. Clone the repo: 

   git clone https://github.com/GaneshTodkari/rossmann-sales-prediction.git

   cd Rossmann-Sales-Prediction
3. pip install -r requirements.txt
4. jupyter notebook notebooks/rossmann_model.ipynb

📘 Learnings & Takeaways:

Feature engineering is paramount in time-series forecasting, cyclical features and competition age significantly improved the model.

Gradient Boosting models like XGBoost excel at capturing complex, non-linear patterns in sales data.

Log-transforming a skewed target variable like Sales is a crucial step for stabilizing variance and improving model performance.
