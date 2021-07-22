```python
def CheckNum(list, num) :
    if num in list : 
        return "True"
    else :
        return "False"

inputlist = [2, 4, 6, 8, 10]
num1 = 5
num2 = 10

print(inputlist)
result = CheckNum(inputlist, num1)
print("%d => %s" % (num1, result))
result = CheckNum(inputlist, num2)
print("%d => %s" % (num2, result))
```



