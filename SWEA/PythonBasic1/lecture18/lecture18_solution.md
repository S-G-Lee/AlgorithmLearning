```python
arr = []
for i in range(1,201):
    if i%7 == 0 : 
        if i%5 != 0 : 
            arr.append(str(i))

result = ""
for arridx in range(0,len(arr)):
    if arridx < len(arr)-1:
        result = result+arr[arridx]+","
result = result + arr[-1]
print(result)
```



