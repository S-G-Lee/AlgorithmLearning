```python
inputstr = input().split(', ')
inputlist = list(map(int, inputstr))

PI = 3.1415923135
resultlist = list(map(lambda x: 2 * x * PI,inputlist))

resultstr = ""
for idx, val in enumerate(resultlist):
    resultstr = resultstr + "{0:.2f}".format(val)
    if idx < len(resultlist) - 1:
        resultstr = resultstr + ", "
        
print(resultstr)
```



