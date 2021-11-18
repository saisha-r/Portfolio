# Writing for loops that use the accumulator pattern

The follow codes establishes acclumator variables and uses for loops to update the variable.

```python

#Prints the total number of characters for each word
total = 0

for word in ['red', 'green', 'blue']:
    total = total + len(word)

print(total)

#Prints a list of the lengths of each word
lengths = []

for word in ['red', 'green', 'blue']:
    lengths.append(len(word))

print(lengths)

#Concatenates all of the words in the list into one string
words = ['red', 'green', 'blue']
result = ""

for colour in words:
    result = result + colour

print(result)

#Creates acronym "RGB"
words = ['red', 'green', 'blue']
result = ""

for colour in words:
    result = result + colour[0].upper()

print(result)

#Outputs a list with the cumulative sum of data
data = [1, 2, 2, 5]
cumulative = []
sum = 0

for number in data:
    sum += number
    cumulative.append(sum)

print(cumulative)


```

```
