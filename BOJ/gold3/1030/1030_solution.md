```python

def fractal(s, N, K, i, j):
    lvl = 0
    while lvl < s:
        i_quotient, i_remainder = divmod(i, (N**(s-lvl-1)))
        j_quotient, j_remainder = divmod(j, (N**(s-lvl-1)))
        if ((N-K)//2-1 < i_quotient < (N+K)//2) and ((N-K)//2-1 < j_quotient < (N+K)//2):
            return 1
        i = i_remainder
        j = j_remainder
        lvl += 1
    return 0


s, N, K, R1, R2, C1, C2 = map(int, input().split())

for i in range(R1, R2+1):
    for j in range(C1, C2+1):
        print(fractal(s, N, K, i, j), end='')
    print()
```



