```python
T = 10

answer = []
for tc in range(1, T + 1):

    N = int(input())

    numbers = list(map(int, input().split()))

    minnum = min(numbers)
    common_sub = ((minnum//15)-1) * 15
    for i in range(len(numbers)):
        numbers[i] -= common_sub
    
    cycle = 1
    while True:
        numbers[0] -= cycle
        a = numbers[0]
        if a < 0:
            a = 0
        numbers.pop(0)
        numbers.append(a)
        if a == 0:
            break

        cycle += 1
        if cycle > 5:
            cycle = 1

    result = ' '.join(map(str, numbers))

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



