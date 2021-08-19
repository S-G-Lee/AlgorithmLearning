```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    result = []
    for _ in range(N):
        result.append('1/'+str(N))

    result = ' '.join(map(str, result))
    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



