# Ex-04-Multivariate-Analysis
#AIM
To perform Multivariate Exploratory Data Analysis on the given data set.

#EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

#ALGORITHM
#STEP 1:
Import the built libraries required to perform EDA and outlier removal.

#STEP 2:
Read the given csv file

#STEP 3:
Convert the file into a dataframe and get information of the data.

#STEP 4:
Return the objects containing counts of unique values using (value_counts()).

#STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

#STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

#STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

#STEP 8:
Save the final data set into the file

#CODE
```
# program developed by : kavya k
# reg no : 212222230065
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot SZ
data=pd.read_csv("SuperStore.csv")
data
data.head()

data.info()
data.describe()
data.tail()
data.shape
data.columns
data.isnull().sum()
data.duplicated()
data['Postal Code'] = data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

states=data.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

states=data.loc[:,["State","Postal Code"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Postal Code",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES") 
plt.ylabel=("Postal Code") 
plt.show()

states=data.loc[:,["Segment","Sales"]]
states=data.groupby(by=["Segment"]).sum()
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()

sns.barplot(x="Ship Mode",y="Sales",hue=data["Category"],data=data)

data.corr()
sns.heatmap(data.corr(),annot=True)
plt.figure(figsize=(10,7))
sns.scatterplot(x='Sub-Category', y='Sales', hue=data['Ship Mode'],data=data)
plt.xticks(rotation = 90)
```
#OUTPUT:
DATASET:

![image](https://user-images.githubusercontent.com/118668727/232685364-1a939973-ff09-44bf-9575-c73b8e05ec4e.png)

INFO:

![image](https://user-images.githubusercontent.com/118668727/232685541-cbc80655-a639-41af-b6b1-3b2c17da1fd5.png)

DESCRIBE:

![image](https://user-images.githubusercontent.com/118668727/232685658-505c5dda-bb7f-459c-823c-abeb083eeffb.png)

TAIL:

![image](https://user-images.githubusercontent.com/118668727/232685711-d12232cc-eb41-4b20-861f-98bb4b8a8b99.png)

SHAPE:

![image](https://user-images.githubusercontent.com/118668727/232686207-e1e44ecf-9506-4ab8-9335-2fdd3a56f550.png)

COLUMNS:

![image](https://user-images.githubusercontent.com/118668727/232686232-cbd067f1-617b-4785-bddf-3c301b5698a4.png)

NULL SUM:

![image](https://user-images.githubusercontent.com/118668727/232686259-80bc4bf0-7a93-482d-9a7c-667e2eceb561.png)
DUPLICATED:

![image](https://user-images.githubusercontent.com/118668727/232686288-dbc0b229-6971-4c1c-a3b5-928b308fea3f.png)

POST CLEANING:

![image](https://user-images.githubusercontent.com/118668727/232686333-f6fd28e5-dc3d-4472-a389-3a1cb27d13be.png)

BAR PLOT (STATES AND SALES):

![image](https://user-images.githubusercontent.com/118668727/232686367-ccce58d0-4b44-49f7-bdea-8a56ae48e9d2.png)

BAR PLOT (STATES AND POSTAL CODE):

![image](https://user-images.githubusercontent.com/118668727/232686398-c7c8603c-42a3-4c18-a794-cecb91a90ea3.png)

BAR PLOT (SALES AND SEGMENT):

![image](https://user-images.githubusercontent.com/118668727/232686062-cfdb6dfa-283b-4487-a8bf-d5368af81a84.png)

BAR PLOT (Ship Mode & Category vs Sales):

![image](https://user-images.githubusercontent.com/118668727/232686037-2b5cad3b-b627-4ebf-8b62-81ed95868437.png)

Correlation coefficient:

![image](https://user-images.githubusercontent.com/118668727/232686012-d21e4a4d-7af7-4ca6-9f75-9ba1db1e4cf3.png)

Heatmap:

![image](https://user-images.githubusercontent.com/118668727/232685983-358c2e63-68d6-4f00-bd56-070d820f6dc5.png)

SCATTER PLOT:

![image](https://user-images.githubusercontent.com/118668727/232685959-cc7ec084-794d-45c6-adca-f7dea9d31007.png)

RESULT:
Thus the program to perform EDA on the given data set is successfully executed.
