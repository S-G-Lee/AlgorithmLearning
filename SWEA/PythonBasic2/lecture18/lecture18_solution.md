```python
inputlist = list(map(int, input().split(', ')))

resultlist = [i for i in inputlist if i%2 != 0]

resultstr = ", ".join(str(e) for e in resultlist)

print(resultstr)
```



