```python
def createdictionary(string):
    tempdict = {}
    for i in range(len(string)):
        tempdict[string[i]] = i
    return tempdict

inputstr = 'abcdef'
strdict = createdictionary(inputstr)
for i in strdict.items():
    print(f"{i[0]}: {i[1]}")
```



