```python
T = int(input())

for tc in range(1, T + 1): 

    cur_tc = int(input())
    num_list = list(map(int, input().split()))

    num_count_list = [0] * 101 # 0 ~ 100 range
    
    for i in num_list:
        num_count_list[i] += 1
    
    maxnum = 0
    result = 0
    for idx, val in enumerate(num_count_list):
        if maxnum <= val:
            maxnum = val
            result = idx

    print(f'#{cur_tc} {result}')
```



