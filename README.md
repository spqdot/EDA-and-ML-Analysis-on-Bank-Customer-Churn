# EDA-and-ML-Analysis-on-Bank-Customer-Churn
This project focuses on Exploratory Data Analysis (EDA) and Machine Learning (ML) classification to understand and predict bank customer churn using the Churn_Modelling.csv dataset. The goal is to identify key factors that influence a customer's decision to leave the bank and build predictive models to flag high-risk customers.

📊 Exploratory Data Analysis (EDA)The EDA phase involved cleaning the data and visualizing the relationship between key features and the target variable, 'Exited' (churn).Data Cleaning:The dataset contains 10,000 entries and no missing values (df.isnull().sum()) or duplicate rows (df.duplicated().sum()) were found.Irrelevant columns like RowNumber, CustomerId, and Surname were dropped.Key Churn Observations:
Gender: Female customers have a higher exit rate (25.1%) compared to male customers (16.5%).
Geography: Germany has a significantly higher churn rate (32.4%), which is nearly double the rates of France (16.2%) and Spain (16.7%).
Age: The 35 to 55 age bracket shows the highest absolute number of customer exits.
Credit Card Ownership (HasCrCard): Credit card ownership does not appear to be a significant predictor of churn, as the exit rates for customers with and without a card are very similar (20.2% vs. 20.8%).
Tenure: Churn is distributed across all tenure lengths, but the 35-55 age group appears to have high churn regardless of tenure.
🤖 Machine Learning AnalysisThe second phase involved preparing the data for modeling, including encoding categorical features and scaling numerical features, followed by training and evaluating three different classification models.
1. Data PreprocessingFeature Engineering/Encoding: Categorical features (Geography and Gender) were converted into numerical format using LabelEncoder.
2. Data Splitting: The data was split into features ($\text{X}$) and the target variable ($\text{Y}$ - 'Exited').
3. Scaling: Numerical features for the Logistic Regression model were scaled using StandardScaler. For Decision Tree and Random Forest models, the original unscaled data was used.

 Model Evaluation:
 The models were evaluated based on Accuracy and Precision.ModelModel Training DataAccuracy

Model,               Model Training Data,       Accuracy,            "Confusion Matrix (TN, FP / FN, TP)",            Precision for Exited (1)
Logistic Regression,       Scaled,                 81.50%,                  (1559322​4871​),                                     59.66%
Decision Tree,            Unscaled,                78.20%,                 (1358187​249206​),                                    45.29%
Random Forest,            Unscaled,                86.15%,                  (1542226​51181​),                                    78.02%


