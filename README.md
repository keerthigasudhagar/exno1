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
## Data cleaning process:
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![359429919-4527d27f-ce48-44cb-b8ce-34bbd266e130](https://github.com/user-attachments/assets/22b1c5d1-3170-4bc7-a838-4243e477c798)
```
df.head()
```
   ![359430246-75445d50-f356-4172-a260-7744a4b8a5d0](https://github.com/user-attachments/assets/5fcb8d9c-2ad3-487f-83f2-7dc2b4f0e4f1)
```
df.tail(5)
```
![359430844-0aad2483-f1d4-4161-8819-6dd578b6c0b7](https://github.com/user-attachments/assets/b81b1a90-d938-4bca-81c7-cb8d30919392)
```
df.isnull()
```
![359431245-e3ad59dc-d554-42fa-ab22-1a0b8dccd19a](https://github.com/user-attachments/assets/e769dd46-635a-41af-8995-854ef043f98f)
```
df.notnull()
```
![359431612-cab8a38c-0423-4657-8487-85a5b7cc4d9d](https://github.com/user-attachments/assets/d693cbeb-2318-41e8-a654-ec675e6ff77b)
```
df.dropna(axis=0)
```
![359432233-6848d1b2-2b91-4d7b-aae2-89f3d5ebbd83](https://github.com/user-attachments/assets/d8a2198f-5c2e-4976-971b-7e4281688941)
```
df.dropna(axis=1)
```
![359432527-551c2074-915a-4d95-8596-fbc85c7d3a34](https://github.com/user-attachments/assets/7d626239-dc8d-47be-9152-e0730280b27a)
```
df.fillna(0)
```
![359432819-d79561f9-7a81-4137-bd4e-1f44c82ca40c](https://github.com/user-attachments/assets/5b8c4afb-af97-4c08-b9a0-5535447474b9)
```
print(df.shape)
```
## IQR:
```
import pandas as pd
import seaborn as sns
ir=pd.read_csv('/content/iris.csv')
ir
```
![359434303-5f92ae1d-167b-4412-8e99-312c878199d7](https://github.com/user-attachments/assets/9f756ab5-99fb-4ee0-b901-98e3faa5dc4e)
```
ir.describe()
```
![359434586-cc69d12e-9f65-4b57-a506-b8f9194f2749](https://github.com/user-attachments/assets/0efd5bbb-f487-4f32-81c6-964bc2b4480f)
```
sns.boxplot(x='sepal_width',data=ir)
```
![359434907-7c8b93dc-1649-4b07-bf99-39ce4448edeb](https://github.com/user-attachments/assets/11205cfd-0f7e-43e8-ba3b-1b0f7985c8be)
```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![359435513-4d29e256-9386-4ea4-82a6-02e0f5175f3c](https://github.com/user-attachments/assets/fe9f953d-66d0-4b01-9020-82875fb68997)
```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![359435755-b5da97d6-af4b-4690-b448-c1ff0697ea18](https://github.com/user-attachments/assets/e50a18fd-094e-4ba5-87fe-6687c038dac0)
```
sns.boxplot(x='sepal_width',data=delid)
```
![359436022-1fb5cdcf-87ba-4631-b643-d2aeb0b2f8a2](https://github.com/user-attachments/assets/abfd7644-11dc-4020-b923-ec8262e44086)
## Z SQUARE
```
import matplotlib.pyplot as plt
import pandas as pd
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/content/heights.csv")
dataset
```
![359436930-2f2868d2-4002-4f47-82c4-8c0ad8a19392](https://github.com/user-attachments/assets/ef4e6927-a454-40e0-957f-d648126ef38d)
```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```
![359437229-2dae9f2a-a47a-4249-90a6-159aea236d8d](https://github.com/user-attachments/assets/dc6be9b3-804e-4cb7-922a-d282f5fa3a68)
```
low = q1 - 1.5*iqr
low
```
![359437858-68c83441-a0b3-4821-96c4-8113ec2d0abb](https://github.com/user-attachments/assets/3fce62dc-99d9-4e8f-bbba-741eb1469a59)
```
high = q3 + 1.5*iqr
high
```
![359438348-734158d2-fc68-4f4b-b315-b58ff808ae2c](https://github.com/user-attachments/assets/750980c2-6222-4548-ba9a-600959df7092)
```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![359438726-c6f95d8a-8a60-48bf-9fc0-3bb251eeabec](https://github.com/user-attachments/assets/d212a314-e736-45e2-b4aa-d45333032664)
```
z = np.abs(stats.zscore(df['height']))
z
```
![359439236-0f13eb15-f41a-4de2-b43a-47c5062c495b](https://github.com/user-attachments/assets/9798f381-b2e5-4cd5-8664-2736b3c4f08a)
```
 df1 = df[z<3]
 df1
```
![359439595-2c5a2fc4-cbec-4311-bf01-d85c236ecef3](https://github.com/user-attachments/assets/9ce729aa-5997-43f2-b3d2-8ffeef4b159d)

# Result
      Thus the Data Cleaning Process and Detecting and Removal of Outliers is executed successfully.
