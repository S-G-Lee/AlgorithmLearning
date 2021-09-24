```python
W, H = map(int, input().split())
p, q = map(int, input().split())
t = int(input())

t1 = t % (2*W)
t2 = t % (2*H)

dirx = 1
while t1 > 0:
    p = p + dirx
    t1 -= 1
    if p == W:
        dirx = -1
    elif p == 0:
        dirx = 1

diry = 1
while t2 > 0:
    q = q + diry
    t2 -= 1
    if q == H:
        diry = -1
    elif q == 0:
        diry = 1
    
print(p, q)
```



