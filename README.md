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

CODING

import numpy as np

import pandas as pd

import matplotlib.pyplot as plt

import seaborn as sns

dt=pd.read_csv("/content/titanic_dataset.csv")

dt

dt.info()

dt.shape

dt.set_index("PassengerId",inplace=True)
dt.describe()

dt.nunique()

dt["Survived"].value_counts()

per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per


sns.countplot(data=dt,x="Survived")

dt

dt.Pclass.unique()

dt.rename(columns={'Sex':'Gender'},inplace=True)
dt

sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)

sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")

dt.boxplot(column="Age",by="Survived")

sns.scatterplot(x=dt["Age"],y=dt["Fare"])

sns.jointplot(x="Age",y="Fare",data=dt)


fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x="Pclass",y="Age",hue="Gender",data=dt)

sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")

corr=dt.corr()
sns.heatmap(corr,annot=True)

sns.pairplot(dt)

OUTPUT

![1](https://github.com/maha712/EXNO2DS/assets/121156360/984438e9-2edc-4e44-a7d8-60aa1e44b2f5)

INFO

![2](https://github.com/maha712/EXNO2DS/assets/121156360/01de25f5-0d8c-4a63-b71e-e19f0fcb9f19)

SHAPE

![3](https://github.com/maha712/EXNO2DS/assets/121156360/f2f24eba-b126-420e-b88f-03d500830c9c)

DESCRIBE

![4](https://github.com/maha712/EXNO2DS/assets/121156360/772ec8f9-a431-4682-941b-27dc86c908a5)

NUNIQUE

![5](https://github.com/maha712/EXNO2DS/assets/121156360/5a44cb18-19ca-4bba-a351-15681bfe6e36)

VALUE COUNTS

![6](https://github.com/maha712/EXNO2DS/assets/121156360/a23e8499-82bf-4bed-8f80-23f8a11ca4f3)

COUNTPLOT

![7](https://github.com/maha712/EXNO2DS/assets/121156360/563ffe98-b84c-4fc3-ae0a-f13be86159d4)

DATA

![8](https://github.com/maha712/EXNO2DS/assets/121156360/fe86f034-d8df-4d24-990a-f642a7f9629c)

PCLASS  UNIQUE

![9](https://github.com/maha712/EXNO2DS/assets/121156360/c8f02f03-20c5-468d-a968-4f16c2e8c3bb)

RENAME

![10](https://github.com/maha712/EXNO2DS/assets/121156360/4d50e30c-111d-4285-b7e1-afd28d5fcf35)

CATPLOT

![11](https://github.com/maha712/EXNO2DS/assets/121156360/2cccdbaf-47b6-4ede-83f9-b6c208bf0e64)

CATPLOT

![12](https://github.com/maha712/EXNO2DS/assets/121156360/4ecf5a5d-18be-47d8-9572-fbecd269becd)

BOXPLOT

![13](https://github.com/maha712/EXNO2DS/assets/121156360/7f7add8a-a740-44a0-be9a-1f7f058ff8c0)

SCATTERPLOT

![14](https://github.com/maha712/EXNO2DS/assets/121156360/91d9b58c-707d-4d94-93fc-eca3d1c5d9f5)

JOINTPLOT

![15](https://github.com/maha712/EXNO2DS/assets/121156360/0586862c-9c59-4596-9e61-f49eac32a9b8)

BOXPLOT

![16](https://github.com/maha712/EXNO2DS/assets/121156360/e07fdac6-954c-4141-9f4a-d2767235f28b)

CATPLOT

![17](https://github.com/maha712/EXNO2DS/assets/121156360/7e263cd6-664d-4a99-9601-44ba9891d536)

Co-relation

![18](https://github.com/maha712/EXNO2DS/assets/121156360/5b09d7c0-42d5-4cd8-821f-44d2fcfc9be2)

PAIR PLOT

![19](https://github.com/maha712/EXNO2DS/assets/121156360/11128609-16ea-4036-aa72-2e642d43c349)

RESULT

        Thus, the Exploratory Data Analysis on the given data set was performed successfully.
