```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    A, B, C, D = map(int, input().split())

    time = [0] * 101

    for i in range(A, B):
        time[i] += 1
    
    result = 0
    for i in range(C, D):
        if time[i] == 1:
            result += 1
            
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')

```



