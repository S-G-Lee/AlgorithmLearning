```python
def maximum(arr) : 
    temp = 0
    for i in arr:
        if temp < i:
            temp = i
    return temp

inputarr = [3, 5, 4, 1, 8, 10, 2]
print(f"max{tuple(inputarr)} => {maximum(inputarr)}")
```



