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
df=pd.read_csv("titanic_dataset.csv")
df
```

<img width="1466" height="695" alt="Screenshot 2025-10-09 140949" src="https://github.com/user-attachments/assets/66ddbe36-6dc5-4b22-bd25-af1e12a72b8d" />

```
df.info()
```

<img width="1461" height="474" alt="Screenshot 2025-10-09 140532" src="https://github.com/user-attachments/assets/9387d656-c35b-46a3-a3fc-b655ee1a1cc9" />

```
df.describe()
```

<img width="978" height="415" alt="Screenshot 2025-10-09 140540" src="https://github.com/user-attachments/assets/6ec2ab09-a44f-47fd-b9fa-1904c36bca46" />

```
df.dtypes
```

<img width="801" height="340" alt="Screenshot 2025-10-09 140552" src="https://github.com/user-attachments/assets/50875f79-1505-4de7-af30-1a89b2fef595" />

```
df.shape
```

<img width="304" height="101" alt="Screenshot 2025-10-09 140559" src="https://github.com/user-attachments/assets/02b42f02-30f9-47c7-8842-f830de6602db" />

```
df.value_counts()
```

<img width="1595" height="363" alt="Screenshot 2025-10-09 140912" src="https://github.com/user-attachments/assets/96340544-f21e-4a33-a424-b9441626b34e" />

```
df['Age'].value_counts()
```

<img width="702" height="340" alt="Screenshot 2025-10-09 140638" src="https://github.com/user-attachments/assets/000dc2b3-3496-445a-8163-f76d67331a48" />

```
df.set_index("PassengerId", inplace=True)
df
```

<img width="1344" height="640" alt="Screenshot 2025-10-09 140648" src="https://github.com/user-attachments/assets/441eeaf3-e289-4ea7-997c-c7b01e20179f" />

```
df.nunique()
```

<img width="843" height="321" alt="Screenshot 2025-10-09 140655" src="https://github.com/user-attachments/assets/6ecabeec-dd9d-4b18-bfb3-7331afc33528" />

```
sns.countplot(data=df,x='Survived')
```

<img width="930" height="656" alt="Screenshot 2025-10-09 140706" src="https://github.com/user-attachments/assets/ce1ef8b1-a699-4d78-abc2-814f2fbb4fcb" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1461" height="664" alt="Screenshot 2025-10-09 140713" src="https://github.com/user-attachments/assets/ca8aef4c-36bb-4789-9883-100083cd014e" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="998" height="703" alt="Screenshot 2025-10-09 140720" src="https://github.com/user-attachments/assets/c78ae087-2e52-4960-9849-405199e4cd11" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="939" height="673" alt="Screenshot 2025-10-09 140729" src="https://github.com/user-attachments/assets/9f29d361-cb0e-49d0-9d07-1b1b64c8d219" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="894" height="640" alt="Screenshot 2025-10-09 140735" src="https://github.com/user-attachments/assets/36bb90fd-4d7e-4d4d-9345-8e00bd9e89e9" />

```
fig, axl=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="967" height="633" alt="Screenshot 2025-10-09 140742" src="https://github.com/user-attachments/assets/da0c94cf-eb92-40f7-8451-97af6ac47d90" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```

<img width="1457" height="737" alt="Screenshot 2025-10-09 140749" src="https://github.com/user-attachments/assets/f25f865f-6262-498e-8d34-8f6ac7f55800" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```

<img width="1475" height="733" alt="Screenshot 2025-10-09 140758" src="https://github.com/user-attachments/assets/5c93cb16-42c6-4068-ac09-2414c0911205" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```

<img width="1060" height="652" alt="Screenshot 2025-10-09 140805" src="https://github.com/user-attachments/assets/95c4bc2f-b7ec-433d-9e1d-06bb7aa38d0f" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

<img width="937" height="651" alt="Screenshot 2025-10-09 140811" src="https://github.com/user-attachments/assets/82697d9a-0946-4fec-9b24-73562db67675" />

# RESULT
Thus the programs are executed successfully.



