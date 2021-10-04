```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    a, b = map(int, input().split())

    x = b - a
    K = x*(x-1)//2 - a
    
    result = K
    
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



