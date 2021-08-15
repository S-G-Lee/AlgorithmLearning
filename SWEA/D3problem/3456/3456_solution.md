```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    a, b, c = map(int, input().split())

    result = 0

    if a == b:
        result = c
    elif a == c:
        result = b
    else:
        result = a

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



