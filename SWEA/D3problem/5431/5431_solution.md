```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, K = map(int, input().split())
    submit_list = list(map(int, input().split()))

    check_list = [0] * N

    for i in submit_list:
        check_list[i-1] = 1
    
    absent_list = []
    for i in range(N):
        if check_list[i] == 0:
            absent_list.append(i+1) 
    
    result = ' '.join(map(str, absent_list))
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



