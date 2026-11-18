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
<img width="823" height="290" alt="image" src="https://github.com/user-attachments/assets/b7ffccef-de9f-4cea-b1ee-bd24164a628e" />
```
df.info()
```
<img width="340" height="285" alt="image" src="https://github.com/user-attachments/assets/7c0eda21-03fa-4168-b4da-9a27d1df68ee" />
```
df.shape
```
<img width="80" height="30" alt="image" src="https://github.com/user-attachments/assets/25e08344-3ffa-402a-9051-16103c7a78c7" />
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
<img width="625" height="230" alt="image" src="https://github.com/user-attachments/assets/4770640f-6de9-4eca-b195-d75de7eff967" />
```
df.nunique()
```
<img width="260" height="187" alt="image" src="https://github.com/user-attachments/assets/2bd6a140-1be5-47f6-b56e-0346e11acc69" />
```
df["Survived"].value_counts()
```
<img width="263" height="52" alt="image" src="https://github.com/user-attachments/assets/7112ecab-ba0e-4296-8ab9-a3cd97b15890" />
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
<img width="267" height="60" alt="image" src="https://github.com/user-attachments/assets/6f04c100-98ac-4788-9e8e-edd87979754d" />
```
sns.countplot(data=df,x="Survived")
```
<img width="540" height="390" alt="image" src="https://github.com/user-attachments/assets/2a2968e4-809d-4b61-adc7-5c09c1aedbc9" />
```
df
```
<img width="865" height="332" alt="image" src="https://github.com/user-attachments/assets/f9ef612e-ca58-4a04-9c79-721db63ee4d7" />
```
df.Pclass.unique()
```
<img width="238" height="31" alt="image" src="https://github.com/user-attachments/assets/52a44a77-87a5-4d21-aaf8-0d268049f67e" />
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="871" height="342" alt="image" src="https://github.com/user-attachments/assets/2335b3aa-8f84-4725-aaf8-40982a9cc49f" />
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
<img width="810" height="440" alt="image" src="https://github.com/user-attachments/assets/9e40bb71-b416-4569-9430-511d96406fa6" />

```
sns.catplot(x='Survived',hue="Gender",data=df,kind='count')
```
<img width="551" height="432" alt="image" src="https://github.com/user-attachments/assets/242071d6-b466-42f9-a345-d6b0366b5205" />
```
df.boxplot(column="Age",by="Survived")
```
<img width="596" height="415" alt="image" src="https://github.com/user-attachments/assets/71398517-b374-4641-aaf2-28848c24a326" />
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="597" height="385" alt="image" src="https://github.com/user-attachments/assets/06f7383d-d373-4ce4-a0fd-87ad7f3d2f19" />
```
sns.jointplot(x="Age",y="Fare",data=df)
```
<img width="660" height="527" alt="image" src="https://github.com/user-attachments/assets/604c0ba9-0006-4732-8851-b70e7386ebd5" />
```
fig,ax1=plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=df)
```
<img width="632" height="402" alt="image" src="https://github.com/user-attachments/assets/6078f9cb-19de-487b-bb66-654abb75d2d0" />
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
<img width="822" height="410" alt="image" src="https://github.com/user-attachments/assets/aa19e2fa-144b-4beb-b594-022af85d4356" />
```
numerical_df = df.select_dtypes(include=['number'])
corr = numerical_df.corr()
sns.heatmap(corr, annot=True)
```
<img width="457" height="385" alt="image" src="https://github.com/user-attachments/assets/f223e390-afc9-4f63-907a-87dc885d8f69" />
```
sns.pairplot(df)
```
<img width="748" height="712" alt="image" src="https://github.com/user-attachments/assets/890ef0dd-e05c-444d-80f7-afd2f1b4b244" />


# RESULT
     Thus, the Exploratory Data Analysis on the given data set was performed successfully.   
