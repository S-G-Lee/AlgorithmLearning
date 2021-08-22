```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N, A, B = map(int, input().split())

    max_n = min(A, B)
    min_n = max(A + B - N, 0)

    answer.append([max_n, min_n])

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1][0]} {answer[tc-1][1]}')
```



