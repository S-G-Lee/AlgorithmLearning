```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    fun_day = []
    for _ in range(N):
        fun_day.append(int(input()) - 1)
    
    fun_day.remove(0)
    count = 0
    i = 0
    while i < len(fun_day):
        check = 1
        for day in fun_day[:i]:
            if fun_day[i] % day == 0:
                check = 0
                break
        if check:
            count += 1
            i += 1
        else:
            fun_day.remove(fun_day[i])
    
    answer.append(count)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



