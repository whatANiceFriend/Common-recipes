```
import pandas as pd
```
## pd.DataFrame()
```
# Create a DataFrame from a dictionary
data = {"name": ["Alice", "Bob", "Charlie"], "age": [25, 30, 35]}
df = pd.DataFrame(data)
```
## pd.read_csv()
```
df = pd.read_csv('my_data.csv')
```
## df.to_csv()
```
# write the DataFrame to a CSV file
df.to_csv('my_data.csv', index=False)
```
## df.drop()
```
# Drop columns "col2" and "col3" from the DataFrame
df = df.drop(["col2", "col3"], axis=1)
```
## df.dropna()
```
Drop columns that contain missing values
df_filtered = df.dropna(axis=1)
```
## df.isnull()
```
# Check if column "col2" contains any missing values
col2_is_null = df["col2"].isnull()
```
## df.notnull()
```
# Check if column "col2" does not contain any missing values
col2_not_null = df["col2"].notnull()

# Check for missing values in the DataFrame
print(df.isnull())
```
## df.sort_values()
```
# Sort the DataFrame by the "age" column in descending order
df_sorted = df.sort_values("age", ascending=False)

# Sort the DataFrame by the "age" and "name" columns in ascending order
df_sorted = df.sort_values(["age", "name"])
```
## df.apply()
```
# Define a function that takes two arguments and returns their sum
def add_columns(x, y):
    return x + y

# Use apply() to add a new column to the DataFrame that is the sum of "col1" and "col2"
df["col3"] = df.apply(lambda row: add_columns(row["col1"], row["col2"]), axis=1)
```
## df.rename()
```
# Rename columns in the DataFrame
df = df.rename(columns={"old_name": "new_name"})
```
## df.groupby()
```
# Group the DataFrame by a column and calculate the mean of another column
grouped = df.groupby("group_col")["mean_col"].mean()
```
## df.fillna()
```
# Fill missing values in the DataFrame with 0
df = df.fillna(0)
```
## df.pivot_table()
```
# Create a pivot table from the DataFrame
pivot_table = pd.pivot_table(df, values="value_col", index="index_col", columns="column_col", aggfunc="mean")
```
## df.merge()
```
# Merge two DataFrames based on a common column
merged_df = pd.merge(df1, df2, on="common_col")

merged_df = df1.merge(df2, left_on='lkey', right_on='rkey', how = 'left'
          suffixes=('_left', '_right'))
```
## Select rows base on some condition
```
# Select rows where the "age" column is greater than 30
df_filtered = df[df["age"] > 30]

# Select rows where the "name" column is equal to "Bob"
df_filtered = df[df["name"] == "Bob"]

# select rows where age is greater than 30 and gender is 'M'
df_filtered = df[(df['age'] > 30) & (df['gender'] == 'M')]
```
