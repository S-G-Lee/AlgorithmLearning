```python
N = int(input())

matrix = [[0 for _ in range(N)] for _ in range(N)]
numerator = [1] * N
denominator = [1] * N

for i in range(N-1):
    a, b, p, q = map(int, input().split())
    matrix[i][a] = q
    matrix[i][b] = -p

matrix[-1][0] = 1

visited = [0] * N
queue = []
queue.append(0)
visited[N-1] = 1
while queue:
    w = queue.pop()
    for v in range(N):
        if matrix[v][w] != 0 and not visited[v]:
            visited[v] = 1

            k = 0
            for i in range(N):
                if i != w and matrix[v][i] != 0:
                    k = i
                    break
            numerator[i] *= abs(matrix[v][w]) * numerator[w]
            denominator[i] *= abs(matrix[v][i]) * denominator[w]

            queue.append(i)

mass = [1] * N
total_denom = 1
for i in range(N):
    total_denom *= denominator[i]
for i in range(N):
    mass[i] *= total_denom * numerator[i]
    mass[i] //= denominator[i]

for n in (2, 3, 5, 7):
    flag = True
    while flag:
        for i in range(N):
            if mass[i] % n != 0:
                flag = False
                break
        else:
            for i in range(N):
                mass[i] //= n

print(*mass)
```



