```python
arr = []
for i in range(100,301):
    if (i//100)%2 == 0 : 
        if (i//10)%2 == 0 : 
            if i%2 == 0 :
                arr.append(str(i))

result = ""
for arridx in range(0,len(arr)):
    if arridx < len(arr)-1:
        result = result+arr[arridx]+","
result = result + arr[-1]
print(result)
```



