```python
def fibo(n):
    global callcount
    if n < 2:
        if n == 1:
            callcount[1] = [0, 1]
        elif n == 0:
            callcount[0] = [1, 0]
    else:
        if not callcount[n]:
            if not callcount[n-1]:
                fibo(n-1)
            if not callcount[n-2]:
                fibo(n-2)
            callcount[n] = [0, 0]
            callcount[n][1] = callcount[n-1][1] + callcount[n-2][1]
            callcount[n][0] = callcount[n-1][0] + callcount[n-2][0]


T = int(input())

for tc in range(1, T+1):

    N = int(input())

    callcount = [[] for _ in range(41)]
    fibo(N)

    result = callcount[N]

    print(*result)
```



