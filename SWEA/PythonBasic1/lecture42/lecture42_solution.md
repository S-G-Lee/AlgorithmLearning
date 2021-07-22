```python
def CompareLength(str1, str2) :
    if len(str1) > len(str2) :
        return str1
    else : 
        return str2

T = input()
inputarr = T.split(", ")
print(CompareLength(inputarr[0],inputarr[1]))
```



