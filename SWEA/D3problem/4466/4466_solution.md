```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, K = map(int, input().split())
    numbers = list(map(int, input().split()))

    numbers.sort(reverse=True)

    result = sum(numbers[:K])

    answer.append(result)
    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



