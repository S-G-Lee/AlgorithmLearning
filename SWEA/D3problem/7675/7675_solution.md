```python
T = int(input())

answer = []
for tc in range(1, T + 1): 
    
    N = int(input())
    
    words = input().split()

    count_list = []
    count = 0
    for word in words:
        if word[0].isupper():
            check = 1
            for char in word[1:]:
                if char.isupper() or char.isdigit():
                    check = 0
                    break
            if check:
                count += 1
        if word[-1] in ['.', '!', '?']:
            count_list.append(count)
            count = 0
    
    result = ' '.join(map(str, count_list))

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



