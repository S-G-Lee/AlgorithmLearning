```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    scores = list(map(int, input().split()))

    for i in range(len(scores)):
        if scores[i] < 40:
            scores[i] = 40

    result = sum(scores)//len(scores)

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



