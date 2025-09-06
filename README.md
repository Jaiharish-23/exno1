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
DONE BY JAI HARISH R
REG NO: 212224040124
```            
```
import numpy as np
import pandas as pd
df = pd.read_csv("SAMPLEIDS.csv")
df
```
<img width="1275" height="864" alt="image" src="https://github.com/user-attachments/assets/51ff2dd3-fc52-42de-a3d4-70da87485b49" />


```
df.head()
```
<img width="1040" height="252" alt="image" src="https://github.com/user-attachments/assets/5015c2d9-6859-4e07-8b74-07e83f31a643" />


```
df.tail()
```
<img width="1083" height="276" alt="image" src="https://github.com/user-attachments/assets/0534bf8c-d397-4b5d-8ce1-6d75603da2b7" />


```
df.isnull()
```
<img width="1023" height="856" alt="image" src="https://github.com/user-attachments/assets/264f2e09-58c9-4f71-a0c5-01c8fab061cc" />


```
df.isnull().sum()
```
<img width="336" height="584" alt="image" src="https://github.com/user-attachments/assets/1b4ef06f-e6e8-4c1d-b3e6-a870a0b93b66" />


```
df.isnull().any()
```
<img width="405" height="572" alt="image" src="https://github.com/user-attachments/assets/77237597-b6d0-4783-b1fa-195d664619d8" />


```
df.dropna()
```
<img width="1194" height="568" alt="image" src="https://github.com/user-attachments/assets/cf83006a-ff73-46a1-8010-9caec92d0a2a" />


```
df.fillna(5)
```
<img width="1227" height="852" alt="image" src="https://github.com/user-attachments/assets/dc581e48-5bf9-4e47-8c3a-c56c36f84fc8" />


```

df.fillna(method = 'bfill')
```
<img width="1110" height="844" alt="image" src="https://github.com/user-attachments/assets/7bed128e-dce3-4546-945c-baf911318734" />


```
df.fillna({'GENDER': 'MALE','NAME':'RAM','TOTAL':602.5,'AVG':108.057777})
```
<img width="1149" height="861" alt="image" src="https://github.com/user-attachments/assets/f72708da-586a-43dc-b2e6-302dd8b8d8c8" />


```
ir = pd.read_csv('iris.csv')
ir
```
<img width="812" height="488" alt="image" src="https://github.com/user-attachments/assets/14f854fe-29b9-4fe4-84ee-703260fc3675" />


```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
<img width="899" height="590" alt="image" src="https://github.com/user-attachments/assets/418737f6-5c91-400c-a125-20d402c91edb" />


```
q1 = ir.sepal_width.quantile(0.25)
q3 = ir.sepal_width.quantile(0.75)
iqr = q3 - q1
print(iqr)
```
<img width="286" height="56" alt="image" src="https://github.com/user-attachments/assets/2d86f208-654a-4561-9168-5d246d9e6b6c" />


```
new=df1[(ir.sepal_width>(q1-1.5*iqr))& (ir.sepal_width<(q3+1.5*iqr))]
new
```
<img width="853" height="510" alt="image" src="https://github.com/user-attachments/assets/a1bf2f66-4845-4d93-a05a-ef29c231da0a" />


```
sns.boxplot(x='sepal_width',data=delid)
```
<img width="842" height="608" alt="image" src="https://github.com/user-attachments/assets/5166bd1e-4478-4d87-b454-bb59971cd9e5" />


```
import numpy as np
import scipy.stats as stats
z = np.abs(stats.zscore(ir['sepal_width']))
df1 = ir[z<3]
df1
```
<img width="935" height="486" alt="image" src="https://github.com/user-attachments/assets/1eb550e8-5640-4bba-b4b5-f3fc758f61c3" />


# Result
Thus to read the given data and perform data cleaning and save the cleaned data to a file done successfully.


