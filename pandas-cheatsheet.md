# Pandas Cheat Sheet

## Introduction

Pandas is a Python library for data manipulation and analysis. It offers data structures and operations for manipulating numerical tables and time series.

## Installation
```
pip install pandas

```
## Importing Pandas
```
import pandas as pd

```
## Creating a DataFrame
```
data = {'Name': ['Alice', 'Bob'], 'Age': [25, 30], 'City': ['NY', 'LA']}
df = pd.DataFrame(data)
```
## Reading and Writing Data

#### Read CSV and Excel files
```
df = pd.read_csv('file.csv')
df = pd.read_excel('file.xlsx')
```
#### Save DataFrame to CSV and Excel
```
df.to_csv('file.csv', index=False)
df.to_excel('file.xlsx', index=False)
```

#### Viewing Data
```
df.head()  # First 5 rows
df.tail()  # Last 5 rows
df.info()  # Info about DataFrame
df.shape   # Number of rows and columns
df.columns # List of column names
df.dtypes  # Data types of columns
```
## Data Manipulation

#### Change data type
```
df[['col1', 'col2']] = df[['col1', 'col2']].astype('float')

```

#### Describe statistics

```
df.describe() #show all columns
df[['col1', 'col2']].describe() #show only specific columns
```
#### Counting & Unique Values

```
unique_values = df['Column'].unique()
value_counts = df['Column'].value_counts()
df['column_name'].value_counts().idxmax() #counts most frequent
```

#### Correlation between numeric columns
```
numeric_df = df[['col1', 'col2']]
numeric_df.corr()
```
### Indexing & Selection

#### Set and reset index
```
df.set_index('Column1', inplace=True)
df.reset_index(inplace=True)
```
#### Accessing columns
```
df['column']
df[['col1', 'col2']]
```
#### Filtering
```
df[df['column'] > 10]

```
## Modifying DataFrame

#### Add Headers

```
headers = ["Manufacturer", "Price"]
df.columns = headers
print(df.head())
```

#### Rename columns
```
df.rename(columns={'old_name': 'new_name'}, inplace=True)

```
#### Add a new column
```
df['NewColumn'] = df['Column1'] * 2
df['Total'] = df['ColumnName'].sum(axis=1)      

```
#### Drop a column
```

df.drop('Column1', axis=1, inplace=True)

```

## Aggregation & Grouping

##### Group by operation
```
df_group = df.groupby(['col1']).mean()
df_group = df.groupby(['col1']).count()
df_group = df.groupby(['col1']).sum()

```
#### Pivot table
```
df.pivot_table(values='Value', index='Row', columns='Column', aggfunc='mean')

```

## Handling Missing Data

#### Null values
```

df.isnull().sum()

```

#### Remove missing values
```
df.dropna(subset=['column'], inplace=True)
df.dropna(subset=[“column_name”],axis=0,inplace=True)
```       

#### Fill missing values
```

df.fillna(0, inplace=True) #Fill with zeros

```
#### Replace missing values
```

df['column'].replace(np.nan, 'default_value', inplace=True)

```

## Sorting & Ordering
```
df.sort_values(by='column', ascending=False, inplace=True)

```

## Statistical & Mathematical Operations

##### Column-wise operations
```
df['Total'] = df.sum(axis=1)
Mean_value = df['Column'].mean()
Max_value = df['ColumnName'].max()
Min_Values = df['ColumnName'].min()                  
```

## Merging & Joining DataFrames

#### Merge DataFrames
```
pd.merge(df1, df2, on='key')

```

#### Concatenate
```
df = pd.concat([df1, df2], axis=1)

```

## Working with Dates
```
df['Date'] = pd.to_datetime(df['Date']) #Conversion to Date
df['Year'] = df['Date'].dt.year 
df['Month'] = df['Date'].dt.month
```

## String Operations
```
df['column'].str.contains('text')

```

## Data Normalization & Binning

#### Normalization

```
df['col'] = df['col'] / df['col'].max()

```

#### Binning

```
df['binned'] = pd.cut(df['Price'], bins=[0, 50, 100], labels=['Low', 'High'])

```

#### One-Hot Encoding

```
dummy_vars = pd.get_dummies(df['Category'])
df = pd.concat([df, dummy_vars], axis=1)
df.drop('Category', axis=1, inplace=True)
```
