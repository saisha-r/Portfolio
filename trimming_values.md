## Trimming Values with Conditionals

The following code creates a new list containing 0s where the original list's values were negative, and 1s where the original list's values were positive.

~~~python
original = [-1.5, 0.2, 0.4, 0.0, -1.3, 0.4]
result = []
for value in original:
    if value < 0.0:
        result.append(0)
    else:
        result.append(1)
        
print(result)
~~~


```

```
