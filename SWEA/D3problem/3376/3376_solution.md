```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    
    pn = [1, 1, 1, 2, 2, 3, 4, 5, 7, 9]

    if N <= 10:
        result = pn[N-1]
    else:
        for i in range(10, N):
            new_pn = pn[-1] + pn[-5]
            pn.append(new_pn)

    result = pn[N-1]

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



