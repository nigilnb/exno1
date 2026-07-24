# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
import pandas as pd
df=pd.read_csv("/contentSAMPLEIDS.csv")
df
<img width="757" height="637" alt="image" src="https://github.com/user-attachments/assets/cc7f1635-3ffb-4066-8076-99362dac2e67" />
df.head()
<img width="739" height="175" alt="image" src="https://github.com/user-attachments/assets/eaef721b-f020-477f-963a-e3c90b2b2400" />
df.tail()
<img width="729" height="192" alt="image" src="https://github.com/user-attachments/assets/b5547902-42c5-406f-8977-ea2142fa4298" />
df.info()
<img width="432" height="473" alt="image" src="https://github.com/user-attachments/assets/480ab332-63b2-4cb7-ad1f-a6d3eeffa014" />
df.describe()
<img width="751" height="306" alt="image" src="https://github.com/user-attachments/assets/2af7ed7d-b2a8-4afe-8c2e-b0c6c49e6cdb" />
df.isnull().sum()
<img width="132" height="492" alt="image" src="https://github.com/user-attachments/assets/b8797c0a-96ba-4ca1-9bd0-ebe2ffc19472" />
df.isnull().any()
<img width="221" height="613" alt="image" src="https://github.com/user-attachments/assets/a6c01cd5-2f30-499a-85d3-eb941f78224c" />
df.dropna()
<img width="728" height="398" alt="image" src="https://github.com/user-attachments/assets/c589cbeb-f8d8-49f1-b07b-77811c35b502" />
df.fillna(0)
<img width="706" height="606" alt="image" src="https://github.com/user-attachments/assets/93c5acbf-5305-4f41-8e40-086fbe21766d" />
df.fillna(method='ffill')
<img width="480" height="365" alt="image" src="https://github.com/user-attachments/assets/42fa5318-a6df-4c35-b67d-c6f40da73126" />
df.fillna({'GENDER':'MALE','NAME':'SRI'})
<img width="684" height="585" alt="image" src="https://github.com/user-attachments/assets/e18096cc-f7ea-41b2-a39f-b177b8ecf0fa" />
ir=pd.read_csv("/content/iris.csv")
ir
<img width="718" height="541" alt="image" src="https://github.com/user-attachments/assets/76927b5d-51e7-442b-8d5c-5a42b92dba5e" />
ir.describe()
<img width="656" height="402" alt="image" src="https://github.com/user-attachments/assets/c7762ef5-b738-47ef-9c35-039fd5a9d4ca" />
import seaborn as sns
sns.boxplot(x-'sepal_width',data=ir)
<img width="675" height="572" alt="image" src="https://github.com/user-attachments/assets/9d0089d3-1d17-4e98-8d7b-c883a6143bba" />
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
<img width="58" height="34" alt="image" src="https://github.com/user-attachments/assets/84b45887-76a9-4032-b5a7-b04c8bb194a3" />
ran=ir[((ir.sepal_width<(Q!-1.5*IQR))|(ir.sepal_width>(Q3+1.5IQR)))]
ran['sepal_width]
<img width="227" height="272" alt="image" src="https://github.com/user-attachments/assets/4486c262-ef4e-4132-bff0-87fa140ddd71" />
ram=ir[~((ir.sepal_width<Q1-1.5*IQR))|(ir.sepal_width>)Q3+1.5*IQR)))]
ran['sepal_width]
<img width="218" height="618" alt="image" src="https://github.com/user-attachments/assets/2207d367-6600-428c-9591-103cc5ad6057" />
sns.boxplot(x='sepal_width',data=ran)
<img width="678" height="575" alt="image" src="https://github.com/user-attachments/assets/935b6a84-da2c-4394-ae6b-255802989515" />
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir['petal_length']))
z
<img width="682" height="689" alt="image" src="https://github.com/user-attachments/assets/4a6af8a1-ef58-4571-b7fe-86dc1bf17a7b" />
ir!=ir[z<3]
ir1
<img width="686" height="532" alt="image" src="https://github.com/user-attachments/assets/c1b3beaf-c886-4188-a564-b57aef218075" />

# Result
Thus the given data successfully performed data cleaning and saved the cleaned data to a file
