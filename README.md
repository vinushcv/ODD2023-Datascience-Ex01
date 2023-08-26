# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file

# CODE:
FOR LOAN.CSV:

```python
import pandas as pd
df=pd.read_csv("/Loan_data.csv")
print(df)
df.head(10)
df.info()
df['Loan_ID']=df['Loan_ID'].fillna(df['Dependents'].mode()[0])
df['Dependents']=df['Dependents'].fillna(df['Dependents'].mode()[0])
df['Education']=df['Education'].fillna(df['Dependents'].mode()[0])
df['Self_Employed']=df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df['Gender']=df['Gender'].fillna(df['Gender'].mode()[0])
df.head()

df['ApplicantIncome']=df['ApplicantIncome'].fillna(df['ApplicantIncome'].mean())
df['Loan_Amount_Term']=df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].mean())
df['LoanAmount']=df['LoanAmount'].fillna(df['LoanAmount'].mean())
df.head()

df['Credit_History']=df['Credit_History'].fillna(df['Credit_History'].median())
df.head()

df.info()
df.isnull().sum()
```

FOR DATA.CSV:

```python
import pandas as pd
df=pd.read_csv("/Data_set.csv")
print(df)
df.head(10)
df.info()
df.isnull()
df.isnull().sum()
df['show_name']=df['show_name'].fillna(df['aired_on'].mode()[0])
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network']=df['original_network'].fillna(df['aired_on'].mode()[0])
df.head()

df['rating']=df['rating'].fillna(df['rating'].mean())
df['current_overall_rank']=df['current_overall_rank'].fillna(df['current_overall_rank'].mean())
df.head()

df['watchers']=df['watchers'].fillna(df['watchers'].median())
df.head()

df.info()
df.isnull()
df.isnull().sum()
```

# OUTPUT:

# Data:
```python
import pandas as pd
df=pd.read_csv("/Loan_data.csv")
print(df)
df.head(10)
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/fefbe505-914f-4871-bf16-84a41ede290b)

# Non Null Before:
```python
df.info()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/caba26d6-38c5-4ae5-8920-d91e8d722d90)

# Mode:
```python
df['Loan_ID']=df['Loan_ID'].fillna(df['Dependents'].mode()[0])
df['Dependents']=df['Dependents'].fillna(df['Dependents'].mode()[0])
df['Education']=df['Education'].fillna(df['Dependents'].mode()[0])
df['Self_Employed']=df['Self_Employed'].fillna(df['Self_Employed'].mode()[0])
df['Gender']=df['Gender'].fillna(df['Gender'].mode()[0])
df.head()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/e0d5adf7-e372-4a2e-807e-d12e9b16ff81)

# Mean:
```python
df['ApplicantIncome']=df['ApplicantIncome'].fillna(df['ApplicantIncome'].mean())
df['Loan_Amount_Term']=df['Loan_Amount_Term'].fillna(df['Loan_Amount_Term'].mean())
df['LoanAmount']=df['LoanAmount'].fillna(df['LoanAmount'].mean())
df.head()
```

![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/7912d0a6-2c70-4a73-a695-7f49c4f2c9ea)

# Median:

```python
df['Credit_History']=df['Credit_History'].fillna(df['Credit_History'].median())
df.head()
```

![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/9e2ad2ed-6455-4898-8ec2-45841d27d05e)

# Non Null After:
```python
df.info()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/008c59d3-4158-43a5-b530-585c5b4477b5)

```python
df.isnull().sum()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/e20fa492-f6b9-4b3e-94da-41959d6afd62)

# For Data.csv:

# Data:
```python
import pandas as pd
df=pd.read_csv("/Data_set.csv")
print(df)
df.head(10)
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/e5ceeded-a911-4cb4-a9ac-94905d2ba17b)

# Non Null Before:

```python
df.info()
```

![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/de6ecabf-fa11-43b4-affc-f20e046e79fe)


```python
df.isnull()
```

![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/b19a7cbb-c956-4be6-8e0a-f31b3e82c45e)

# Mode:

```python
df['show_name']=df['show_name'].fillna(df['aired_on'].mode()[0])
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network']=df['original_network'].fillna(df['aired_on'].mode()[0])
df.head()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/0be82a8d-d29a-4373-9bbc-be1e942284f1)

# Mean:

```python
df['rating']=df['rating'].fillna(df['rating'].mean())
df['current_overall_rank']=df['current_overall_rank'].fillna(df['current_overall_rank'].mean())
df.head()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/a406affc-0d2e-4c78-ab31-15626bcf017e)

# Median:
```python
df['watchers']=df['watchers'].fillna(df['watchers'].median())
df.head()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/7cc5c8b8-2340-4b95-b3f6-2e81cb4fd533)

# Non Null After:

```python
df.info()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/8f048f86-cb34-49ef-a47e-019aa83d713b)

```python
 df.isnull()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/431767c9-0c76-4cea-8543-20eb701940a3)

```python
df.isnull().sum()
```
![image](https://github.com/vinushcv/ODD2023-Datascience-Ex01/assets/113975318/6ec22c00-2b5c-4570-a6ad-67e556fdbbbc)

## Result:
Thus,the given data is read,cleansed and the cleaned data is saved into the file.










