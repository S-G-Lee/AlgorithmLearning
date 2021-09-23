```python
rec_list = [list(map(int, input().split())) for _ in range(4)] # rec_list[i] : x1, y1, x2, y2

board = [[0 for _ in range(100)] for _ in range(100)] # 최대 100 * 100 크기

for n in range(len(rec_list)):
    for i in range(rec_list[n][1], rec_list[n][3]):
        for j in range(rec_list[n][0], rec_list[n][2]):
            board[i][j] = 1

result = 0
for i in range(100):
    for j in range(100):
        result += board[i][j]

print(result)
```



