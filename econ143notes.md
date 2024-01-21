# Week 1
## Lab 01 Using Pandas
Learning the differeence between .loc and .iloc
```python 
df.iloc[1:3, 0:2]  # Select rows 1 and 2, columns 0 and 1,  accessing data based on integer positions

df.loc['row2':'row4', 'columnA':'columnB']  # Select rows 'row2' to 'row4', columns 'columnA' to 'columnB', accessing data based on label locations
```
