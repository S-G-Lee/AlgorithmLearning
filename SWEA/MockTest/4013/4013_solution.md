```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N = 4
    K = int(input())

    magnet = [list(map(int, input().split())) for _ in range(N)]
    commands = [list(map(int, input().split())) for _ in range(K)]
    for i in range(K):
        commands[i][0] -= 1
    
    for command in commands:
        rotation_queue = []
        rotation_queue.append(command)
        idx, rot = command
        while idx > 0:
            if magnet[idx][6] != magnet[idx-1][2]:
                rotation_queue.append([idx-1, -rot])
                idx -= 1
                rot = -rot
            else:
                break
        idx, rot = command
        while idx < N-1:
            if magnet[idx][2] != magnet[idx+1][6]:
                rotation_queue.append([idx+1, -rot])
                idx += 1
                rot = -rot
            else:
                break
        for idx, rot in rotation_queue:
            if rot == 1:
                item = magnet[idx].pop()
                magnet[idx].insert(0, item)
            else:
                item = magnet[idx].pop(0)
                magnet[idx].append(item)

    result = 0
    for i in range(N):
        result += magnet[i][0] * (2**(i))
    
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



