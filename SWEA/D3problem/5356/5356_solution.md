```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    words = []
    for _ in range(5):
        words.append(input())
    
    result = ''
    idx = 0
    while words:

        for i in words:
            result += i[idx]
        idx += 1
        
        idx2 = 0
        while idx2 < len(words):
            if idx < len(words[idx2]):
                idx2 += 1
            else:
                words.pop(idx2)
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



