```python
T = int(input())

for tc in range(1, T + 1):

    N, M = list(map(int, input().split()))

    fly_arr = []
    for i in range(N):
        temp = list(map(int, input().split()))
        fly_arr.append(temp)
    
    killfly_arr = [[0 for col in range(N-M+1)] for row in range(N-M+1)]   
    for i in range(N-M+1):
        for j in range(N-M+1):
            for k in range(M):
                for l in range(M):
                    killfly_arr[i][j] += fly_arr[i+k][j+l]
    
    
    result = max(map(max, killfly_arr))
    print(f'#{tc} {result}')
```



