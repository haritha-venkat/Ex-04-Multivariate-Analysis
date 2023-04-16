# Ex-04-Multivariate-Analysis
## AIM

To perform Multivariate EDA on the given data set.
## Explanation

Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
## ALGORITHM
### STEP 1:

Import the built libraries required to perform EDA and outlier removal.
### STEP 2:

Read the given csv file
### STEP 3:

Convert the file into a dataframe and get information of the data.
### STEP 4:

Return the objects containing counts of unique values using (value_counts()).
### STEP 5:

Plot the counts in the form of Histogram or Bar Graph.
### STEP 6:

Use seaborn the bar graph comparison of data can be viewed.
### STEP 7:

Find the pairwise correlation of all columns in the dataframe.corr()
### STEP 8:

Save the final data set into the file
## CODE:

/*Name : harithashree.V
Register Number : 212222230046*/
```python
import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt
df = pd.read_csv("/content/SuperStore.csv")
df.head(10)
df.info()
df.describe()
df.isnull().sum()
df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()
df.dtypes
sbn.scatterplot(df['Postal Code'],df['Sales'])
states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()
states=df.loc[:,["State","Postal Code"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")
plt.figure(figsize=(17,7))
sbn.barplot(x=states.index,y="Postal Code",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("Postal Code")
plt.show()
states=df.loc[:,["Segment","Sales"]]
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")
#plt.figure(figsize=(10,7))
sbn.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()
sbn.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])
df.corr()
sbn.heatmap(df.corr(),annot=True)
```
# OUTPUT:
## EDA - SuperStore.csv
![image](https://user-images.githubusercontent.com/121285701/232273640-62923b9b-12e9-44de-a8ae-1c8968bcc798.png)
## Displaying information about Dataset
![image](https://user-images.githubusercontent.com/121285701/232273665-682697c5-4820-404a-8a54-57b475b05151.png)
## Checking the null values and Cleaning it
![image](https://user-images.githubusercontent.com/121285701/232273676-8b61c831-566d-4cf8-bb1d-77f679d7ae73.png)
## Displaying datatypes of each features
![image](https://user-images.githubusercontent.com/121285701/232273711-63cdb3a0-8532-4373-97e4-8030c5fe288b.png)
## Multivariate Analysis - Scatterplot
![image](https://user-images.githubusercontent.com/121285701/232273752-aaf5d117-d19c-420a-890d-df41305b12cd.png)
## Multivariate Analysis - Barplot
![image](https://user-images.githubusercontent.com/121285701/232273764-8d5d662b-04d7-428b-b2b7-8912dc5870cc.png)

![image](https://user-images.githubusercontent.com/121285701/232273767-4ef1e517-67c2-4a0f-91a4-fd3762e91cab.png)
![image](https://user-images.githubusercontent.com/121285701/232273772-6069f250-b1ee-4820-a05f-c318e7d9ac10.png)
## Correlation Coefficient Interpretation using HeatMap
![image](https://user-images.githubusercontent.com/121285701/232273785-1bfb7859-30d1-425c-a08f-8fd700871253.png)

# RESULT:
Thus the program to perform EDA on the given data set is successfully executed.
