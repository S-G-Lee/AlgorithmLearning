```python
T = 10

answer = []
for tc in range(1, T + 1):

    N, sentence = input().split()
    N = int(N)

    pwd = []
    for i in range(N):
        if len(pwd) == 0:
            pwd.append(sentence[i])
        elif pwd[-1] == sentence[i]:
            pwd.pop(-1)
        else:
            pwd.append(sentence[i])

    result = ''.join(pwd)

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



