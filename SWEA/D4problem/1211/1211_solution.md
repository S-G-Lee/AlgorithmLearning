```python
T = 10

answer = []
for tc in range(1, T + 1):

    nothing = int(input())
    ladder = []
    for _ in range(100):
        ladder.append(list(map(int, input().split())))
    
    result = 0
    min_dist = 10000000
    for start in range(100):
        if ladder[0][start] == 1:
            i = 0
            j = start
            distance = 1
            while i < 100:
                if j-1 >= 0 and ladder[i][j-1] == 1:
                    while j-1 >= 0 and ladder[i][j-1] == 1:
                        j -= 1
                        distance += 1
                elif j+1 < 100 and ladder[i][j+1] == 1:
                    while j+1 < 100 and ladder[i][j+1] == 1:
                        j += 1
                        distance += 1
                i += 1
                distance += 1
            if min_dist >= distance:
                min_dist = distance
                result = start

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



