```python
def eratosthenes(a, b):
    
    primes = set(range(a, b+1))
    max_factor = int(b ** (1/2))
    factors = set(range(2, max_factor + 1))
    while factors:
        i = list(factors)[0]
        not_primes = set(range(2*i, b+1, i))
        primes = primes - not_primes
        factors = factors - not_primes - set({i})
    return sorted(primes)

num_to_prime_index = [0] * 1000001
all_primes = eratosthenes(2, 1000000)
length = len(num_to_prime_index)
plength = len(all_primes)
i = 0
primeidx = 0

while i < length:
    if primeidx >= plength:
        pass
    elif i > all_primes[primeidx]:
        primeidx += 1
    num_to_prime_index[i] = primeidx
    i += 1
    

T = int(input())

answer = []
for tc in range(1, T + 1):

    D, A, B = map(int, input().split())
    D = str(D)
    
    i = num_to_prime_index[A]
    j = num_to_prime_index[B]
    if B in all_primes:
        primes = list(map(str, all_primes[i:j+1]))
    else:
        primes = list(map(str, all_primes[i:j]))
    
    total = 0
    if B >= 2:
        for num in primes:
            if D in num:
                total += 1

    answer.append(total)
    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



