# Pandas

## 1. What is Pandas

A Python library is like a collection of pre-built tools or functions that we can use to perform specific tasks without writing code from scratch. In the case of pandas, it's a popular library that helps us work with data in a structured way, making it easier to analyze and manipulate data tables.

In other words Pandas is the "excel" of Python.

To import the pandas library in Python, you can use the import statement. 

```python
import pandas as pd
```

- `import` is the Python keyword used to import external libraries.
- `pandas` is the name of the library you want to import.
- `as pd` is an alias or shorthand that you can use to refer to the pandas library in your code.

It's a common convention to use `pd` as the alias when working with pandas, but you can choose any alias you prefer.


## 2. Dataframe

A DataFrame in pandas is like a super spreadsheet where you can store and work with data in rows and columns, making it easy to analyze and manipulate information.

### 2.1 Create df from zero

```python
# Dictionary with the data
data = {
    'Model': ['Boeing 747', 'Airbus A320', 'Cessna 172', 'Embraer E190'],
    'Manufacturer': ['Boeing', 'Airbus', 'Cessna', 'Embraer'],
    'Passenger Capacity': [660, 220, 4, 114],
    'Max Speed (mph)': [570, 511, 131, 541]
}

# Dataframe generation
df_planes = df = pd.Dataframe()

print(df_planes)
```

```output title="output"
          Model Manufacturer  Passenger Capacity  Max Speed (mph)
0    Boeing 747       Boeing                 660               570
1  Airbus A320       Airbus                 220               511
2    Cessna 172       Cessna                   4               131
3  Embraer E190      Embraer                 114               541
```

### 2.2 Create df from a file

!!! tip "Reminder"
    If the file is in the same folder of the code, you don't need to write the path, just the name of the file to opern it from pandas.

```python
# Path to the CSV file
file_path = 'airports.csv'

# Read the CSV file and create a DataFrame
airports_df = pd.read_csv(file_path)

# Display the DataFrame
print(airports_df)
```

## 3. Exploring operations

### 3.1 Display the head and tail

### 3.2 Get the size and total

### 3.3 Data info & describe


## 4. Extracting operations

These operations allow the user to retrieve specific columns or rows from a DataFrame for analysis and manipulation.

### 4.1 Extract a column

```python
# Extract the 'Age' column
planes = df_planes['Model']

print(planes)
```

```output title="output"
0      Boeing 747
1     Airbus A320
2      Cessna 172
3    Embraer E190
Name: Model, dtype: object
```

### 4.3 Extract multiple columns

```python
# Selecting the columns
selected_columns = df_planes[['Model', 'Max Speed (mph)']]

# Printing the selected columns
print(selected_columns)
```

```output title="output"
          Model  Max Speed (mph)
0    Boeing 747              570
1   Airbus A320              511
2    Cessna 172              131
3  Embraer E190              541
```

### 4.4 Extract a row by index

```python
# Extracting a row by index using iloc
row_at_index_2 = df_planes.iloc[2]

# Printing the extracted row
print(row_at_index_2)
```

```output title="output"
Model                 Cessna 172
Manufacturer              Cessna
Passenger Capacity             4
Max Speed (mph)              131
Name: 2, dtype: object
```

### 4.5 Extract a row by condition

Suppose you want to extract all rows where the speed is greater than 200 mph.

```python
# Extracting rows with speed > 200 mph
df_fast_planes = df_planes[df_planes['Max Speed (mph)'] > 200]

# Printing the extracted rows
print(df_fast_planes)
```

```output title="output"
          Model Manufacturer  Passenger Capacity  Max Speed (mph)
0    Boeing 747       Boeing                 660              570
1   Airbus A320       Airbus                 220              511
3  Embraer E190      Embraer                 114              541
```

## 5. Edit columns & rows

### 5.1 Add a new column

To add a new column to a pandas DataFrame, you can simply assign a list or a Series to a new column name. Remember to add a column with the same amount of rows of the dataframe.

```python
# List of lengths in meters
lengths_in_meters = [70.6, 37.6, 8.2, 36.2]

# Add a new column named "Length (m)" to df with the length values
df_planes['Length'] = lengths_in_meters

# Print the updated DataFrame
print(df_planes)
```

```output title="output"
          Model Manufacturer  Passenger Capacity  Max Speed (mph)      Length
0    Boeing 747       Boeing                 660              570        70.6
1   Airbus A320       Airbus                 220              511        37.6
2    Cessna 172       Cessna                   4              131         8.2
3  Embraer E190      Embraer                 114              541        36.2
```

### 5.2 Rename a column

```python
# Rename the "Lenght" column to "Length (m)"
df_planes.rename(columns={'Length': 'Length (m)'}, inplace=True)

# Print the updated DataFrame
print(df_planes)
```

```output title="output"
          Model Manufacturer  Passenger Capacity  Max Speed (mph)  Length (m)
0    Boeing 747       Boeing                 660              570        70.6
1   Airbus A320       Airbus                 220              511        37.6
2    Cessna 172       Cessna                   4              131         8.2
3  Embraer E190      Embraer                 114              541        36.2
```

## 6. Aggregate operations

Imagine you have a database with hacker attacks.

| datetime             | ip_source       | location     | type_of_attack   | severity | duration_minutes |
| --- | --- | --- | ---| --- | --- |
| 2023-04-10 08:15:00  | 192.168.1.100  | Madrid     | DDoS             | High     | 45               |
| 2023-04-10 12:45:00  | 203.54.32.17   | Los Angeles  | Phishing         | Medium   | 30               |
| 2023-04-11 14:30:00  | 104.23.45.67   | London       | SQL Injection    | Low      | 60               |
| 2023-04-12 20:10:00  | 45.76.12.34    | Singapore    | Malware          | High     | 90               |
| 2023-04-10 16:03:00  | 203.54.32.17   | Los Angeles  | Phishing         | Medium   | 30               |


### 6.1 Unique values

```python
unique_attack_types = df_attacks['type_of_attack'].unique()
print(unique_attack_types)
```

```output title="output"
['DDoS' 'Phishing' 'SQL Injection' 'Malware']
```

### 6.2 Count unique values

```python
unique_attack_count = df_attacks['type_of_attack'].nunique()
print(unique_attack_count)
```

```output title="output"
4
```

### 6.3 Count elements in a column

```python
element_count = df_attacks['datetime'].count()
print(element_count)
```

```output title="output"
5
```

### 6.4 Math operators


## 7. Grooping Operations

*Reset index*

### 7.1 Group rows counting

### 7.2 Group rows operating

### 7.3 Multiple grooping


## 8. Other operations

### 8.1 Ordering rows of a dataframe

### 8.2 Joining two dataframes


