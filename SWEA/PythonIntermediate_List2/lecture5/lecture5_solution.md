```python
casenum = int(input())

for case in range(1, casenum+1):
    
    recnum = int(input())
    field = [[0 for col in range(10)] for row in range(10)] # field that have color information, 1 : red, 2 : blue, 3 : purple
    
    for i in range(recnum):
        r1, c1, r2, c2, color = list(map(int, input().split()))
        for i in range(r1, r2+1):
            for j in range(c1, c2+1):
                if field[i][j] == 0:
                    field[i][j] = color
                elif field[i][j] != color:
                    field[i][j] = 3

    purplearea = 0
    for i in range(10):
        for j in range(10):
            if field[i][j] == 3:
                purplearea += 1

    print(f'#{case} {purplearea}')
```



