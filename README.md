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
import pandas as pd
import numpy as np
import seaborn as sns
```
```
df=pd.read_csv("C:\\Users\\priya\\Downloads\\Data_set.csv")
df
```
![image](https://github.com/user-attachments/assets/d3bba7b0-548c-4253-b070-d749a7a6ad71)
```
df.info()
```
![image](https://github.com/user-attachments/assets/18c9ad5b-7f72-45b5-a1df-f77885cffe9e)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/0fbff716-1346-4eb0-8e4c-5ddba28fb605)
```
df.head()
```
![image](https://github.com/user-attachments/assets/fe823d82-6d35-453d-9857-d3d697dc7bdf)
```
df.tail()
```
![image](https://github.com/user-attachments/assets/f6abd0a1-ed8b-436c-a293-e0dd612dc771)
```
df.tail(8)
```
![image](https://github.com/user-attachments/assets/258767c1-1830-4a1b-8db5-d10d3c648a1b)
```
df.isnull()
```
![image](https://github.com/user-attachments/assets/40747b7e-2ef9-43ce-864f-d10a5cd2d49f)
```
df.notnull()
```
![image](https://github.com/user-attachments/assets/66653996-81a3-42c0-a0ac-738f1ff8e11e)
```
df.dropna(axis=0)
```
![image](https://github.com/user-attachments/assets/b4124759-d448-4fc0-9e68-385900c6abaf)
```
df.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/5e6ddd6c-1d79-4f10-93f3-52320fc1d5bf)
```
df[df['num_episodes']>20]
```
![image](https://github.com/user-attachments/assets/e08d6975-58c3-4728-b40d-9abfb3ca243d)
```
df.iloc[:3]
```
![image](https://github.com/user-attachments/assets/101b5296-ae5d-4b90-8bf0-f6b35b45946e)
```
df.iloc[:3,3:]
```
![image](https://github.com/user-attachments/assets/70d05f3c-b218-48f1-a95a-43c190128b06)
```
df.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/473f2d72-b2e9-4700-b092-d06a365ed122)
```
df.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/b34a576b-4859-4be8-ba8c-d663dcc46dbb)
```
df.iloc[[1,2,3],[1,3,5]]
```
![image](https://github.com/user-attachments/assets/2ddc0002-e3e9-496f-ae9c-c758c533af08)
```
df.fillna(df['rating'].mean())
```
![image](https://github.com/user-attachments/assets/4a2ecd1a-2cc9-4a33-9d7e-93885a7c0cff)
```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/361d10ac-0e7d-4eb5-bed3-7e5f1e5947d0)
```
df.notnull().any()
```
![image](https://github.com/user-attachments/assets/3bc27f55-c0dd-486e-8bdd-0a856bc714f9)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/3be87944-d63d-4418-a344-9a59a50ffb0c)
```
df.interpolate()
```
![image](https://github.com/user-attachments/assets/d08b2f5c-bdcd-4930-aacd-0a0cdb257178)
```
df.shape
```
![image](https://github.com/user-attachments/assets/4d098ce4-0735-411d-8417-983a4a64f5d3)
```
import pandas as pd
import numpy as np
import seaborn as sns
df=pd.read_csv("SAMPLEIDS.csv")
df
````
![image](https://github.com/user-attachments/assets/d12f5b60-5c6f-4b63-9d1c-5580e4c1a16c)
```
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/7b0f0250-9d05-45c7-b9b4-88b059e417a4)
```
df.dropna(inplace=True)
```
```
sns.heatmap(df.isnull(),yticklabels=False,annot=True)
```
![image](https://github.com/user-attachments/assets/9fd41f1b-bae0-4c2e-a03e-076f21277701)
```
import pandas as pd 
import seaborn as sns
import numpy as np
```
```
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/user-attachments/assets/c19ec73f-21cf-4b12-b0b9-866268fce30f)
```
sns.scatterplot(data=af)
```
![image](https://github.com/user-attachments/assets/91a8c4b8-74e9-4e70-b69c-e3e0669111b0)
```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/934115f3-51bf-4eee-9844-b272cc1abcf0)
```
Q1=np.percentile(af,25)
Q3=np.percentile(af,75)
IQR=Q3-Q1
IQR
```
![image](https://github.com/user-attachments/assets/e8589ac4-399a-45c5-9077-64e9b50d9e3a)
```
lower_bound=Q1-1.5*IQR
upper_bound=Q3+1.5*IQR
```
```
outliers=[x for x in age if x<lower_bound or x>upper_bound]
```
```
print("Q1: ",Q1)
print("Q3: ",Q3)
print("IQR: ",IQR)
print("Lower_bound: ",lower_bound)
print("Upper_bound: ",upper_bound)
print("Outliers: ",outliers)
```
![image](https://github.com/user-attachments/assets/8b275712-3047-4492-98cc-b670beaa401b)
```
sns.scatterplot(data=af)
```
![image](https://github.com/user-attachments/assets/72700b7e-7367-499b-a071-a54e1aa7f070)
```
import pandas as pd 
import numpy as np
import seaborn as sns
from scipy import stats
```
```
data={'weight':[12,15,18,21,24,27,30,33,36,39,42,45,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![image](https://github.com/user-attachments/assets/66b901a0-c771-4a73-adf4-529259bf0be0)
```
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/user-attachments/assets/beb8c785-a386-4b39-8428-3d0bcd37203a)
```
print(df[z['weight']>3])
```
![image](https://github.com/user-attachments/assets/ab03eefa-2a7e-4eef-82a0-31507896674b)
```
import numpy as np
val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,202,72,75,78,81,84,232,87,90,93,96,99,258]
```
```
#zscore implementation without stats method
out=[]
def d_o(val):
    ts=3
    m=np.mean(val)
    sd=np.std(val)
    for i in val:
        z=(i-m)/sd
        if np.abs(z)>ts:
            out.append(i)
    return out 
            
```
```
op= d_o(val)
```
```
op
```

![image](https://github.com/user-attachments/assets/33715118-a574-4357-bfc9-cafbc167349c)

       



# Result
Thus we have read and cleaned the data and also removed the outliers by detection using IQR and Z-score method.

