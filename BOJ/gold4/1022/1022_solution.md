```python
def find_num(n, lvl, i, j):    
    cur_i, cur_j = (lvl-1, lvl)
    if cur_i == i and cur_j == j:
        return n
    while cur_i != -lvl:
        cur_i -= 1
        n += 1
        if cur_i == i and cur_j == j:
            return n
    while cur_j != -lvl:
        cur_j -= 1
        n += 1
        if cur_i == i and cur_j == j:
            return n
    while cur_i != lvl:
        cur_i += 1
        n += 1
        if cur_i == i and cur_j == j:
            return n
    while cur_j != lvl:
        cur_j += 1
        n += 1
        if cur_i == i and cur_j == j:
            return n

r1, c1, r2, c2 = map(int, input().split())

board = [[0 for _ in range(c2-c1+1)] for _ in range(r2-r1+1)]

max_digit = 0
for i in range(r1, r2+1):
    for j in range(c1, c2+1):
        n = 1
        lvl = 0
        while lvl < max(abs(i), abs(j)):
            n += lvl*8
            lvl += 1
        if lvl == 0:
            num = 1
        else:
            num = find_num(n+1, lvl, i, j)
        temp_max_digit = len(str(num))
        if max_digit < temp_max_digit:
            max_digit = temp_max_digit
        board[i-r1][j-c1] = num

for i in range(len(board)):
    for j in range(len(board[i])):
        print(f'{board[i][j]:>{max_digit}}', end=' ')
    print()
```



