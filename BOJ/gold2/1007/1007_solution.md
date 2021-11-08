```python
from itertools import combinations


def distance(x, y):
    return ((x**2) + (y**2))**(1/2)


T = int(input())

for tc in range(1, T+1):
    N = int(input())
    X = []
    Y = []
    for _ in range(N):
        x, y = map(int, input().split())
        X.append(x)
        Y.append(y)
    
    visited = [0] * N
    result = 100000000

    combis = combinations(range(0, N), N//2)
    for combi in combis:
        x, y = 0, 0
        for i in range(N):
            if i in combi:
                x += X[i]
                y += Y[i]
            else:
                x -= X[i]
                y -= Y[i]
        dist = distance(x, y)
        if result > dist:
            result = dist

    print(result)
```



