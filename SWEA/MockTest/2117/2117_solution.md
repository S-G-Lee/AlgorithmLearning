```python
def cost(K):
    return (K * K) + ((K - 1) * (K - 1))


def is_possible(N, i, j):
    if (0 <= i < N) and (0 <= j < N):
        return True
    return False


T = int(input())

answer = []
for tc in range(1, T + 1):

    N, M = map(int, input().split())
    board = []
    total_house_num = 0
    for _ in range(N):
        temp = list(map(int, input().split()))
        for j in range(N):
            if temp[j] == 1:
                total_house_num += 1
        board.append(temp)
    
    K = 1
    max_house_num = 0
    while cost(K) < total_house_num * M:
        for i in range(N):
            for j in range(N):
                benefit = 0
                count = 0
                for di in range(-K+1, K):
                    for dj in range(-K+1, K):
                        if abs(di)+abs(dj) <= (K-1) and is_possible(N, i+di, j+dj) and board[i+di][j+dj] == 1:
                            benefit += M
                            count += 1
                if benefit >= cost(K) and count > max_house_num:
                    max_house_num = count
        K += 1
    
    result = max_house_num
    
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



