# Hotel Booking Revenue Optimization (Ongoing Group Project)

# Predictive Analytics for Hotel Chain A (OCTAVE - John Keells Group)

## Project Overview
This project aims to help Hotel Chain A reduce revenue lost from booking cancellations and no-shows. By analyzing historical data from OCTAVE, the goal is to move from looking at past problems to predicting future risks. This provides data-driven advice to improve how the hotel chain manages its City, Airport, and Resort properties.

## My Role
Lead Data Engineer & Analyst

## Main Objectives
### 1. Investigative & Exploratory Objectives

Data Quality Issues: Check for missing data or errors in the data to make sure the final results are accurate.

Data Analysis: Identify trends in check-ins and cancellations across different hotel types, behavioral traits and customer demographics.

Key Drivers: Identify features most strongly associated with cancellations.

### 2. Financial & Revenue Analysis Objectives

Quantify Revenue Loss: Calculate the total revenue lost specifically due to cancellations and no-shows.

Segment Analysis: Analyze how this revenue loss varies by customer demographics (Age) and geography (Country and Region) to identify high-risk segments.

### 3. Predictive Modelling Objectives

Risk Prediction: Build a machine learning model to predict the chance of a specific booking being cancelled or becoming a no show.

Performance Testing: Test the model's accuracy, precision, and recall to ensure it provides reliable insights for business users

Interpretability: Determine which features drive the model’s predictions to ensure the results are understandable and useful for hotel management

### 4. Strategic & Operational Objectives

Mitigation Strategies: Propose data-driven interventions and booking management strategies to reduce future revenue loss

Future Data Enhancement: Identify and justify additional data attributes that should be collected to improve future predictive accuracy.

## 5. Key Insights (EDA Findings)
Based on the analysis of 26,986 bookings, the following insights were identified:

The Revenue Leak: 23% of all bookings (6,213 records) are at risk of cancellation or no-show, exposing approximately $1.98M in annual revenue.

Lead Time Risk: Bookings made 100–400+ days in advance carry significantly higher cancellation risk. As lead time increases, the probability of cancellation or no-show rises rapidly.

Deposit Policy Impact: ~15.5% of all no deposite bookings ends up cancelled out of all no deposit bookings, representing the largest volume of financial risk for the cencellations.

Non-Predictive Factors: Demographic data such as Income Level, Educational Level, and Gender showed no meaningful correlation with cancellation behavior.

Property Trends: Resorts experience the highest cancellation rates (23.8%) compared to air port hotels, possibly due to non-urgency of the booking. 

## 6. Methodology
This project follows the end-to-end Data Science Project Lifecycle, moving from industry research to a deployable predictive model. The process is divided into the following five key phases:

### Step 1: Domain Research & Business Understanding

Industry Benchmarking: Researched global and local hospitality trends, comparing Hotel Chain A against competitors like Cinnamon Hotels, Aitken Spence, and Marriott.

Problem Definition: Identified that the lack of a predictive system leads to an annual revenue exposure of $1.98M.

KPI Definition: Established key metrics for success, focusing on Reducing Cancellation Rates and improving Model Accuracy/Recall for high-risk bookings.

### Step 2: Data Engineering & Cleaning

Initial Validation: Audited 27,499 records for inconsistencies. Removed 506 "time-travel" entries where check-in dates preceded booking dates.

Data Integrity: Standardized categorical labels (e.g., "Check-Out" vs "check-out") and handled 4 corrupt Reservation IDs.

Feature Engineering: Derived new, high-impact variables:

Lead_Time: Gap between booking and arrival.

Total_Nights: Duration of stay.

Checkin_Month & Day_of_Week: Capturing seasonal and weekly fluctuations.

Total_Guests: Combined count of adults, children, and babies.

### Step 3: Exploratory Data Analysis (EDA)

Univariate & Multivariate Analysis: Visualized the distribution of cancellations across different Hotel Types and Booking Channels.

Correlation Analysis: Identified that Lead Time and Deposit Type are the strongest predictors of cancellation, while demographic data (Income, Education) showed little to no correlation.

Revenue Mapping: Linked booking statuses to Room Rates to visualize exactly where and why revenue leakage occurs.

### Step 4: ML Modelling & Pipeline Development

Preprocessing: Applied One-Hot Encoding for categories and StandardScaler for numerical data to ensure model compatibility.

Algorithm Selection: Developed and compared multiple models: Logistic Regression, Decision Trees, and Gradient Boosting.

Class Imbalance Handling: Used class_weight='balanced' to ensure the model accurately identifies the 23% minority class (Cancellations/No-shows).

### Step 5: Validation, Tuning & Interpretability

Hyperparameter Optimization: Utilized GridSearchCV with 5-fold stratified cross-validation to refine the Gradient Boosting model.

Performance Scoring: Evaluated the final model using Accuracy (71%), Precision, Recall, and ROC-AUC curves.

Model Explainability: Integrated SHAP values to determine which features most heavily influence a "High Risk" flags, ensuring the model's output is actionable for hotel management.
