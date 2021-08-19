```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    hay = []
    for _ in range(N):
        hay.append(int(input()))

    avg = sum(hay) // len(hay)

    result = 0
    for num in hay:
        result += abs(num-avg)
    result = result // 2

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



