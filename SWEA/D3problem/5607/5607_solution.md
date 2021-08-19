```python
PRIME = 1234567891

T = int(input())

def power(x, y):
    global PRIME
    if y == 0:
        return 1
    elif y == 1:
        return x
    else:
        a = power(x, y//2)
        a = a % PRIME
        if y % 2 == 1:
            b = a * a * x
        else:
            b = a * a
        b = b % PRIME
        return b

answer = []
for tc in range(1, T + 1):

    #페르마의 소정리
    #1234567891로 나눈 나머지를 구해야함. 이 숫자는 소수임
    N, R = map(int, input().split())

    #nCr = n!/(r!(n-r)!)
    numerator = 1
    for i in range(1,N+1):
        numerator = numerator * i
        numerator = numerator % PRIME
    denominator = 1
    for i in range(1, R+1):
        denominator = denominator * i
        denominator = denominator % PRIME
    for i in range(1, N-R+1):
        denominator = denominator * i
        denominator = denominator % PRIME

    denominator = power(denominator, PRIME-2)

    result = (numerator * denominator) % PRIME

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



