```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N = int(input())
    num_list = list(map(int, input().split()))

    avg = sum(num_list) / len(num_list)

    count = 0
    for i in num_list:
        if i <= avg:
            count += 1

    answer.append(count)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



