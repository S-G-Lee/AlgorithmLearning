```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    input_list = list(input().split())
    N = int(input_list[0])

    queue = [['A', 0] for _ in range(1000)]
    for i in range(0, N):
        queue[i] = [input_list[1 + 2*i], int(input_list[1 + 2*i + 1])]

    B_front = 0
    O_front = 0

    B_queue = []
    O_queue = []
    time = 0
    count = 0
    B_pos = 0
    O_pos = 0
    while True:
        
        if len(B_queue) == 0:
            while True:
                if queue[B_front][0] == 'O':
                    B_front += 1
                    continue
                break
            B_queue.append(queue[B_front][1])
        
        if len(O_queue) == 0:
            while True:
                if queue[O_front][0] == 'B':
                    O_front += 1
                    continue
                break
            O_queue.append(queue[O_front][1])
        
        if B_pos < B_queue[0]:
            B_pos += 1
        elif B_pos > B_queue[0]:
            B_pos -= 1
        else:
            if B_front < O_front:
                count += 1
                B_queue.pop()
                B_front += 1
        
        if O_pos < O_queue[0]:
            O_pos += 1
        elif O_pos > O_queue[0]:
            O_pos -= 1
        else:
            if O_front < B_front:
                count += 1
                O_queue.pop()
                O_front += 1

        if not count < N:
            break
        time += 1

    answer.append(time)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



