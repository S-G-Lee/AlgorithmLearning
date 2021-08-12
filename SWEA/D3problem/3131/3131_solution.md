```python
T = 1

answer = []
for tc in range(1, T + 1):

    N = 1000000

    numbers = [1] * (N+1)
    numbers[0] = 0
    numbers[1] = 0
    for i in range(2, 1001):
        for j in range(2*i, N+1, i):
            numbers[j] = 0
    
    primes = []
    for i in range(2, N+1):
        if numbers[i] == 1:
            primes.append(i)
    numbers = sorted(list(primes))
    result = ' '.join(map(str, numbers))

    answer.append(result)

for tc in range(1, T+1):
    print(f'{answer[tc-1]}')
```



