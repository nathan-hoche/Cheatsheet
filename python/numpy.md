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
array = np.random.randn(nb) # nb = 5, generate an array of 5 random number 

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

### Operator

In case of : (+, -, *, /)
```py
array * 2
# Equivalent to:
for x in range(list):
    list[x] *= 2
```

### Utils

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