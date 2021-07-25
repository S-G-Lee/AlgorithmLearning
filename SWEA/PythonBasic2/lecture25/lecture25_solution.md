```python
def removeduplicate1(arr):
    temp = set(arr)
    temp = list(temp)
    return temp

def removeduplicate2(arr):
    duplicateidxlist = []
    for i in range(len(arr)):
        src = arr[i]
        idx = i+1
        while idx< len(arr):
            if arr[idx] == src:
                duplicateidxlist.append(idx)
            idx += 1
    
    result = [val for idx, val in enumerate(arr) if idx not in duplicateidxlist]
    return result

inputlist = [12,24,35,24,88,120,155,88,120,155]

#resultlist = removeduplicate1(inputlist)
resultlist = removeduplicate2(inputlist)

print(resultlist)
```



