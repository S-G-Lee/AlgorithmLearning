```python
inputstr = list(input())

resultdict = {}
for char in inputstr:
    if char in resultdict:
        resultdict[char] += 1
    else:
        resultdict[char] = 1

for key, val in resultdict.items():
    print(f'{key},{val}')
```



