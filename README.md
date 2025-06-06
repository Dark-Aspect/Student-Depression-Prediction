# Student Depression Prediction Project

<div style="text-align: center;">
  <img src="images/Depressed_Student.png" alt="Depressed Student Illustration" width="600"/>
</div>

## Project Overview
This is a project to predict **Student Depression** using the [Student Depression Dataset](https://www.kaggle.com/datasets/hopesb/student-depression-dataset/data) from Kaggle. Understanding and predicting depression among students is an essential task, as mental health plays a critical role in their academic performance and overall well-being.  

## Problem Statement:
Student depression is a serious issue that affects academic success and well-being. This project aims to analyze factors contributing to depression and build a machine learning model to predict students at risk. The goal is to provide insights and tools for early intervention and better mental health support.

## Dataset Overview:
The dataset provides comprehensive information about students and their mental health status, with 18 columns and 27,901 rows, structured in a CSV format. Below is a brief explanation of the columns:  

1. **id**: A unique identifier for each student.  
2. **Gender**: The gender of the student.  
3. **Age**: The age of the student.  
4. **City**: The city where the student resides.  
5. **Profession**: The student's occupation, such as student, part-time worker, etc.  
6. **Academic Pressure**: The level of academic stress experienced by the student.  
7. **Work Pressure**: The work-related stress experienced by the student.  
8. **CGPA**: The student’s cumulative grade point average.  
9. **Study Satisfaction**: The student’s level of satisfaction with their studies.  
10. **Job Satisfaction**: The student’s level of satisfaction with their job or part-time work.  
11. **Sleep Duration**: Average sleep duration in hours per day.  
12. **Dietary Habits**: The dietary pattern of the student (e.g., healthy or unhealthy).  
13. **Degree**: The current level of education the student is pursuing.  
14. **Have you ever had suicidal thoughts?**: A binary column (Yes/No) indicating if the student has had suicidal thoughts.  
15. **Work/Study Hours**: The number of hours spent working or studying per day.  
16. **Financial Stress**: The financial burden or stress experienced by the student.  
17. **Family History of Mental Illness**: A binary column (Yes/No) indicating if the student has a family history of mental health issues.  
18. **Depression**: The target variable, indicating whether the student is experiencing depression (Yes/No).  

> ⚠️ *Disclaimer*: This dataset, given its sensitive nature, must be used responsibly, ensuring ethical considerations like privacy, informed consent, and data anonymization. This project aims to leverage this dataset to build a model capable of predicting depression status in students and identifying significant contributing factors.

## Links to Notebooks & Dashboard

* **Step 1: Data Wrangling**
  `01_data_wrangling.ipynb` – Prepares raw data via cleaning, handling missing values, deduplication, renaming, feature creation.
  🔗 [View Notebook](./01_data_wrangling.ipynb)

* **Step 2: EDA – Visualization**
  `02_eda_visualization.ipynb` – Uses charts and plots to reveal distributions, correlations, and trends for depression-related factors.
  🔗 [View Notebook](./02_eda_visualization.ipynb)

* **Step 3: EDA – SQL Queries**
  `03_eda_sql_queries.ipynb` – Executes SQL queries on the cleaned data to summarize key statistical insights.
  🔗 [View Notebook](./03_eda_sql_queries.ipynb)

* **Step 4: Excel Dashboard**
  `04_excel_dashboard.xlsx` – Dynamic dashboard featuring pivot tables, charts, and slicers to provide interactive insights.
  🔗 [Download Dashboard](./04_excel_dashboard.xlsx)

* **Step 5: Modeling & Prediction**
  `05_modeling_prediction.ipynb` – Builds, tunes, and evaluates Logistic Regression, Decision Tree, and Gradient Boosting models.
  🔗 [View Notebook](./05_modeling_prediction.ipynb)

## Section Summaries

### Step 1: Data Wrangling & Cleaning

This notebook focuses on preparing the dataset for analysis. It starts with importing necessary libraries and loading data, followed by inspecting the dataset for missing values and duplicates. Columns are renamed for consistency, and new features are engineered to improve analysis. Finally, the cleaned dataset is saved for further use. This step ensures data quality and readiness for exploratory analysis.

### Step 2: Exploratory Data Analysis (EDA)

We analyze the dataset through univariate, bivariate, and multivariate approaches, exploring distributions and relationships among variables. Categorical data is encoded to enable deeper statistical analysis. Key insights reveal patterns in demographics, academic factors, lifestyle, and their links to depression. Visualizations highlight how factors like suicidal thoughts, financial stress, and sleep duration strongly relate to depression status.

Below are the boxplots of the continuous numerical variables

![Distribution_by_Depression_Status](images/Distribution_by_Depression_Status.png)

Here is the heatmap showing the correlation between all the variable after encoding

![Correlation Heatmap](images/Correlation_Heatmap.png)

### Step 3: SQL-Based Analysis

Using SQL queries on the cleaned dataset, this step extracts clear numerical summaries and associations. It highlights the prevalence of depression, age and gender differences, and academic performance trends. Regional distribution and lifestyle factors such as diet, sleep, and financial stress are also examined. The findings reinforce the strong connection between mental health and socio-economic, behavioral, and demographic factors.

### Step 4: Interactive Dashboard Design

An interactive dashboard is developed to present key findings visually. It includes bar charts, line charts, pie charts, and maps summarizing student distribution, depression rates, and related factors like stress levels and dietary habits. Important KPIs such as total students, depression rate, and average CGPA are displayed for quick insights. The dashboard enables easy exploration of data trends and supports informed decision-making.

Here is a screenshot of the completed Dashboard

![Excel Dashboard](images/Dashboard.png)

### Step 5: Modeling and Hyperparameter Tuning

This step involves building and evaluating three classification models: Logistic Regression, Decision Tree, and Gradient Boosting. Features were standardized using StandardScaler, and the dataset split into training and test sets. Models were evaluated on accuracy, precision, recall, and F1-score, with cross-validation to ensure stability. Hyperparameter tuning using GridSearchCV and RandomizedSearchCV was performed to optimize each model. Results showed Decision Tree tuning improved generalization, while Logistic Regression and Gradient Boosting had minimal changes. Overall, the tuned models demonstrated strong performance, especially in identifying the "Depressed" class.

Below is the Confusion Matrix for the best model Gradient Boosting Classifier

![Confusion Matrix](images/Confusion_Matrix.png)

Also here is the feature importance ranking for the Gradient Boosting Classifier

![Barplot of feature importances](images/Feature_Importance_Ranking.png)

### Model Comparison

Logistic Regression showed consistent and balanced performance with training accuracy around 83.5% and test accuracy near 83.9%. It achieved strong F1-scores for the "Depressed" class (about 0.87) and moderate scores for the "Not Depressed" class (around 0.80), indicating good generalization and balanced precision and recall.

The Decision Tree initially had slightly higher training accuracy (around 85.7%) but showed some overfitting, reflected in lower test accuracy (\~81.2%). After hyperparameter tuning, the model’s training accuracy slightly decreased to about 83.7%, while test accuracy improved to approximately 83.3%. This tuning also increased F1-scores for both classes, especially improving recall on the "Depressed" class, making the model more balanced and less prone to overfitting.

Gradient Boosting consistently delivered the highest test accuracy (\~84.1%) and strong F1-scores for both classes, with minimal differences before and after tuning. This indicates that the model was already near optimal performance, showing excellent generalization and robust predictions.

In summary, Gradient Boosting is the top-performing model, offering the best balance of accuracy and class-wise performance. The tuned Decision Tree is a close second, benefiting significantly from hyperparameter tuning by reducing overfitting and improving class recall. Logistic Regression remains a reliable, stable option with slightly lower but consistent results.

## Conclusion
This project demonstrates the value of data preprocessing, feature selection, and model tuning in classification tasks. Future work could explore:

1. Testing advanced ensemble models like XGBoost or LightGBM for improved accuracy.
2. Incorporating additional mental health or lifestyle features to enrich the dataset.
3. Applying cross-validation techniques like stratified k-fold for more robust evaluation.

#### Thank you, Feedback would be appreciated!!!