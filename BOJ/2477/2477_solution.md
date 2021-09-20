```python
K = int(input())

sides = []
for _ in range(6):
    sides.append(list(map(int, input().split())))

# side[i]의 0번째항이 1:동쪽, 2:서쪽, 3:남쪽, 4:북쪽
lr_max = 0
td_max = 0
for i in sides:
    if i[0] in [1, 2]:
        if lr_max < i[1]:
            lr_max = i[1]
    elif i[0] in [3, 4]:
        if td_max < i[1]:
            td_max = i[1]

side1 = 0
side2 = 0
for i in range(6):
    if i == 0:
        prev = 5
    else:
        prev = i-1
    if i == 5:
        next = 0
    else:
        next = i+1
    
    if sides[i][0] in [1, 2]:
        if sides[prev][1] < td_max and sides[next][1] < td_max:
            side1 = sides[i][1]
    elif sides[i][0] in [3, 4]:
        if sides[prev][1] < lr_max and sides[next][1] < lr_max:
            side2 = sides[i][1]

result = K * ( (lr_max * td_max) - (side1 * side2) )
print(result)
```



