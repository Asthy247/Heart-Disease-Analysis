# Heart-Disease-Analysis
This project explores a heart disease dataset sourced from Kaggle (https://www.kaggle.com/code/estherjames/heart-disease-analysis/edit). The dataset contains information on 1025 patients, including demographic, medical, and lifestyle factors. The goal of this analysis is to identify key risk factors and develop predictive models to aid in the early detection and prevention of heart disease. This document explores a heart disease dataset containing information on 1025 patients. The analysis is performed using Python libraries like pandas for data manipulation and exploration.
# Data Acquisition and Cleaning
The data was loaded from a CSV file named "heart disease dataset.csv" using pandas.read_csv(). Initial exploration revealed duplicate entries (302 duplicates were identified). These duplicates were removed using the drop_duplicates() method.
# Data Exploration
•**	Dataset Shape:** The dataset contains 302 rows (patients) and 14 columns (features).

**•	Data Types:** Most features are integers representing categorical data (e.g., sex, chest pain type). One feature (oldpeak) is a float representing a continuous value.

# Attribute Information:
1.	age
2.	sex
3.	chest pain type (4 values)
4.	resting blood pressure
5.	serum cholestoral in mg/dl
6.	fasting blood sugar > 120 mg/dl
7.	resting electrocardiographic results (values 0,1,2)
8.	maximum heart rate achieved
9.	exercise induced angina
10.	oldpeak = ST depression induced by exercise relative to rest
11.	the slope of the peak exercise ST segment
12.	number of major vessels (0-3) colored by flourosopy
13.	thal: 0 = normal; 1 = fixed defect; 2 = reversable defect

# Missing Values: 
The dataset has no missing values for any feature.
# Descriptive Statistics: 
The describe() method provided summary statistics for each feature, including mean, standard deviation, minimum, maximum, quartiles, etc. This allows us to understand the distribution of values within each feature.
# Key Observations

•	The average age of patients in the dataset is 54.4 years old.

•	Men make up a slightly larger portion of the dataset (68%).

•	The average resting blood pressure is 131.6.

•	The average maximum heart rate achieved during exercise is 149.6.

•	Approximately 33% of patients experience exercise-induced angina (chest pain).

•	The average number of major vessels colored by fluoroscopy is 0.72.

•	Roughly 54% of patients have been diagnosed with heart disease (target value of 1).

# 1.	Correlation Matrix
Calculating correlations between features to identify which features are most strongly associated with heart disease.

**Positive Correlations:**
**•	Target with cp (Chest Pain Type):** 
A strong positive correlation indicates that higher chest pain type (more severe) is associated with a higher likelihood of heart disease.

**•	Target with thalach (Maximum Heart Rate Achieved):** 
A moderate positive correlation suggests that a lower maximum heart rate might be linked to a higher risk of heart disease.

**•	Target with oldpeak (ST Depression Induced by Exercise):** 
A strong negative correlation implies that a higher ST depression is associated with a higher risk of heart disease.

**Negative Correlations:**
**•Target with age**:
A weak negative correlation suggests that older age might be slightly associated with a lower risk of heart disease, but this relationship is not very strong.

**•	Target with chol (Serum Cholesterol):** A weak negative correlation indicates that higher cholesterol levels might be slightly associated with a lower risk of heart disease, but again, this relationship is not very strong.

**Other Notable Observations:**
**•	Chest Pain Type (cp) and Resting Blood Pressure (trestbps):** 
There's a weak positive correlation, suggesting that higher chest pain types might be associated with higher resting blood pressure.

**•	Cholesterol (chol) and Fasting Blood Sugar (fbs): **
A weak positive correlation suggests that higher cholesterol levels might be slightly associated with higher fasting blood sugar levels.
**•	Exercise Angina (exang) and Oldpeak (ST Depression Induced by Exercise): **
A strong positive correlation indicates that individuals with exercise-induced angina are more likely to have higher ST depression.

# 2.	Heart Disease Incidence with Count Plot 
![image](https://github.com/user-attachments/assets/477e7670-9272-4baf-9d90-c866377c3420)

The provided dataset appears to be related to heart disease prediction. 
The target column likely indicates the presence or absence of heart disease, with 0 representing ‘no heart disease’ and 1 representing ‘heart disease’.
**Interpreting the Countplot:**
The countplot visualizes the distribution of the target variable. It shows:

**•	164 patients** do not have heart disease (target = 0).

**•	138 patients** have heart disease (target = 1).

**Insights from the Countplot:**
**•	Class Imbalance**: The dataset exhibits a slight class imbalance, with a higher number of patients without heart disease compared to those with heart disease.

# 3.	Gender Distribution 
Based on the count plot, it appears that there are more male patients than female patients.
![image](https://github.com/user-attachments/assets/a9b07e83-1cbb-44b1-9ae9-6f33e520fe30)

Specifically, there are approximately:
**•	90 Female patients**

**•	200 Male patients**

# 4.	Gender Distribution and Heart Disease:
![image](https://github.com/user-attachments/assets/4bc3aa09-8b3a-4eae-a88c-ba1fcec8e5ed)
Based on the provided bar chart, we can observe the following:
**Gender Distribution and Heart Disease:**
**•	Overall: **The dataset seems to be dominated by males.

**•	Disease Prevalence: **
**o	Females:** A smaller proportion of females have heart disease compared to those who don't.

**o	Males:** A larger proportion of males have heart disease compared to those who don't.
# 5.	Age Distribution
![image](https://github.com/user-attachments/assets/b548cf0f-747d-4e9a-99b6-34102e2bb7c4)

**Observations from the Plot:**
The distribution of ages appears to be **approximately normally distributed**, with a slight skew towards older ages. Here are some key observations:

**•	Peak Age:** The distribution peaks around the age of 55-60, suggesting that a significant portion of the individuals in the dataset fall within this age range.

**•	Age Range:** The ages in the dataset range from approximately 25 to 80 years old.
**•	Skewness**: There's a slight positive skew, indicating that there are more older individuals in the dataset compared to younger ones.

# 6.	Age Distribution
![image](https://github.com/user-attachments/assets/5bd44e48-95ea-4d01-bd9a-fe827b95e3c4)
**Interpretation of the Bar Plot:**
The bar plot visualizes the distribution of different chest pain types (cp) among the patients.
**Key Observations:**
**•	Dominance of Typical Angina: **
The category "typical angina" has the highest count, indicating that a significant portion of the patients experience this type of chest pain.

**•	Lower Frequencies for Other Types: **
The other categories, "atypical angina," "non-anginal pain," and "asymptomatic," have lower counts, suggesting that these types of chest pain are less prevalent.

# 7.	Analyzing the Chest Pain Type vs. Heart Disease Relationship

![image](https://github.com/user-attachments/assets/84287042-be49-453e-8f7d-15942ad9a2dd)
**Understanding the Chart:**
The provided bar chart visualizes the distribution of chest pain types (cp) across two categories:
•**	No-Disease: **Patients who do not have heart disease

**•	Disease:** Patients who have heart disease

**Interpretations:**
**A)	Chest Pain Type 0 (Typical Angina):**

o	A significant number of patients with typical angina have heart disease.
o	This suggests that typical angina is a strong indicator of heart disease.

**B)	Chest Pain Type 1 (Atypical Angina):**

o	A smaller proportion of patients with atypical angina have heart disease.
o	This indicates that atypical angina might be less indicative of heart disease.

**C)	Chest Pain Type 2 (Non-Anginal Pain):**

A significant number of patients with non-anginal pain have heart disease.
This suggests that non-anginal pain can also be a significant indicator of heart disease.

**D)	Chest Pain Type 3 (Asymptomatic):**
A smaller proportion of asymptomatic patients have heart disease.
This indicates that asymptomatic individuals might be at a lower risk of heart disease.

# 8.	Fasting Blood Sugar (FBS) vs. Heart Disease Relationship
![image](https://github.com/user-attachments/assets/92164461-040b-44cd-9dfe-feea055508a9)
**Understanding the Chart:**
The bar chart illustrates the distribution of fasting blood sugar (FBS) levels among patients with and without heart disease.

**Interpretations:**
**A)	FBS Level 0:**
o	A significant number of patients with both heart disease and no heart disease have a fasting blood sugar level of 0.
o	This might suggest that having a fasting blood sugar level below 120 mg/dL is not a strong predictor of heart disease.

**B)	FBS Level 1:**
o	A smaller number of patients with both heart disease and no heart disease have a fasting blood sugar level of 1 (above 120 mg/dL).
o	This indicates that having a fasting blood sugar level above 120 mg/dL might be associated with a higher risk of heart disease, but the difference is not as pronounced as other factors.

# 9.	Histogram of Maximum Heart Rate
![image](https://github.com/user-attachments/assets/0385dc1c-74f8-4434-9004-2ceab51ae7cb)

**Observations from the Histogram:**
The histogram visualizes the distribution of maximum heart rates achieved by individuals in the dataset. Here are some key observations:

**A)	Peak Range:** The majority of individuals seem to have a maximum heart rate between 120 and 140 beats per minute (bpm). This suggests that this range is relatively common.

**B)	Right Skew:** The distribution is slightly skewed to the right, indicating that a few individuals have significantly higher maximum heart rates.
**C)	Range: **The maximum heart rate values range from approximately 100 bpm to 200 bpm.

# 10.	Analyzing the Resting Blood Pressure (trestbps) Distribution by Gender

![image](https://github.com/user-attachments/assets/149c3f59-2016-45b4-bf8c-284896ec9602)
**Understanding the Plot:**
The plot visualizes the distribution of resting blood pressure (trestbps) for both male and female patients. It uses a kernel density estimation (KDE) plot to represent the probability density function of the data.

**Key Observations:**
**•	Overall Shape:** Both distributions appear to be roughly normally distributed, with a peak around 130-140 mmHg. This suggests that the majority of patients have resting blood pressure within this range.

**•	Male vs. Female: **
o	The distribution for males seems to be slightly wider than that for females, indicating a greater variability in resting blood pressure among males.
o	Both distributions overlap significantly, suggesting that there might not be a substantial difference in resting blood pressure between genders in this dataset.

# 11.	Analyzing the Cholesterol Level Distribution
![Uploading image.png…]()
**Observations from the Histogram:**
**•	Peak Range:** The majority of individuals have cholesterol levels between 200 and 300 mg/dL.

**•	Right Skew:** The distribution is slightly skewed to the right, indicating that a few individuals have significantly higher cholesterol levels.

**•	Outliers:** There are a few outliers with cholesterol levels above 400 mg/dL.

# Conclusion
The analysis of the heart disease dataset has provided valuable insights into the factors associated with heart disease. By exploring the distribution of key features and their relationships, we have identified potential risk factors and areas for further investigation.
**Key Findings:**
**•	Demographic Factors**: Age and gender can influence heart disease risk.

**•	Cardiovascular Factors:** Elevated blood pressure, high cholesterol levels, and abnormal heart rate patterns are significant risk factors.

**•	Chest Pain:** Different types of chest pain have varying associations with heart disease.

**•	Lifestyle Factors:** Factors like smoking, physical inactivity, and poor diet can contribute to heart disease risk.

# Recommendations 
**Early Detection and Prevention:**
o	**Regular Health Checkups:** Encourage regular checkups to monitor blood pressure, cholesterol levels, and heart rate.

o**	Healthy Lifestyle**: Promote a healthy lifestyle, including a balanced diet, regular exercise, and stress management.

o**	Smoking Cessation:** Advise individuals to quit smoking.
