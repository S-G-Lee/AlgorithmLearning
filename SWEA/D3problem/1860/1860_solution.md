```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, M, K = map(int, input().split())

    people = list(map(int, input().split()))

    people_count = [0] * 20000

    for person in people:
        people_count[person] += 1
    
    total_bread = 0
    total_people = 0
    result = 'Possible'
    for i in range(20000):
        if i % M == 0 and i > 0:
            total_bread += K
        total_people += people_count[i]

        if total_people > total_bread:
            result = 'Impossible'
            break
    
        if total_people >= N:
            break   

    answer.append(result)
    
for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



