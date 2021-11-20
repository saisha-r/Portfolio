## Removing an Outlier in a List
In a list containing reaction times (RT), there is one value that is about 1 second longer than most of the data. The following code identifies this outlier in the data and removes this value from the RT data.


```python
# The lists
rt = [0.394252808, 0.442094359, 0.534764366, 0.565906723, 0.570404592, 
      0.486154719, 0.518792127, 0.844916827, 0.495622859, 0.476159436, 
      0.612854746, 0.529661203, 0.389157455, 1.517088266, 0.573962432, 
      0.714152493, 0.409225638, 0.435308188, 0.509801957, 0.544626271, 
      0.437877745, 0.333356848, 0.401773569, 0.479840688]

# This shows you the longest RT (the outlier)
print('The slowest rt is:', max(rt))
```

    The slowest rt is: 1.517088266



```python
# Finds the outlier and removes it
position = rt.index(max(rt))
del rt[position]

# To check that the outlier has been removed...

# This finds the new slowest RT, rounded to 2 decimal places
print('The slowest rt remaining is:', round(max(rt), 2))
```

    The slowest rt remaining is: 0.84

