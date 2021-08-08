```python
def power_recursive(a, b):
    if b == 0:
        return 1
    elif b == 1:
        return a
    else:
        c = power_recursive(a, (b//2))
        if b % 2 == 0:
            d = power_recursive(a, (b//2))
        else:
            d = power_recursive(a, (b//2) + 1)
        return c*d

# T = int(input())
T = 10

answer = []
for tc in range(1, T + 1):

    nothing = int(input())
    N, M = map(int, input().split())

    result = power_recursive(N, M)

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



