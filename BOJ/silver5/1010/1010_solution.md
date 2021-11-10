```python
import sys
sys.stdin = open('boj/silver5/1010/input.txt')


def combination(n, m):
    temp = 1
    for i in range(1, n+1):
        temp *= i
    for i in range(1, m+1):
        temp //= i
    for i in range(1, n-m+1):
        temp //= i
    return temp


T = int(input())

for tc in range(1, T+1):
    N, M = map(int, input().split())
    result = combination(M, N)
    print(result)



```



