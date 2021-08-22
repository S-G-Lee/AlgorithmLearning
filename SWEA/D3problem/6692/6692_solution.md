```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N = int(input())
    
    random_boxes = []
    for _ in range(N):
        s = input().split()
        random_boxes.append([float(s[0]), int(s[1])])

    result = 0
    for box in random_boxes:
        result += box[0] * box[1]
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]:.6f}')
```



