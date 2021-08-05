```python
T = int(input())

for tc in range(1, T + 1):

    h1, m1, h2, m2 = list(map(int, input().split()))

    sum_h = (h1 + h2) % 12
    sum_m = (m1 + m2) % 60
    if m1 + m2 >= 60:
        sum_h += 1
    
    print(f'#{tc} {sum_h} {sum_m}')
```



