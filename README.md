#EX.NO:1
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
data=pd.read_csv("Data_set.csv")
data
```
<img width="1309" height="517" alt="image" src="https://github.com/user-attachments/assets/bdd0d8fd-fb13-42e6-a01f-bb68fa11e65e" />
```
data.head(4)
```
<img width="1325" height="205" alt="image" src="https://github.com/user-attachments/assets/88375b8f-2699-420d-9891-d10c84c0da80" />
```
data.tail(9)
```
<img width="1341" height="397" alt="image" src="https://github.com/user-attachments/assets/354eb280-2263-4db5-9496-ac5f5c131ea6" />
```
data.isnull()
```
<img width="1278" height="504" alt="image" src="https://github.com/user-attachments/assets/30e9d86f-0a12-444c-8018-4842e9be991f" />
```
data.notnull()
```
<img width="1224" height="506" alt="image" src="https://github.com/user-attachments/assets/01bb4979-b077-45ef-90a0-f249e769f847" />
```
data.isnull().sum()
```
<img width="758" height="226" alt="image" src="https://github.com/user-attachments/assets/0ed42372-fea7-4f93-897a-d71b5e72d81f" />
```
data.dropna(axis=1)
```
<img width="526" height="514" alt="image" src="https://github.com/user-attachments/assets/a83ceb6e-5a43-405c-8246-54b724bcccc4" />
```
data.dropna(axis=0)
```
<img width="1379" height="519" alt="image" src="https://github.com/user-attachments/assets/cedd1a08-c139-4a2c-a6a4-325f39cfd392" />
```
data.fillna(0)
```
<img width="1377" height="523" alt="image" src="https://github.com/user-attachments/assets/150f05dd-7d70-4ff4-96c3-4b33ef92cb97" />
```
data.ffill()
```
<img width="1363" height="521" alt="image" src="https://github.com/user-attachments/assets/32896049-df73-4335-bb41-152f2f7db0dc" />
```
data.bfill()
```
<img width="1328" height="516" alt="image" src="https://github.com/user-attachments/assets/2eccbc0f-4731-4c1a-83fe-4f5278b1162e" />
```
data.fillna({'rating':0,'country':'South Korea'})
```
<img width="1368" height="509" alt="image" src="https://github.com/user-attachments/assets/ab49ae24-f3c2-46f6-84f2-a7d2796263cb" />
```
ir=pd.read_csv("Data_set.csv")
ir
```
<img width="1384" height="517" alt="image" src="https://github.com/user-attachments/assets/908db4a6-88da-498b-b750-9f6754eb1cc4" />
```
ir.head()
```
<img width="1385" height="232" alt="image" src="https://github.com/user-attachments/assets/afdccc75-6b44-4525-b31c-f0d2c8ff04f4" />
```
ir.tail()
```
<img width="1334" height="240" alt="image" src="https://github.com/user-attachments/assets/913914ae-f213-4e05-b1ef-8bdb4899f708" />
```
ir.info()
```
<img width="544" height="344" alt="image" src="https://github.com/user-attachments/assets/bed8def2-4c3e-4993-b75f-66a33961f197" />
```
ir.describe()
```
<img width="1082" height="347" alt="image" src="https://github.com/user-attachments/assets/024773f5-64aa-491f-a04e-548d803370e3" />
```
ir.isnull().sum()
```
<img width="316" height="220" alt="image" src="https://github.com/user-attachments/assets/3a70d26d-9d7f-42a1-a3bc-26fe37fe5890" />
```
ir.isnull().any()
```
<img width="488" height="227" alt="image" src="https://github.com/user-attachments/assets/be6c351b-9c47-490f-878d-b4dbee405490" />
```
ir.notnull()
```
<img width="1318" height="518" alt="image" src="https://github.com/user-attachments/assets/672ed2ae-33ae-4d07-abf1-d64282ef1ed2" />
```
ir.dropna()
```
<img width="1377" height="511" alt="image" src="https://github.com/user-attachments/assets/c79d439c-f7f2-406e-a1d6-ce8a3f553d8e" />
```
ir.dropna(axis=1)
```
<img width="540" height="498" alt="image" src="https://github.com/user-attachments/assets/ce3cbf14-f15d-48c1-943e-d03f5c133b62" />
```
ir.fillna(8)
```
<img width="1361" height="519" alt="image" src="https://github.com/user-attachments/assets/657b2816-58e4-4613-829e-8d6587aaf719" />
```
ir.fillna(method='ffill')
```
<img width="1352" height="521" alt="image" src="https://github.com/user-attachments/assets/f27757d1-4174-46f3-bf1e-ff3c9c3c8c00" />
```
ir.fillna(method='bfill')
```
<img width="1388" height="497" alt="image" src="https://github.com/user-attachments/assets/83ac83c2-89e7-4fe8-925d-a1cd2f3b291c" />
```
import seaborn as sns
sns.boxplot(x='num_episodes',data=ir)
```
<img width="806" height="575" alt="image" src="https://github.com/user-attachments/assets/222b7858-abca-40c9-bb94-1f3e991a4be0" />
```
Q1=ir.num_episodes.quantile(0.25)
Q3=ir.num_episodes.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```
<img width="122" height="33" alt="image" src="https://github.com/user-attachments/assets/bba62868-365c-4ea6-84a8-a956255ad2b2" />
```

```
# Result
          <<include your Result here>>
