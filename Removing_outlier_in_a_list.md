## Removing an outlier in a list

The following code identifies the longest reaction time (RT) in the data and removes this value from both the RT data and the error data.

~~~python

#The lists
rt = [0.394252808, 0.442094359, 0.534764366, 0.565906723, 0.570404592, 
      0.486154719, 0.518792127, 0.844916827, 0.495622859, 0.476159436, 
      0.612854746, 0.529661203, 0.389157455, 1.517088266, 0.573962432, 
      0.714152493, 0.409225638, 0.435308188, 0.509801957, 0.544626271, 
      0.437877745, 0.333356848, 0.401773569, 0.479840688]

err = [False, False, True, False, False, False, False, False, True, False, 
       False, True, False, False, False, False, True, True, True, False, 
       ]

#Finds the position (index) of the slowest RT in the data
position = rt.index(max(rt))

#Removes that slowest RT value from the list rt
del rt[position]

#Removes the data from err
del err[position]

#Prints the slowest RT remaining, rounded to two decimal places
print('The slowest rt remaining is:', round(max(rt), 2))

#prints the lengths of rt and err
print('The length of rt is', len(rt), 'and the length of err is', len(err)
~~~
