```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N = int(input())
    route_list = []
    for _ in range(N):
        route_list.append(list(map(int, input().split())))
    P = int(input())
    station_list = []
    for _ in range(P):
        station_list.append(int(input()))

    station_count = [0] * 5001

    for a, b in route_list:
        for i in range(a, b+1):
            station_count[i] += 1
    
    result = []
    for station in station_list:
        result.append(station_count[station])
    
    result = ' '.join(map(str, result))    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



