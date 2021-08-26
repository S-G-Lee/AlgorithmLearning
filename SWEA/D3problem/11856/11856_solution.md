```python
T = int(input())

for tc in range(1, T + 1): 

    word = input()

    word_dict = {}
    
    for char in word:
        if char not in word_dict:
            word_dict[char] = 1
        else:
            word_dict[char] += 1
    
    result = 'No'
    if len(word_dict) == 2:
        check = 1
        for i in word_dict.values():
            if i != 2:
                check = 0
                break
        if check:
            result = 'Yes'
    
    print(f'#{tc} {result}')
```



