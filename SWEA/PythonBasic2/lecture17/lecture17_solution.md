```python
inputlist = input().split(', ')
resultlist = sorted(inputlist)

resultstr = ""
length = len(resultlist)
for idx, val in enumerate(resultlist):
    resultstr = resultstr + val
    if idx < length - 1:
        resultstr = resultstr + ", "

print(resultstr)
```



