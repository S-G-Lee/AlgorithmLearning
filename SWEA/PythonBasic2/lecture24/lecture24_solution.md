```python
inputlist1 = [1,3,6,78,35,55]
inputlist2 = [12,24,35,24,88,120,155]

resultlist = []
for i in inputlist1:
    for j in inputlist2:
        if i == j:
            resultlist.append(i)
            break

print(resultlist)
```



