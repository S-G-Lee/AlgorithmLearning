```python
columnnum, rownum = map(int, input().split(', '))

resultlist = []
for i in range(columnnum):
    templist = []
    for j in range(rownum):
        templist.append(i*j)
    resultlist.append(templist)
    
print(resultlist)

```



