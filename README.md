# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
![image](https://github.com/user-attachments/assets/c25dc61a-7a52-4e5b-8da1-33becf86b7e4)
dt.info()
![image](https://github.com/user-attachments/assets/2daf09ba-e42f-4d91-a73c-06ea0c469e52)
dt.set_index("PassengerId",inplace=True)
dt.describe()
![image](https://github.com/user-attachments/assets/53096905-7192-4813-bd58-2ef054f96d9e)
dt.shape
![image](https://github.com/user-attachments/assets/424f987a-bef6-42f4-a66a-a4b743acb296)
dt.nunique()
![image](https://github.com/user-attachments/assets/ed8d7d4c-8454-4ae2-bdf9-8d7571258792)
dt["Survived"].value_counts()
![image](https://github.com/user-attachments/assets/6b798050-1f09-46a0-8de6-be4f533e33c7)
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
![image](https://github.com/user-attachments/assets/09c74cfa-ac92-4459-a31d-ce551e980440)
sns.countplot(data=dt,x="Survived")
![image](https://github.com/user-attachments/assets/8fb9a0b0-f4de-4fe8-98cc-3b72b5e881fa)
dt.Pclass.unique()
![image](https://github.com/user-attachments/assets/bcd4c1e0-c338-4a62-9942-7c1a0b9215d5)
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
![image](https://github.com/user-attachments/assets/f1a5dd0f-80e6-4955-b48c-44f980392b40)
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
![image](https://github.com/user-attachments/assets/f327f485-f18d-4684-b745-24d832bac3ac)
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
![image](https://github.com/user-attachments/assets/76d9dac8-b78f-4c4f-b6f8-236542a80806)
dt.boxplot(column="Age",by="Survived")
![image](https://github.com/user-attachments/assets/bfa1ee87-816f-47c4-8e19-053bebe1255b)
sns.scatterplot(x=dt["Age"],y=dt['Fare'])
![image](https://github.com/user-attachments/assets/30c5b8c8-afd8-469f-baef-969cd6c6277e)
sns.jointplot(x="Age",y="Fare",data=dt)
![image](https://github.com/user-attachments/assets/8b089c6a-fe74-4a00-ac0e-d7c20ecaaf66)
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
![image](https://github.com/user-attachments/assets/a18c6885-1eb7-4971-aae4-c6df41741471)
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
![image](https://github.com/user-attachments/assets/eaf6e5f2-2e9b-4249-9039-7e2d3040b0f0)
corr=dt.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
![image](https://github.com/user-attachments/assets/220c791d-56bf-4015-bf41-b7b8dc559f87)
sns.pairplot(dt)
![image](https://github.com/user-attachments/assets/3b04ee4d-9974-48f3-8bb4-bf5aba1fd3b7)
![image](https://github.com/user-attachments/assets/b4deac22-6971-4f65-b829-60e8b1961cf7)













# RESULT
To perform exploratory data analysis on the given data set is successfully completed.
