```python
mult_table = []
for i in range(2,10):
    templist = []
    for j in range(1,10):
        templist.append(i*j)
    mult_table.append(templist)

for i in mult_table:
    idx = 0
    while idx < len(i):
        if (i[idx]%3 == 0) or (i[idx]%7 == 0):
            i.pop(idx)
        else:
            idx += 1

print(mult_table)
```



