```python
from itertools import product


def distance(pr, pc, sr, sc):
    return abs(pr-sr) + abs(pc-sc)


T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    floor = []
    exit = []
    people = []
    for i in range(N):
        temp = list(map(int, input().split()))
        for j in range(N):
            if temp[j] == 1:
                people.append((i, j))
            elif temp[j] >= 2:
                # time, i, j
                exit.append([temp[j], i, j])
        
    people_goto_list = list(product(range(len(exit)), repeat=len(people)))
    
    min_time = 10000000
    for people_goto in people_goto_list:
        exit_queue = [[] for _ in range(len(exit))]
        for i in range(len(people)):
            exit_queue[people_goto[i]].append(distance(people[i][0], people[i][1], exit[people_goto[i]][1], exit[people_goto[i]][2]) + exit[people_goto[i]][0])

        for i in range(len(exit_queue)):
            exit_queue[i].sort()
        
        time = 0
        left = len(people)
        while left > 0:
            for i in range(len(exit)):
                while len(exit_queue[i]) > 0 and exit_queue[i][0] == time:
                    if len(exit_queue[i]) > 3 and exit_queue[i][3] < time + exit[i][0]:
                        exit_queue[i][3] = time + exit[i][0]
                    exit_queue[i].pop(0)
                    left -= 1
            time += 1
        if min_time > time:
            min_time = time                

    result = min_time
    
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



