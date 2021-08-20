```python
def eratosthenes(n):
    num = set(range(2, n+1))
 
    for i in range(2, n+1):
        if i in num:
            num -= set(range(2*i, n+1, i))

    return sorted(list(num))

T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N = int(input())

    prime_numbers = eratosthenes(N)
    length = len(prime_numbers)
    
    count = 0
    for i in range(length):
        for j in range(i,length):
            for k in range(j, length):
                if prime_numbers[i] + prime_numbers[j] + prime_numbers[k] == N:
                    count += 1

    answer.append(count)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



