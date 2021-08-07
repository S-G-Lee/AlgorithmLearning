```python
T = 10

answer = []
for tc in range(1, T + 1):

    N = int(input())
    boxes = list(map(int, input().split()))
    
    result = 0

    for _ in range(N):
        box_min = min(boxes)
        box_max = max(boxes)
        if box_max - box_min > 1:
            boxes[boxes.index(box_min)] += 1
            boxes[boxes.index(box_max)] -= 1
        else:
            break

    box_min = min(boxes)
    box_max = max(boxes)
    result = box_max - box_min

    answer.append(result)    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



