```python
W, H = map(int, input().split())
N = int(input())
coords = []
for i in range(N):
    coords.append(list(map(int, input().split())))
    # coords[i][0] = 1 : λΆ, 2 : λ¨, 3: μ, 4 : λ
start = list(map(int, input().split()))

result = 0
for coord in coords:
    if start[0] == 1:
        if coord[0] == 1:
            result += abs(start[1] - coord[1])
        elif coord[0] == 2:
            result += H + min((W - start[1]) + (W - coord[1]), start[1] + coord[1])
        elif coord[0] == 3:
            result += start[1] + coord[1]
        else:            
            result += (W - start[1]) + coord[1]
    elif start[0] == 2:
        if coord[0] == 1:
            result += H + min((W - start[1]) + (W - coord[1]), start[1] + coord[1])
        elif coord[0] == 2:
            result += abs(start[1] - coord[1])
        elif coord[0] == 3:
            result += start[1] + (H - coord[1])
        else:            
            result += (W - start[1]) + (H - coord[1])
    elif start[0] == 3:
        if coord[0] == 1:
            result += start[1] + coord[1]
        elif coord[0] == 2:
            result += (H - start[1]) + coord[1]
        elif coord[0] == 3:
            result += abs(start[1] - coord[1])
        else:            
            result += W + min((H - start[1]) + (H - coord[1]), start[1] + coord[1])
    else:
        if coord[0] == 1:
            result += start[1] + (W - coord[1])
        elif coord[0] == 2:
            result += (H - start[1]) + (W - coord[1])
        elif coord[0] == 3:
            result += W + min((H - start[1]) + (H - coord[1]), start[1] + coord[1])
        else:            
            result += abs(start[1] - coord[1])    

print(result)

```



