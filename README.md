# EXNO2DS
## NAME: Sudhindra.R
## REG NO: 212224240164
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
df=pd.read_csv("titanic_dataset.csv")
df
```
<img width="1428" height="516" alt="image" src="https://github.com/user-attachments/assets/dd778f14-4cf9-4a6e-b39a-8a091b61131d" />

```
df.info()
```
<img width="934" height="364" alt="image" src="https://github.com/user-attachments/assets/2e104686-a34f-4f6c-841e-47eff1d9c751" />

```
df.shape
```
<img width="202" height="63" alt="image" src="https://github.com/user-attachments/assets/1760ddfc-6275-4e1d-902f-8aeb38874627" />

```
df.value_counts()
```
<img width="1439" height="279" alt="image" src="https://github.com/user-attachments/assets/d699ce05-d45d-4df1-8c71-2cfaa5b29564" />

```
df['Age'].value_counts()
```
<img width="446" height="263" alt="image" src="https://github.com/user-attachments/assets/5c438040-0522-4f22-8603-347ae61e7757" />

```
df.set_index("PassengerId", inplace=True)
df
```
<img width="1385" height="550" alt="image" src="https://github.com/user-attachments/assets/18aa8f6c-ea4b-4ec8-9621-9bf9596df0ac" />

```
df.nunique()
```
<img width="430" height="274" alt="image" src="https://github.com/user-attachments/assets/3c842c1d-104b-4ad8-83c1-e02ee790a0bc" />

```
sns.countplot(data=df,x='Survived')
```
<img width="988" height="577" alt="image" src="https://github.com/user-attachments/assets/eb77931a-9373-46c7-baf9-6b0f1c9e595e" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1431" height="555" alt="image" src="https://github.com/user-attachments/assets/e2f07d13-28f8-490a-96ea-5fd4f032c2db" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="1109" height="658" alt="image" src="https://github.com/user-attachments/assets/53801f3c-c625-4cbe-a50f-95cd44909768" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="929" height="619" alt="image" src="https://github.com/user-attachments/assets/ce1778e8-877d-4df5-9789-3a524e31aa46" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="1062" height="575" alt="image" src="https://github.com/user-attachments/assets/c46b1190-78f9-4d8a-8681-2e8b9f9bdbb4" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="1123" height="564" alt="image" src="https://github.com/user-attachments/assets/6bfa085c-8bb0-4315-ac55-6641f877742c" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="776" height="534" alt="image" src="https://github.com/user-attachments/assets/3006afef-dcad-4eaa-b08a-f379bd77e231" />

```
sns.catplot(x="Pclass",y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
<img width="757" height="390" alt="image" src="https://github.com/user-attachments/assets/68d22d8a-33be-4399-88d8-8ea82e35f532" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="723" height="573" alt="image" src="https://github.com/user-attachments/assets/9484fb51-1119-4bce-8ea8-9cd3673ab84f" />






# RESULT

Thus, To perform Exploratory Data Analysis on the given data set is implemented successfully.
