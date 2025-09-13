# EXN - O2 DS

# AIM : To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION : The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:

STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.
STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.
STEP 3: Use boxplot method to analyze the outliers of the given dataset.
STEP 4: Remove the outliers using Inter Quantile Range method.
STEP 5: Use Countplot method to analyze in a graphical method for categorical data.
STEP 6: Use displot method to represent the univariate distribution of data.
STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.
STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

# CODING AND OUTPUT

## Exploratory Data Analysis

```
import pandas as pd
import numpy as np
import seaborn as sns
data=pd.read_csv("/content/titanic_dataset.csv")
data
```
<img width="1019" height="420" alt="op1 1" src="https://github.com/user-attachments/assets/47d17838-1f6a-4435-a851-fa37782010c6" />

```
data.info()
```
<img width="368" height="297" alt="op1 2" src="https://github.com/user-attachments/assets/706850dd-32dc-4a33-a215-d79fd675cd2c" />

```
data.describe()
```
<img width="639" height="264" alt="op1 3" src="https://github.com/user-attachments/assets/b43e9372-e983-495a-a83b-d521da9870cc" />

```
data.dtypes
```
<img width="226" height="391" alt="op1 4" src="https://github.com/user-attachments/assets/b2974635-9feb-4648-ab35-f341b05eb841" />

```
data.shape
```
<img width="150" height="53" alt="image" src="https://github.com/user-attachments/assets/ab3af533-6929-4a00-ad4d-d438f90058c6" />

```
data.value_counts()
```
<img width="1011" height="418" alt="op1 5" src="https://github.com/user-attachments/assets/c05ba3fb-e4d1-4cf0-a35a-b4068a484cfe" />

```
data['Name'].value_counts()
```
<img width="430" height="417" alt="op1 6" src="https://github.com/user-attachments/assets/38e99461-b2f8-4c3b-95c2-9cc761dde8b6" />

```
data.set_index("PassengerId") #or data.set_index("PassengerId", inplace=True)
data
```
<img width="1004" height="384" alt="op1 7" src="https://github.com/user-attachments/assets/abd75368-55dd-4137-966c-7cf31854e122" />

```
data.nunique()
```
<img width="188" height="389" alt="op1 8" src="https://github.com/user-attachments/assets/67269439-6882-490f-9eef-bd43c9f03305" />

```
sns.countplot(data=data,x='Survived')
```
<img width="509" height="398" alt="op1 9" src="https://github.com/user-attachments/assets/5d6ca894-cd3b-456c-b3ce-7b94898c4e82" />

```
data.rename(columns={'Sex':'Gender','PassengerId':'P_ID'},inplace=True)
data
```
<img width="963" height="376" alt="op1 10" src="https://github.com/user-attachments/assets/33acc149-1d96-4f87-9db5-6d4caad15cb9" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=data)
```
<img width="839" height="440" alt="op1 11" src="https://github.com/user-attachments/assets/aa1afc10-c2c1-42ce-be77-7d5027b5f249" />

```
data.boxplot(column="Age",by="Survived")
```
<img width="530" height="415" alt="op1 12" src="https://github.com/user-attachments/assets/967a20be-7355-4eed-bdf2-cf091ffd744e" />

```
sns.scatterplot(x=data["Age"],y=data["Fare"])
```
<img width="535" height="392" alt="op1 13" src="https://github.com/user-attachments/assets/384c4e04-cab9-41a0-a170-4cc0b3a76a6a" />

```
plt=sns.boxplot(x='Pclass', y='Age', hue='Gender', data=data)
```
<img width="511" height="376" alt="op1 14" src="https://github.com/user-attachments/assets/3e6ee7a1-6101-410a-9f05-aa4e3a89bd87" />

```
sns.catplot(data=data, col="Survived", x="Gender", hue='Pclass', kind="count")
```
<img width="892" height="441" alt="op1 16" src="https://github.com/user-attachments/assets/bee43844-a3b7-4546-a8f4-e4cd0f00903c" />

```
corr=data.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="470" height="397" alt="op1 17" src="https://github.com/user-attachments/assets/b5de5682-ff60-4afe-8d75-011723f6e7d1" />

# RESULT
Thus, the programs are executed and verified successfully.
