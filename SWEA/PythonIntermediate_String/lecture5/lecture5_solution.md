```python
T = int(input())

for tc in range(1, T + 1):   

    str1 = input()
    str2 = input()

    str1_dict = { char : 0 for char in str1}

    for char in str2:
        if char in str1_dict:
            str1_dict[char] = str1_dict[char] + 1
    
    maxcount = 0
    for count in str1_dict.values():
        if maxcount < count:
            maxcount = count
    
    print(f'#{tc} {maxcount}')
```



