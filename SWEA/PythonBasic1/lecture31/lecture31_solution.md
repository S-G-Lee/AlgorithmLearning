```python
for i in range(1,6) :
    tempstr = ""
    for temp in range(0,6-i-1) : 
        tempstr = tempstr + " "
    for temp in range(0,i):
        tempstr = tempstr + "*"
    print(tempstr)
```



