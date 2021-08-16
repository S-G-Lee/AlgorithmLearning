```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    D, H, M = map(int, input().split())

    D = D - 11
    H = H - 11
    M = M - 11

    result = D * 1440 + H * 60 + M
    if result < 0:
        result = -1
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



