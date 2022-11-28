# Pandas

### Import
```py
import pandas as pd
```

### Read CSV
```py
df = pd.read_csv('file.csv')
df = pd.read_csv(url)
```

### Convert dict to DataFrame
```py
df = pd.DataFrame(dict)
```

# Information

### Global Info
```py
df.info() # return number of rows, columns, type of each column
df.describe() # return mean, std, min, max, 25%, 50%, 75% of each column
```

### Shape
```py
df.shape
```

### Columns Type
```py
df.dtypes
```

### Max value
```py
df.column_name.max()
df['column_name'].max()
```

### Min value
```py
df.column_name.min()
df['column_name'].min()
```

### Mean value
```py
df.column_name.mean()
df['column_name'].mean()
```

### Get index
```py
df.index
```


# Print

### Partial
```py
df.head()
df.tail()
```

# Edit

### Transpose
```py
df = df.T
```

### Change row index
```py
df = df.set_index('column_name') # will replace index by values of column_name
```

### Add column
```py
df['new_column'] = df['column_1'] + df['column_2']
df['new_column'] = df['column_1'] > df['column_2'] # a column with boolean values
```

### Apply a func to each value
```py
df = df.apply(func) # to all the DataFrame
df = df.apply(func, axis=1) # to each row
df['column_name'] = df['column_name'].map(func) # to a specific column
```

### Sorting
```py
df.sort_values('column_name')
```

### Drop column
```py
df = df.drop(columns='column_name')
```

### Group
```py
df = df.groupby(['column_name']).sum() # group by column_name and sum values
df = df['column_name1'].groupby(['column_name2']).sum() # group by column_name2 and sum column_name1
df = df.groupby(['column_name1', 'column_name2']).sum() # group by column_name1 and column_name2 and sum values
df = df[['column_name1', 'column_name2']].groupby(['column_name1']).sum() # group by column_name1 and sum column_name1 and column_name2
```

### Concatenate
```py
df = pd.concat([df1, df2]) # concatenate df1 and df2
df = pd.concat([df1, df2], axis=1) # concatenate df1 and df2 by columns
```

# Select

### Column
```py
df.columns # return name of columns
df['column_name'] # return a specific column
df.column_name # return a specific column
```

### Row
```py
df.loc['id']
df.loc['id', 'column_name'] # return a specific value
df.loc[['id', 'id']] # return some specific rows
df.loc[['id', 'id'], ['column_1', 'column_2']] # return some specific rows and columns
df.loc[df['column_name'] == 'value'] # return rows where column_name is equal to value

df.iloc[index] # return first row
df.iloc[[index1, index2]] # return multiple rows

df['id':] # return every rows after id
df[:'id'] # return every rows before id
df['id':'id2'] # return every rows between id and id2
```