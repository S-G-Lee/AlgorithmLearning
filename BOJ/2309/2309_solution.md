```python
height = []
for _ in range(9):
    height.append(int(input()))

height_sum = sum(height)

result = height[:]
check = 0
for i in range(9):
    tempheight = height_sum - height[i]
    for j in range(i+1, 9):
        temptempheight = tempheight -height[j]
        if temptempheight == 100:
            check = 1
            result.remove(height[i])
            result.remove(height[j])
            break
    if check:
        break

result.sort()
for i in result:
    print(i)
            
```



