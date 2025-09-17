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
```
import numpy as np
import pandas as pd
data=pd.read_csv("SAMPLEIDS.csv")
data
```
<img width="1414" height="807" alt="Screenshot 2025-09-17 154407" src="https://github.com/user-attachments/assets/546e28c3-2f08-4d37-bb4c-87a5714646a4" />

```
data.head(4)
```
<img width="1382" height="237" alt="image" src="https://github.com/user-attachments/assets/c90a056e-60ae-4636-89ce-66ecddcf640d" />

```
 data.tail(7)
```           
<img width="1376" height="335" alt="image" src="https://github.com/user-attachments/assets/6d055069-c419-459d-b381-74157b0e9b6c" />

```
data.isnull()
```
<img width="1382" height="782" alt="image" src="https://github.com/user-attachments/assets/eb89266c-9fb3-4919-9d6a-614905b31a99" />

```
 data.notnull()
```
<img width="1373" height="784" alt="image" src="https://github.com/user-attachments/assets/df24b5a2-330f-4988-8266-45d36568245b" />

```
data.isnull().sum()
```
<img width="1376" height="339" alt="image" src="https://github.com/user-attachments/assets/24ac5caf-1b1c-43b7-9b23-f0a1e3ccacc1" />

```
data.isnull().any()
```
<img width="1382" height="339" alt="image" src="https://github.com/user-attachments/assets/9ea42ec5-2b8b-407e-b715-9ad5e4854577" />

```
data.dropna(axis=1)
```
<img width="1373" height="779" alt="image" src="https://github.com/user-attachments/assets/8a7b1fdd-e2c7-4754-b1eb-13dbd79f7466" />

```
data.dropna(axis=0)
```
<img width="1381" height="524" alt="image" src="https://github.com/user-attachments/assets/08ab1d1d-81dd-44d7-9cfe-d07a5a573899" />

```
data.fillna(0)
```
<img width="1382" height="783" alt="image" src="https://github.com/user-attachments/assets/9acbea9d-594e-4a40-baa1-4f162518c372" />

```
data.bfill()
```
<img width="1376" height="780" alt="image" src="https://github.com/user-attachments/assets/ca68518c-5218-4d2f-9c07-6a2b4f4ba696" />

```
data.fillna({'REGNO':0, 'NAME':'PRAVEEN'})
```
<img width="1379" height="778" alt="image" src="https://github.com/user-attachments/assets/cc4a2c71-1b2e-4205-8025-55677e484257" />

```
ir=pd.read_csv("iris.csv")
ir
```
<img width="1399" height="526" alt="image" src="https://github.com/user-attachments/assets/f86f927d-f6c6-44a2-a2c1-973606e14ecf" />

```
ir.describe()
```
<img width="1372" height="366" alt="image" src="https://github.com/user-attachments/assets/253d6ea6-af65-4415-8945-faa09d51d08a" />

```
import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)
```
<img width="1380" height="659" alt="image" src="https://github.com/user-attachments/assets/d3f4d523-53e7-4cc2-90a8-ed17873ee235" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```
<img width="1379" height="151" alt="image" src="https://github.com/user-attachments/assets/42906448-97f1-479d-9046-40c5c6eb2883" />

```
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="1375" height="186" alt="image" src="https://github.com/user-attachments/assets/fee26582-0536-4a6e-93aa-70b517b678e4" />

```
rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
```
<img width="1372" height="522" alt="image" src="https://github.com/user-attachments/assets/c0c8a28d-ce20-4a7e-9499-7b8df74a03ef" />

```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z
```
<img width="1378" height="380" alt="image" src="https://github.com/user-attachments/assets/3e24b43d-311a-4b0e-820b-5066fa073f86" />


# Result

Thus the programs are executed successfully
