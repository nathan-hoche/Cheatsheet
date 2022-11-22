# Numpy

### Import

```py
import numpy as np
```

# Generate Array:

### To convert list to array
```py
array = np.array(list) # ex: list = [0, 1, 2, 3, 4, 5]
```

### To generate numpy array
```py
array = np.zeros(nb) # ex: nb = 5 -> [0, 0, 0, 0, 0]
array = np.ones(nb) # ex: nb = 5 -> [1, 1, 1, 1, 1]
array = np.empty(nb) # Allocate nb float space
array = np.arrange(nb) # ex: nb = 5 [0, 1, 2, 3, 4]
array = np.random.randn(nb) # nb = 5, generate an array of 5 random number between -1 and 1
array = np.random.randint(start_nb, end_nb, size_tuple) # nb = 5, generate an array of 5 random number 
```

### Slice
```py
# x[start:end:step]
array = np.arange(10)
array[:5] # first five elements
array[::2] # every other element
array[4:7] # middle subarray
array[(array >= 2) & (array <= 8)] # all values between 2 and 8
array[(array >= 2) & (array <= 8)] = 0 # set all values between 2 and 8 to 0
```

### Indexing
```py
array[[3, 7, 2]] # return [array[3], array[7], array[2]]

indices = np.array([[3, 7], [4, 5]])
np.array(indices) # return [[array[3], array[7]], [array[4], array[5]]]
```

# Multdimensionnal Array

### To convert list to array
```py
array = np.array(list) # ex: list = [[0, 1, 2], [3, 4, 5]]
```

### To generate numpy array
```py
# work with all way to generate single array
array = np.zeros(tuple) # ex: tuple = (2, 3) -> [[0, 0, 0], [0, 0, 0]]
```
### Resize
```py
data = np.zeros(nb) # nb = 5 [0, 1, 2, 3, 4, 3]
data = data.reshape(tuple) # ex: tuple = (2, 3) -> [[0, 1, 2], [3, 4, 5]]
```

### Slice
```py
# x[start:end:step, start:end:step]
array = np.random.randint(0, 100, (3, 4))
array[:2, :3] # first 2 rows and 3 columns
array[:3, ::2] # all rows, every other column
array[:, 0] # first column
array[0, :] = 0 # set first row to 0
```
> array[x, x] <=> array[x][x]

### Indexing
```py
array[2, [0, 2]] # return [array[2][0], array[2][2]]
array[:2, [0, 2]] # return [array[2][0], array[2][2]] for first and second row
```


# Operator

In case of : (+, -, *, /)
```py
array * 2
# Equivalent to:
for x in range(list):
    list[x] *= 2
```

In case of : (<, >, <=, >=)
```py
array < 6 # return array of boolean
array[array < 6] # return only element less than 6
```

# Utils

### Mean of all values

```py
np.mean(array)
```

### Sum all values

```py
np.sum(array)
```

### Max value

```py
np.max() # global one
np.max(axis=nb) # row/colonne
```

### Count

```py
np.count_nonzero(array)
```

# File

### Save
```py
np.save('some_array', array)
np.savetxt('some_array.txt', array)
np.savetxt('some_array.csv', array, delimiter=',')
```

### Load
```py
array = np.load('some_array.npy')
array = np.loadtxt('some_array.csv', delimter=',')
```
