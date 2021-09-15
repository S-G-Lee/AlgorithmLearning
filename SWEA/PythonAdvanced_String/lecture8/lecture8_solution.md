```python
T = int(input())

answer = []
for tc in range(1, T + 1):

    N, M = map(int, input().split())
    str_list1 = [input() for _ in range(N)]
    str_list2 = [input() for _ in range(M)]

    # suf_list1 = []
    # for string in str_list1:
    #     suf_list1.append(create_suffix_list(string))
    
    # lcp1 = create_LCP_list(suf_list1)
    result = 0
    for prefix in str_list2:
        for string in str_list1:
            if len(prefix) <= len(string):
                for i in range(len(prefix)):
                    if prefix[i] != string[i]:
                        break
                else:
                    result += 1
                    break

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



