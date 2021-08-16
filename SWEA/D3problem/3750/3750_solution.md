```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    
    while N >= 10:

        N = sum(map(int, str(N)))

    result = N
        
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



