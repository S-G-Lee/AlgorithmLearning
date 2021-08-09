```python
T = 10

answer = []
for tc in range(1, T + 1):

    N = int(input())

    numbers = input().split()

    M = int(input())

    commands = input().split()

    idx = 0
    count = 0
    while count < M:
        if commands[idx] == 'I':
            x, y = int(commands[idx+1]), int(commands[idx+2])
            idx += 3
            for i in range(y):
                numbers.insert(x+i, commands[idx])
                idx += 1
        elif commands[idx] == 'A':
            y = int(commands[idx+1])
            idx += 2
            for _ in range(y):
                numbers.append(commands[idx])
                idx += 1
        elif commands[idx] == 'D':
            x, y = int(commands[idx+1]), int(commands[idx+2])
            idx += 3
            for _ in range(y):
                numbers.pop(x)
        count += 1

    result = ' '.join(numbers[:10])

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



