```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    clap_condition = list(map(int, input()))
    length = len(clap_condition)

    i = 0
    clap_people = 0
    result = 0
    while i < length:        
        clap_people += clap_condition[i]
        if clap_people > 0:
            clap_people -= 1
        else:
            result += 1
        i += 1
        
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



