```python
W, H = map(int, input().split())
N = int(input())
horizontal_cut = [0] 
vertical_cut = [0]
for i in range(N):
    a, b = map(int, input().split())
    if a == 0:
        horizontal_cut.append(b)
    else:
        vertical_cut.append(b)

horizontal_cut.sort()
vertical_cut.sort()

horizontal_cut.append(H)
vertical_cut.append(W)

width_max = 0
height_max = 0
for i in range(len(vertical_cut) - 1):
    temp = vertical_cut[i+1] - vertical_cut[i]
    if width_max < temp:
        width_max = temp
for i in range(len(horizontal_cut) - 1):
    temp = horizontal_cut[i+1] - horizontal_cut[i]
    if height_max < temp:
        height_max = temp

result = width_max * height_max
print(result)
```



