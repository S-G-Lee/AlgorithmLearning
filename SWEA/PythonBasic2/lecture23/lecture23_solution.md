```python
inputlist = [12, 24, 35, 70, 88, 120, 155]

resultlist = [val for idx, val in enumerate(inputlist) if (idx != 0 and idx != 4 and idx != 5)]

print(resultlist)
```



