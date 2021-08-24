```python
T = int(input())

answer = []
for tc in range(1, T + 1): 

    word = input()

    word_dict = {}
    for char in word:
        if char not in word_dict:
            word_dict[char] = 1
        else:
            word_dict[char] += 1
    
    result = []
    for key, val in word_dict.items():
        if val % 2 != 0:
            result.append(key)
    result.sort()

    if len(result):
        result = ''.join(map(str, result))
    else:
        result = 'Good'
    
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



