```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N = int(input())
    line_list = []
    for _ in range(N):
        line_list.append(list(map(int, input().split())))
    
    count = 0

    for i in range(N):
        for j in range(i+1, N):
            if line_list[i][0] < line_list[j][0] and line_list[i][1] > line_list[j][1]:
                count += 1
            elif line_list[i][0] > line_list[j][0] and line_list[i][1] < line_list[j][1]:
                count += 1

    answer.append(count)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



