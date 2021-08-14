```python
def get_max_substring_length(str1, str2):

    table = [[0 for _ in range(len(str2)+1)] for _ in range(len(str1)+1)]

    for i in range(len(str1)+1):
        for j in range(len(str2)+1):

            if i == 0 or j == 0:
                table[i][j] = 0
            else:
                if str1[i-1] == str2[j-1]:
                    table[i][j] = table[i-1][j-1] + 1
                else:
                    table[i][j] = max(table[i-1][j], table[i][j-1])
    
    return table[len(str1)][len(str2)]


T = int(input())

answer = []
for tc in range(1, T + 1):

    str1, str2 = input().split()
    
    result = get_max_substring_length(str1, str2)

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



