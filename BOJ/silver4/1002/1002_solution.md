```python
def distance_square(x, y):
    return ((x**2) + (y**2))


T = int(input())

for tc in range(1, T+1):
    x1, y1, r1, x2, y2, r2 = map(int, input().split())
    dist_square = distance_square((x2-x1), (y2-y1))
    if r1**2 == r2**2 and dist_square == 0:
        print(-1)
    elif dist_square > (r1+r2)**2 or dist_square < (r2 - r1)**2 :
        print(0)
    elif dist_square == (r1+r2)**2 or dist_square == abs(r1-r2)**2:
        print(1)
    else:
        print(2)
```



