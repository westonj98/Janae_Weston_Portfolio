# Janae_Weston_Portfolio

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv("diabetes_health_indicators.csv")
print(df.head())

# Basic cleaning
df.dropna(inplace=True)

# Summary statistics
print(df.describe())

# Diabetes prevalence by age group
age_diabetes = df.groupby("Age")["Diabetes_binary"].mean().reset_index()
sns.barplot(data=age_diabetes, x="Age", y="Diabetes_binary")
plt.title("Diabetes Prevalence by Age Group")
plt.ylabel("Prevalence (%)")
plt.show()

# BMI distribution for diabetic vs non-diabetic participants
sns.boxplot(data=df, x="Diabetes_binary", y="BMI")
plt.title("BMI Distribution by Diabetes Status")
plt.xlabel("Diabetes Status (0 = No, 1 = Yes)")
plt.show()
