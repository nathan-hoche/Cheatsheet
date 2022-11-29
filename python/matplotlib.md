# Matplotlib

## Import
```py
import matplotlib.pyplot as plt
```
# Data Visualization

### Display graph
```py
plt.show()
```

### Plot (for graph / mathematical function)
```py
plt.plot(list) # x axis is the index of the list
plt.plot(list, list)
plt.plot(list, list, 'ro') # 'ro' is the color and the shape of the points (r= red, o= dot)
plt.plot(list, list, 'bx') # (b= blue, x= cross)
plt.plot(list, list, 'g-') # (g= green, -= line)
plt.plot(list0, list1, 'r-', list2, list3, "b-") # display 2 lines can be replace by plt.plot(list0, list1, 'r-') \n plt.plot(list2, list3, "b-")
plt.plot ("Open", c="b", data=VIX) # plot the column "Open" of the dataframe VIX, and color it in blue
plt.plot ("Date", "Open", "ro", data=VIX) # plot the column "Open" of the dataframe VIX on the time not index, and color it in red with dots
```
> we can use multiple plot with the same list of x and y, so we can change the shape and color, for more complicate visualization

### Scatter (for point cloud)
```py
plt.scatter(list0, list1) # x axis is the index of the list
plt.scatter("RestingDP", "MaxHR", data=VIX) # plot the column "Open" of the dataframe VIX on the time not index, and color it in red with dots
plt.scatter("RestingDP", "MaxHR", c="Age", data=VIX) # color change depending of the column "Age"
plt.scatter("RestingDP", "MaxHR", s="Cholesterol", data=VIX) # size change depending of the column "Cholesterol"
```

### Bar (for bar chart)
```py
SalesDict = { # VIX data from the CBOE
"GEO0" : { "Geo" : "Kent", "Sales" : 100},
"GEO1" : { "Geo" : "Surrey", "Sales" : 110},
"GEO2" : { "Geo" : "Essex", "Sales" : 110},
"GEO3" : { "Geo" : "London", "Sales" : 120}
}
Sales = pd.DataFrame(data=SalesDict).T
plt.bar (Sales.Geo, Sales.Sales)

Freq = heart[["ChestPainType"]].groupby(["ChestPainType"]).size()
Classes = Freq.index
plt.bar(Classes, Freq)
```

### Histogram (for histogram)
```py
plt.hist(list) # x axis is the index of the list
plt.hist(list, bins=20) # number of bins
plt.hist(list, bins=20, density=True) # normalize the histogram
```

# Settings

### labels
```py
plt.xlabel('x label')
plt.ylabel('y label')
plt.title('title')
plt.grid(True) # display grid
```

### Add legends to plot
```py
plt.text(x, y, "text")
plt.text(x, y, "text", fontsize=nb) # fontsize
plt.annotate("text", xy=(x, y), xytext=(x, y), arrowprops=dict(facecolor='black', shrink=0.05)) # add an arrow
```
