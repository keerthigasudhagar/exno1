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
##Data cleaning process:##
```
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![363189923-93401c95-bb10-41fd-879e-4969a5f7ee4f](https://github.com/user-attachments/assets/4d60b2ad-01f4-4181-8c4d-4b892c2a8c6d)
```
df.head()
```
![363190130-1a447fe0-a978-4c92-87b7-a98c6c1d7d84](https://github.com/user-attachments/assets/9b24144a-c98a-43a3-83a0-df593e0f9143)
```
df.tail(5)
```
![363190267-5cda549c-de93-45b7-ba82-b7f5f5e686af](https://github.com/user-attachments/assets/66195699-bbf8-44bd-ad5d-b052b5152d8a)
```
df.isnull()
```
![363190427-77005ab8-affc-49a0-94bb-e85103cdba08](https://github.com/user-attachments/assets/b4a47b9e-c16a-45fc-b62b-9eba366a2d28)
```
df.notnull()
```
![363190737-01585993-3e36-4f64-b635-bec23b09a13a](https://github.com/user-attachments/assets/056defe9-a7b7-468e-93c4-472409721d8d)
```
df.dropna(axis=0)
```
![363190930-2f67b824-36bd-4f8b-9b45-e101d99f273c](https://github.com/user-attachments/assets/0f4d5f5a-31ef-4763-9a9a-876a444ae543)
```
df.dropna(axis=1)
```![363191042-6a6d8a81-5109-4079-aa55-9de0774f7a66](https://github.com/user-attachments/assets/dc3e6de2-d4b5-4610-b97a-6c94b9acf687)

# Result
          <<include your Result here>>
