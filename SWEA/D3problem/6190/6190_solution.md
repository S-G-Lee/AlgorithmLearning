```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N = int(input())

    numbers = list(map(int, input().split()))

    mult_list = [numbers[i] * numbers[j] for i in range(N) for j in range(N) if i < j]

    result = -1
    for num in mult_list:
        word = str(num)
        check = 1
        for i in range(len(word)-1):
            if word[i] > word[i+1]:
                check = 0
                break
        if check:
            if result < num:
                result = num
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



