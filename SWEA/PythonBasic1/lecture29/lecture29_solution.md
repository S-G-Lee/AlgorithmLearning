```python
i = 4
while i > 0 : 
    tempstr = ""
    for temp in range(4-i) :
        tempstr = tempstr + " "
    for temp in range(2*i-1) : 
        tempstr = tempstr + "*"
    for temp in range(4-i) :
        tempstr = tempstr + " "
    print(tempstr)
    i -= 1

```



