```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    
    s1 = N*(N+1)//2
    s2 = N*(N+1) - N
    s3 = N*(N+1)

    result = ' '.join(map(str, [s1, s2, s3]))

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



