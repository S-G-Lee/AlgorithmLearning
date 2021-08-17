```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    word = input()
    H = int(input())
    pos_list = list(map(int, input().split()))

    length = len(word)
    hyphen_num = [0] * (length + 1)

    for i in pos_list:
        hyphen_num[i] += 1
    
    result = ''
    for i in range(length):
        result += '-' * hyphen_num[i]
        result += word[i]
    result += '-' * hyphen_num[-1]

    answer.append(result)
    

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



