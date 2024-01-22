# Week 1
## Loading in and looking at the data
### Packages
Pandas, NumPy, Matlablib
```Python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
### Loading in a .csv
```python 
pd.read_csv('name.csv')
```
### .apply
Parameters 
* Fucntion: the function to apply to each column or row
* Axis: which way to apply the function to, 0 applies the function to columns and 1 applies the function to rows
### Extracting data 
We can extract specific rows of columns of a df in 4 ways:
* .head 
* .tail
* .loc: gets values based on the index/column label that is associated with them
```python
df.loc[:,['column name 1','column name 2']]

df.iloc[1:3, 0:2]  # Select rows 1 and 2, columns 0 and 1,  accessing data based on integer positions

```
The : specifies that were are interested in all of the labels or indexes 
* .iloc: looks at the integers associated with each label rather than the label itself
```python
df.iloc[0:854,4]

df.loc['row2':'row4', 'columnA':'columnB']  # Select rows 'row2' to 'row4', columns 'columnA' to 'columnB', accessing data based on label locations
```
This example means we are extracting rows 0 to 854 and we want the 5th column 
* []: can enter a single column table, a list of column labels, or a slice of row index positions

## Selecting and Modifying Rows/Columns
### Logical operators
* < less than
```python
df['beer_tax'] < 3
```
* & you only want the data that satisfies both conditions, note the parenthesis around the boolean expression, a boolean is an expression or data type that either represents 'True' or "False'
```python
df[(df['beer_tax'] < 3) & (df['btax_dollars'] < 0.5)]

```
* | is the either or expression
* ^ is the way to express either is true, but both are not true
### Multiple labels
* df['string_name'].isin()
```python
df[df['st_name'].isin(['CA','FL','TX','NE'])]
```
### Adding columns
If we want to create a new column named total_percent_tax into the dataframe ths syntax is 
```python
df[new_column_name] = series or array name
```
### Renaming columns
If we wanted to rename a column c_beer to beer_consumption we use this syntax
```python
df.rename(columns={'c_beer':'beer_consumption'})
```
Pandas just returns a copy of the modified Dataaframe rather than changing the original dataframe.  To change the origiinal df you set inplace = True or you can manually assign the new df = df
### Dropping columns
```python
df.drop(columns=['salestax'])
```
You can also pass in a list of columns that you want to pass and then used the axis parameter to specify that the labels represent column names
```python
df.drop(["salestax","beer_tax"], axis = 'columns')
```
### Changing the index of a df
When you have inplace = True, this modifies the original df. To set the newly index df to a new variable, delet this part of the code  
```python
df.set_index('string' , inplace = True)
```
