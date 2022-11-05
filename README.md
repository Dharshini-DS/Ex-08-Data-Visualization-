# Ex-07-Data-Visualization-

## AIM
To Perform Data Visualization on the given dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
Name: Dharshini D.S
Register number: 212221230022
```
```
#Reading the given dataset
import pandas as pd
df=pd.read_csv("Superstore.csv",encoding='unicode_escape')
df.head()
#Data Visualization using Seaborn
import seaborn as sns
from matplotlib import pyplot as plt
#1.Line Plot
plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')
#2.Scatterplot
sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)
#3.Boxplot
sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)
#4.Violin Plot
sns.violinplot(x="Profit",data=df)
#5.Barplot
sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)
#6.Pointplot
sns.pointplot(x=df["Quantity"],y=df["Discount"])
#7.Count plot
sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)
#8.Histogram
sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')
#9.KDE Plot
sns.kdeplot(x="Profit", data = df,hue='Category')
#Data Visualization Using MatPlotlib
#1.Plot
plt.plot(df['Category'], df['Sales'])
plt.show()
#2.Heatmap
df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)
#3.Piechart
df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()
df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()
#4.Histogram
plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()
#5.Bargraph
plt.bar(df.index,df['Category'])
plt.show()
#6.Scatterplot
OUPUT
Reading the given dataset
## Data Visualization Using Seaborn: ### 1.Line Plot
plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()
#7.Boxplot
plt.boxplot(x="Sales",data=df)
plt.show()
```
# OUPUT
## Reading the given dataset
<img width="595" alt="d1" src="https://user-images.githubusercontent.com/93427345/200100583-c061cccd-80d7-45bd-a21e-832bec8c604d.png">

## Data Visualization Using Seaborn: 
### 1.Line Plot
<img width="336" alt="2d" src="https://user-images.githubusercontent.com/93427345/200100589-db6a3821-dc6f-4290-b405-e26c956aff23.png">

<img width="314" alt="3" src="https://user-images.githubusercontent.com/93427345/200100592-af8f1900-fb5d-415f-bbe6-4087ec6e413b.png">

<img width="258" alt="4" src="https://user-images.githubusercontent.com/93427345/200100613-2c30b4c1-0961-47e0-9bd1-c67ff09216d8.png">

### 2.Scatterplot
<img width="293" alt="5" src="https://user-images.githubusercontent.com/93427345/200100620-d0c546de-cfca-4970-bcd8-a7eb6a6205d3.png">

<img width="284" alt="6" src="https://user-images.githubusercontent.com/93427345/200100635-33756e5b-6086-404f-b72c-5f9a98e13bdb.png">

<img width="408" alt="7" src="https://user-images.githubusercontent.com/93427345/200100645-9f6ab487-6331-4253-be7b-814c9948ef89.png">

### 3.Boxplot
<img width="252" alt="8" src="https://user-images.githubusercontent.com/93427345/200100656-bc08abee-cf88-47c5-a155-425624a5a3bb.png">

<img width="283" alt="9" src="https://user-images.githubusercontent.com/93427345/200100667-541ff07a-fc75-4fc0-936f-27b926d1a8af.png">

### 4.Violin Plot
<img width="229" alt="s1" src="https://user-images.githubusercontent.com/93427345/200100762-6c09c869-6c7f-429b-a0cd-ffd64dda7554.png">

### 5.Barplot
<img width="362" alt="s2" src="https://user-images.githubusercontent.com/93427345/200100858-a20f42ea-1cce-42f1-a970-d049f819422a.png">

<img width="248" alt="s3" src="https://user-images.githubusercontent.com/93427345/200100948-98980a44-838f-4686-ad20-7d0465c4785d.png">

### 6.Pointplot
<img width="258" alt="s4" src="https://user-images.githubusercontent.com/93427345/200101058-d5c3bce7-6981-4e0f-acb6-cc0074f86667.png">

### 7.Count plot
<img width="267" alt="s5" src="https://user-images.githubusercontent.com/93427345/200101076-0e904050-36f2-4290-8cad-750c0f221e91.png">

<img width="258" alt="s6" src="https://user-images.githubusercontent.com/93427345/200101082-43c21474-2476-4a35-a893-77592c07052f.png">

### 8.Histogram
<img width="281" alt="s7" src="https://user-images.githubusercontent.com/93427345/200101106-5426b3ab-afb6-4b96-9f20-a916ddc794b4.png">

### 9.KDE Plot
<img width="252" alt="s8" src="https://user-images.githubusercontent.com/93427345/200101118-c31c202d-5bd5-488a-959e-a7002c53e509.png">

## Data Visualization Using Matplotlib:
### 1.Plot
<img width="268" alt="s9" src="https://user-images.githubusercontent.com/93427345/200101130-1b6f3888-2da1-4b41-9b81-8c97d25c2167.png">

### 2.Heatmap
<img width="381" alt="s10" src="https://user-images.githubusercontent.com/93427345/200101138-62cf6fcd-8d1b-4df5-8240-23a286f1c49a.png">

### 3.Piechart
<img width="168" alt="ds1" src="https://user-images.githubusercontent.com/93427345/200101206-f9d598a1-20be-4754-a0fb-4b88292e15c0.png">

<img width="288" alt="ds2" src="https://user-images.githubusercontent.com/93427345/200101224-18ed3b41-94a2-4e7b-ba0c-51b56e1263cc.png">

### 4.Histogram
<img width="245" alt="ds3" src="https://user-images.githubusercontent.com/93427345/200101234-330258e8-1eb4-44ee-9e6b-7cd3303eae5c.png">

### 5.Bargraph
<img width="279" alt="ds4" src="https://user-images.githubusercontent.com/93427345/200101243-03798c42-4324-4821-93a0-96598ae8023a.png">

### 6.Scatterplot
<img width="248" alt="ds5" src="https://user-images.githubusercontent.com/93427345/200101251-baceab8b-a91f-4409-b6a9-b5b16b3c9b66.png">

### 7.Boxplot
<img width="261" alt="ds6" src="https://user-images.githubusercontent.com/93427345/200101270-0e0f80e3-3bad-4e35-a8d5-4d03d04f4433.png">

# RESULT
Hence,Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
