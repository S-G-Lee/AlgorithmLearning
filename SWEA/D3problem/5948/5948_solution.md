```python
T = int(input())

answer = []
for tc in range(1, T + 1):    

    numbers = list(map(int, input().split()))

    sum_set = set()
    for i in range(7):
        for j in range(i+1, 7):
            for k in range(j+1, 7):
                sum_set.add(numbers[i]+numbers[j]+numbers[k])
    
    sum_list = list(sum_set)
    sum_list.sort()
    result = sum_list[-5]
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



