```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    A, B =map(int, input().split())

    result = A + B

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



