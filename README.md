# Ex-04-Multivariate-Analysis
# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1:
Import the built libraries required to perform EDA and outlier removal.

# STEP 2:
Read the given csv file.

# STEP 3:
Convert the file into a dataframe and get information of the data.

# STEP 4:
Return the objects containing counts of unique values using (value_counts()).

# STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

# STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

# STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr() .

# STEP 8:
Save the final data set into the file.

# PROGRAM:
NAME:kavya.k REG NO:212222230065.

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
# OUTPUT:
# DATASET

![image](https://user-images.githubusercontent.com/118668727/236998730-294f57b8-ec4d-414a-9fbb-bd3e85595fea.png)
# HEAD()

![image](https://user-images.githubusercontent.com/118668727/236998810-d8055e0c-8037-4d79-90e5-18663e318569.png)
# INFO()
![image](https://user-images.githubusercontent.com/118668727/236999159-96bdff5c-8678-40b1-9bc2-39b614f40989.png)
# DESCRIBE()
![image](https://user-images.githubusercontent.com/118668727/237000506-4171823f-e6e5-490c-a6d4-2b9124638808.png)
# DATATYPE()
![image](https://user-images.githubusercontent.com/118668727/237000557-7e178b5b-a940-4cdc-b0fa-f85ba61e2294.png)
# ISNULL()
![image](https://user-images.githubusercontent.com/118668727/237000638-bb54f3ac-e09b-48c2-b918-6a11323419d7.png)
# Postal code has outliers.
![image](https://user-images.githubusercontent.com/118668727/237000693-154e3dc9-975e-4bde-9fe4-7921eff5c894.png)
After removing outliers from Postal Code.
MULTIVARIATE ANALYSIS
# SCATTER PLOT

![image](https://user-images.githubusercontent.com/118668727/237000747-73202fa2-9043-4f7e-a82f-60f3706daf58.png)
# BARPLOT
![image](https://user-images.githubusercontent.com/118668727/237000892-9b8d933b-f84d-45c7-b35d-6d6ae35f7fc5.png)
![image](https://user-images.githubusercontent.com/118668727/237000917-ea81cdb2-97b8-41c8-9c9c-b0dd0d1e7d62.png)
# SEGMENTATION
![image](https://user-images.githubusercontent.com/118668727/237000950-b93d4ebe-8bd0-4398-a0ae-d3218c69200f.png)
# CORRESSION

![image](https://user-images.githubusercontent.com/118668727/237001017-bb667a45-4a68-49e7-941c-33213b05d551.png)
# HEATMAP()
![image](https://user-images.githubusercontent.com/118668727/237001072-ac23259b-a779-4a9a-b304-2114becccefc.png)
# RESULT
Hence The Performance of the Multivariate EDA on the given data set is verified.
