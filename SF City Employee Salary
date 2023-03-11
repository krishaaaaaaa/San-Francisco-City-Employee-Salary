import pandas as pd
import numpy as np


df = pd.read_csv("Salaries.csv",low_memory=False)
data = df.drop(['Id','Notes','Agency','Status'], axis=1)


#print(f"{df.info()}\n{df.columns}\n{df.shape}\n{df.dtypes}")
#1.  Display Top 10 Rows of The Dataset
print(df.head(10))

#2. Check Last 10 Rows of The Dataset

print(df.tail(10))
#3. Find Shape of Our Dataset (Number of Rows And Number of Columns)
print(f"number og rows: {df.shape[0]}\nNumber of Columns: {df.shape[1]}")

#4.  Getting Information About Our Dataset Like Total Number Rows, Total Number of Columns, Datatypes of Each Column And Memory Requirement
print(df.info())

#5. Check Null Values In The Dataset
print(df.isnull().sum())

#6. Drop ID, Notes, Agency, and Status Columns
data = df.drop(['Id','Notes','Agency','Status'], axis=1)
print(data.info())

#7. Get Overall Statistics About The Dataframe
print(data.describe(include='all'))


#8. Find Occurrence of The Employee Names  (Top 5)
print(df['EmployeeName'].value_counts().head())

#9. Find The Number of Unique Job Titles
print(df['JobTitle'].nunique())

#10.Total Number of Job Titles Contain Captain
print(df['JobTitle'].str.contains('Captain',case= False).sum())
print(df[df['JobTitle'].str.contains('Captain',case= False)].count())
print(len(df[df['JobTitle'].str.contains('Captain',case= False)]))

#11. Display All the Employee Names From Fire Department
print(df[df[ 'JobTitle'].str.contains('FIRE', case=False)]['EmployeeName'])

#12. Find Minimum, Maximum, and Average BasePay
print((pd.to_numeric(df['BasePay'].replace('Not Provided', np.nan))).describe())

#13. Replace 'Not Provided' in EmployeeName' Column to NaN
df['EmployeeName'] = df['EmployeeName'].replace('Not provided', np.nan)
print( df['EmployeeName'])

#14. Drop The Rows Having 5 Missing Values
data = df.drop(df[df.isnull().sum(axis=1)==3].index,axis=0)
print(data)
print([data.isnull().sum(axis=1)])

#15. Find Job Title of ALBERT PARDINI
print(df[df['EmployeeName'] == 'ALBERT PARDINI']['JobTitle'])

#16. How Much ALBERT PARDINI Make (Include Benefits)?
print(df[df['EmployeeName'] == 'ALBERT PARDINI']['TotalPayBenefits'])
print(df[df['EmployeeName'] == 'ALBERT PARDINI'])

#17.Display Name of The Person Having The Highest BasePay
data = pd.concat([pd.to_numeric(df['BasePay'].replace('Not Provided', np.nan)),  df['EmployeeName'],df['JobTitle'], df['Year']], axis = 1)
print(data[data['BasePay'].max()==data['BasePay']]['EmployeeName'])

#18.Find Average BasePay of All Employee Per Year
print(data.groupby('Year').mean())

#19. Find Average BasePay of All Employee Per JobTitle
print(data.groupby('JobTitle').mean()['BasePay'])

#20. Find Average BasePay of Employee Having Job Title ACCOUNTANT
print(data[data['JobTitle']=='ACCOUNTANT']['BasePay'].mean())

#21. Find Top 5 Most Common Jobs
#print(data.groupby('JobTitle').count())
print(data['JobTitle'].value_counts().head())
