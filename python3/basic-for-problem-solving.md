### Read input from standard input stream
```python
input()
```

### type casting
```python
num = int("100")
```

### type casting
```python
num = int("100")
```

### for loop
```python
for i in range(1, 10): #1 to 9
    print(i)
```

### for loop reversed
```python
for i in reversed(range(1, 10)): #9 to 1
    print(i)
```

### for loop with index
```python
fibonacci = [0,1,1,2,3,5,8,13,21]
for i in range(len(fibonacci)):
    print(i,fibonacci[i])
```

### print
```python
print("Hello, World!") # *****
```

### repeat String
```python
print('*' * 5) # *****
```

### split String into array
```python
'Hello,World'.split(',')

# toString, split into array of each character
list(str(12345))
```

### init array
```python
arr = []
for i in range(0, rows):
    arr.append([0]*(cols))
```

### copy array
```python
newArr = list(oldArr)

newArr = oldArr[:]

newArr = oldArr # same reference
```

### sort
```python
sorted([5, 2, 4, 1, 3])

#reverse
sorted([5, 2, 4, 1, 3], reverse=True)

#sort by length
sorted(["chemistry","physics","mathematics","art"], key=len)
```


### substring
```python
var1 = 'Hello World!'
var2 = "Python Programming"

print ("var1[0]: ", var1[0]) # var1[0]:  H
print ("var2[1:5]: ", var2[1:5]) # var2[1:5]:  ytho => from index 1 to 5(before)

var1[0]:  H
var2[1:5]:  ytho
```
