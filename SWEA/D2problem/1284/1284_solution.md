```python
T = int(input())

for tc in range(1, T + 1): 

    P, Q, R, S, W = map(int, input().split())

    A_price = P * W
    B_price = Q + max((W-R), 0) * S

    print(f'#{tc} {min(A_price, B_price)}')
```



