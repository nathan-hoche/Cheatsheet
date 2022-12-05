# Scikit-learn

## Import
```py
import sklearn
```

# Dataset

### Load dataset
```py
from sklearn import datasets
iris = datasets.load_iris()
```

### Create dataset
```py
from sklearn.datasets import make_blobs
X, y = make_blobs(n_samples=100, centers=2, random_state=0, cluster_std=0.60)
```

# Model

### K-means
```py
from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=3, # number of clusters
    init='random', # centroid initialisation
    n_init=10, # number of executions
    max_iter=300, # number of iterations
    random_state=0 # random seed
)
kmeans.fit_predict(X)
kmeans.cluster_centers_ # centroids
```

### One Hot encoding
```py
from sklearn.preprocessing import OneHotEncoder
# creates the encoder object
enc = OneHotEncoder(handle_unknown='ignore', sparse=False)
# encodes and replaces the original values on the dataframe
values = enc.fit_transform(df.loc[:, ['Sex']])
# checks the categories name ['female', 'male']
enc.categories_
# adds the columns to the dataframe
df['Female'] = values[:, 0]
df['Male'] = values[:, 1]
# removes the categorical column
df.drop(columns=['Sex'])
```

# Tree

### Decision Tree
```py
from sklearn.tree import DecisionTreeClassifier
tree = DecisionTreeClassifier(criterion='entropy', # entropy or gini
    max_depth=3, # max depth of the tree
    random_state=0 # random seed
)
tree.fit(X_train, y_train)
```

### Visualize Decision Tree
```py
from matplotlib import pyplot as plt
from sklearn.tree import export_text
from sklearn.tree import plot_tree
# text representation
text_representation = export_text(tree)
print(text_representation)
# graphic representation
fig = plt.figure(figsize=(25,20))
_ = plot_tree(tree, feature_names=columns, class_names=y_train.values, filled=True)
```

### Evaluation
```py
tree.score(X_train, y_train)
```

### Matrix Evaluation
```py
from sklearn.metrics import confusion_matrix, ConfusionMatrixDisplay
predictions = tree.predict(X_train)
cm = confusion_matrix(y_train, predictions, labels=tree.classes_)
disp = ConfusionMatrixDisplay(confusion_matrix=cm, display_labels=tree.classes_)
# displays the matrix
_ = disp.plot()
```

### Evaluation train + test
```py
from sklearn.model_selection import train_test_split
X = iris_data.loc[:, 'sepal length':'petal width']
y = iris_data['class']
# splits the data in training + testing
X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=0)
# builds the classifier
tree = DecisionTreeClassifier()
tree.fit(X_train, y_train)
# evaluates on the test data
tree.score(X_test, y_test)
# displays the confusion matrix
predictions = tree.predict(X_test)
cm = confusion_matrix(y_test, predictions, labels=tree.classes_)
disp = ConfusionMatrixDisplay(confusion_matrix=cm, display_labels=tree.classes_)
_ = disp.plot()
```

### Other Classifier
```py
from sklearn.ensemble import RandomForestClassifier
# ... as before
# instead of tree use a forest
forest = RandomForestClassifier(n_estimators=10, random_state=0)
# ... as before
```

# Model Creation

### Linear Regression
```py
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)
```

### Decision Tree
```py
from sklearn.tree import DecisionTreeRegressor
regressor = DecisionTreeRegressor()
regressor.fit(X_train, y_train)
```

### Evaluation
```py
model.score(X_train, y_train)
```

### Evaluation train + test
```py
from sklearn.model_selection import train_test_split
X = concrete_data.iloc[:, 0:-1]
y = concrete_data.iloc[:, -1]
# train + test split
X_train, X_test, y_train, y_test = train_test_split(X, y, random_state=0)
# builds the regressor
regressor = DecisionTreeRegressor()
regressor.fit(X_train, y_train)
# evaluates on the test data
regressor.score(X_test, y_test)
```

