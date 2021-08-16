```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    numbers = ''
    i = 0
    while i < N:
        temp = input().split()
        for char in temp:
            numbers += char
            i += 1

    number_combination = [0] * 10000 # 1000자리 숫자로는 조건에 맞는 수가 1000언저리에서 나올 것이기 떄문에 적당한 크기로 숫자조합을 카운트할 배열 생성
    for i in range(N):
        if i + 3 < N:
            number_combination[int(numbers[i:i+4])] = 1
        if i + 2 < N:
            number_combination[int(numbers[i:i+3])] = 1
        if i + 1 < N:
            number_combination[int(numbers[i:i+2])] = 1
        number_combination[int(numbers[i])] = 1

    result = 0
    i = 0
    while True:
        if number_combination[i] == 0:
            result = i
            break
        i += 1
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



