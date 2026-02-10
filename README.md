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
```
import pandas as pd
import numpy as np 
import matplotlib.pyplot as plt 
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```

![WhatsApp Image 2026-02-10 at 10 42 09 AM](https://github.com/user-attachments/assets/34b85f9d-a144-48d3-a4b2-e39b93f97449)

```
dt.info()
```
![WhatsApp Image 2026-02-10 at 10 42 47 AM](https://github.com/user-attachments/assets/f094c2d1-d692-446b-8a31-f542a1263f9f)
```
dt.shape
```
![WhatsApp Image 2026-02-10 at 10 43 16 AM](https://github.com/user-attachments/assets/995969c8-4195-4565-9d2c-27b8fabdde93)
```
dt.set_index("PassengerId",inplace=True)
dt.describe()
```
![WhatsApp Image 2026-02-10 at 10 44 20 AM](https://github.com/user-attachments/assets/e888b5b7-b93b-4f35-9fb8-423ac85af992)
```
dt.nunique()
```
![WhatsApp Image 2026-02-10 at 10 45 07 AM](https://github.com/user-attachments/assets/09144c37-8c5e-441b-9941-47b560a508cd)
```
dt["Survived"].value_counts()
```
![WhatsApp Image 2026-02-10 at 10 45 48 AM](https://github.com/user-attachments/assets/e74b05f2-0318-4b2f-9d22-2455e4418923)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![WhatsApp Image 2026-02-10 at 10 46 30 AM](https://github.com/user-attachments/assets/f2aafac1-9c1f-4497-ae12-58ad98781d1b)
```
sns.countplot(data=dt,x="Survived")
```
![WhatsApp Image 2026-02-10 at 10 47 11 AM](https://github.com/user-attachments/assets/065031d2-482a-497f-9172-d911a124b8fa)

```
dt
```
![WhatsApp Image 2026-02-10 at 10 47 35 AM](https://github.com/user-attachments/assets/6c8633e4-2a8b-4844-ac6d-67603b850725)

```
dt.Pclass.unique()
```
<img width="1479" height="164" alt="image" src="https://github.com/user-attachments/assets/0198b7cc-1b8c-47ef-b915-687013952e52" />
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
<img width="1624" height="816" alt="image" src="https://github.com/user-attachments/assets/232452e5-ce69-48d4-b5eb-e61773bcebf8" />
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt, height=5,aspect=.7)
```
<img width="1841" height="758" alt="image" src="https://github.com/user-attachments/assets/1e33d1c8-ce92-48f3-b513-d484e2de18d6" />
```
sns.catplot(x='Survived', hue="Gender",data=dt, kind='count')
```
<img width="1530" height="738" alt="image" src="https://github.com/user-attachments/assets/e5484e01-d1ae-4004-b747-50236d905670" />
```
dt.boxplot(column="Age", by="Survived")
```
<img width="1572" height="877" alt="image" src="https://github.com/user-attachments/assets/9d878dae-e05a-4bbc-88df-7501b92435e9" />
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
<img width="1616" height="735" alt="image" src="https://github.com/user-attachments/assets/9c0e9f07-d739-47b6-9cac-4774fd2ff2c9" />

```
sns.jointplot(x="Age", y="Fare",data=dt)
```
<img width="1913" height="966" alt="image" src="https://github.com/user-attachments/assets/8848a374-153e-4f75-9e67-670f3be608ef" />
```
fig, ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x="Pclass", y="Age", hue="Gender", data=dt)
```
<img width="1907" height="832" alt="image" src="https://github.com/user-attachments/assets/baf34dcf-ae65-4bb4-b0a7-357a012d4110" />
```
sns.catplot(data=dt, col="Survived",x="Gender", hue="Pclass", kind="count")
```
<img width="1888" height="909" alt="image" src="https://github.com/user-attachments/assets/cc45d8b9-738a-42af-98ab-1bcbed25f3ef" />
```
corr = dt.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
<img width="1780" height="581" alt="image" src="https://github.com/user-attachments/assets/8db1ce63-83e9-410e-bcc6-b326a1acaee6" />

```
sns.pairplot(dt)
```
<img width="1803" height="941" alt="image" src="https://github.com/user-attachments/assets/61b0fea5-0372-4b36-83dc-d6f86097e40d" />
```

# RESULT
   Thus, Exploratory Data Analysis for the given dataset is done successfully.
