```python
C, R = map(int, input().split())

board = [[0 for _ in range(C)] for _ in range(R)]
K = int(input())

direction = [[-1, 0], [0, 1], [1, 0], [0, -1]]
diridx = 0
diri, dirj = direction[diridx]
count = 1
size = C*R
i, j = R-1, 0
while count <= size:
    board[i][j] = count
    if count == K:
        break
    count += 1

    if not ( (0 <= i + diri < R) and (0 <= j + dirj < C) and (board[i + diri][j + dirj] == 0) ):
        diridx = (diridx + 1) % 4
        diri, dirj = direction[diridx]
    
    i, j = i + diri, j + dirj

if count > size:
    result = 0
else:
    result = ' '.join(map(str, [j+1, R-i]))
print(result)
```



