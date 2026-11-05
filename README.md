# Churn_prediction_project


Project Overview
Customer churn occurs when customers stop using a company's products or services. Identifying customers who are likely to leave can help a business understand customer behaviour and take steps to improve retention.

This project analyses customer churn in a subscription-based streaming service dataset. It combines exploratory data analysis, statistical hypothesis testing, survival analysis and classification models to investigate churn patterns and predict whether a customer will churn.

The work is organised into two Jupyter notebooks:
- 01_EDA.ipynb – data cleaning, exploratory analysis, statistical tests, visualisation and survival analysis.
- 02_ModelBuilding.ipynb – preprocessing, feature encoding, scaling, classification model development and performance comparison.
Project Objectives
- Explore customer characteristics and understand the distribution of churn.
- Identify patterns and relationships between customer attributes and churn.
- Apply statistical tests to investigate associations and differences in the data.
- Study customer retention using Kaplan–Meier survival analysis.
- Build classification models to predict customer churn.
- Compare the predictive performance of the implemented models.
Dataset
The notebooks use the Excel dataset Project_Data_Churn.xlsx.

The dataset contains customer and subscription-related information, including variables such as:
- Customer information: Gender, AccountAge and tenure.
- Subscription information: SubscriptionType, PaymentMethod and PaperlessBilling.
- Usage information: ViewingHoursPerWeek, AverageViewingDuration, ContentDownloadsPerMonth and WatchlistSize.
- Customer experience: UserRating and SupportTicketsPerMonth.
- Service preferences: DeviceRegistered, GenrePreference, ContentType, MultiDeviceAccess and ParentalControl.
- Target variable: Churn.
The notebooks handle missing values by imputing numerical variables with their mean and categorical variables with their mode. CustomerID and SubtitlesEnabled are removed during preprocessing.


The first notebook (01_EDA.ipynb) performs the following analyses:
1. Data inspection and cleaning
- Inspect dataset structure, data types and descriptive statistics.
- Identify missing observations.
- Impute missing numerical values using the mean.
- Impute missing categorical values using the mode.
- Remove CustomerID and SubtitlesEnabled.
2. Univariate analysis
- Examine numerical and categorical variables.
- Visualise distributions using histograms, density plots, boxplots and count plots.
- Examine the churn and payment-method distributions.
- Apply the Shapiro–Wilk test to assess normality in selected numerical variables.
3. Bivariate analysis
- Use Spearman rank correlation to examine relationships among numerical variables.
- Apply the Mann–Whitney U test to compare distributions for selected numerical variables in relation to churn.
- Use the Chi-square test of independence to investigate relationships between churn and categorical variables.
- Use visualisations to explore relationships between customer characteristics and churn.
4. Multivariate analysis
- Examine selected combinations of customer and subscription characteristics.
- Use the Kruskal–Wallis test for selected group comparisons.
- Visualise correlations using correlation heatmaps.
- Explore churn proportions across combinations of categorical variables.
5. Survival analysis
- Apply the Kaplan–Meier estimator to examine customer survival over time.
- Plot the survival curve for the analysis period, with tenure capped at 12 months in the notebook.
Machine Learning and Model Building
The second notebook (02_ModelBuilding.ipynb) develops and evaluates three classification models.
Preprocessing
- Handle missing values using mean and mode imputation.
- Remove CustomerID and SubtitlesEnabled.
- Encode categorical variables using LabelEncoder.
- Save the fitted label encoders in encoders.pkl.
- Standardise the input features using StandardScaler.
- Split the data into training and testing sets using an 80:20 ratio and random_state=42.
Models implemented
Model	Implementation
Probit Regression	statsmodels.Probit
Random Forest	sklearn.ensemble.RandomForestClassifier
Gradient Boosting	xgboost.XGBClassifier


Model evaluation
The models are evaluated on the test set using:
- Accuracy score
- Precision
- Recall
- F1-score
- Classification report
- Confusion matrix (for Random Forest and XGBoost models)
The notebook also creates an accuracy comparison table for the three models.

Deployment URL: https://customer-churn-3apr.onrender.com
