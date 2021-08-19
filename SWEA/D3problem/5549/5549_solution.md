```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    i = 1
    check = 0
    while True:
        if i * i * i == N:
            check = 1
            break
        elif i * i * i > N:
            break
        else:
            i += 1

    if check:
        result = i    
    else:
        result = -1
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



