```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, M = map(int, input().split())

    words1 = input().split()
    words2 = input().split()

    set1 = set(words1)
    set2 = set(words2)
    set3 = set1 & set2
    result = len(set3)

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



