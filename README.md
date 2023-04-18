# Ex-04-Multivariate-Analysis
```
AIM:

To perform Multivariate EDA on the given data set.

EXPLANATION:


Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
```
```
ALGORITHM:
STEP 1

Import the built libraries required to perform EDA and outlier removal.

STEP 2

Read the given csv file

STEP 3

Convert the file into a dataframe and get information of the data.

STEP 4

Return the objects containing counts of unique values using (value_counts()).

STEP 5

Plot the counts in the form of Histogram or Bar Graph.

STEP 6

Use seaborn the bar graph comparison of data can be viewed.

STEP 7

Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8

Save the final data set into the file
```
PROGRAM
```
#Name : VAISHALI BALAMURUGAN
#Register Number : 212222230164


import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
OUTPUT:

![image](https://user-images.githubusercontent.com/119390134/231046966-0448c189-5bc5-4f02-8611-45c54c289d48.png)
![image](https://user-images.githubusercontent.com/119390134/232677868-8e966317-df40-4edf-ac3a-0b2f399c4ba5.png)
![image](https://user-images.githubusercontent.com/119390134/232677930-d1d1b747-fe3a-4ae4-85e3-0862846bdcf3.png)
![image](https://user-images.githubusercontent.com/119390134/232678024-dc09a1d5-120e-42ed-a7dd-fef44a9fef90.png)
![image](https://user-images.githubusercontent.com/119390134/232677965-2f6264a5-19da-4427-beb9-e81f05228552.png)
![image](https://user-images.githubusercontent.com/119390134/232678058-75153c6e-8180-47cf-bbf1-d55d06efb34f.png)
![image](https://user-images.githubusercontent.com/119390134/232678093-70f0f549-ad9c-4c36-b6d6-48e0058c6554.png)
![image](https://user-images.githubusercontent.com/119390134/232678138-a7be508f-e3f5-4d7b-9923-fed936008500.png)
![image](https://user-images.githubusercontent.com/119390134/232678204-05a0f5e4-4907-42b5-9424-9eca65496ef5.png)
![image](https://user-images.githubusercontent.com/119390134/232678256-55fa7cd3-2c4d-443b-bc80-d1c7d12a8e72.png)
![image](https://user-images.githubusercontent.com/119390134/232678359-979bb878-1b07-4acd-9689-85cd80516fe8.png)
![image](https://user-images.githubusercontent.com/119390134/232678416-08068bf7-4dd9-401c-9e93-a400b81f6a62.png)
![image](https://user-images.githubusercontent.com/119390134/232678465-a4b91a89-fccc-424f-a631-1e1dff907ef0.png)


```
RESULT:

 Hence The Performance of the Multivariate EDA on the given data set is verified.
```
