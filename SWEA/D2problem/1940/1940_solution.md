```python
T = int(input())

def getvalues(acc_mode, val=0):
    return acc_mode, val

for tc in range(1, T + 1):

    N = int(input())
    
    acc_list = [0, 1, -1]

    velocity = 0
    acc = 0
    distance = 0

    for _ in range(N):

        acc_mode, val = getvalues(*list(map(int, input().split())))
        velocity += acc_list[acc_mode] * val
        velocity = max(velocity, 0)
        distance += velocity

    print(f'#{tc} {distance}')
```



