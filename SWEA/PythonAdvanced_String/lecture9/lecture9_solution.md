```python
def create_suffix_list(string):
    
    suffix_list = []
    string = string + '$'
    length = len(string)
    for i in range(length):
        temp = ''
        for j in range(i, length):
            temp += string[j]
        suffix_list.append(temp)
    suffix_list.sort()
    return suffix_list


def create_LCP_list(suf_list):
    lcp = []
    lcp.append(0)
    for i in range(1, len(suf_list)):
        idx = 0
        while True:
            if suf_list[i-1][idx] == '$' or suf_list[i][idx] == '$' or suf_list[i-1][idx] != suf_list[i][idx]:
                break
            idx += 1
        lcp.append(idx)
    return lcp


T = int(input())

answer = []
for tc in range(1, T + 1):

    N, string = input().split()
    N = int(N)

    suf_list = create_suffix_list(string)
    lcp = create_LCP_list(suf_list)

    result = None
    cur_order = 0    
    idx = 1
    while True:
        if N - cur_order <= len(suf_list[idx]) - 1 - lcp[idx]:
            result = suf_list[idx][0] + ' ' + str(lcp[idx]+N-cur_order)
            break
        else:
            cur_order += len(suf_list[idx]) - 1 - lcp[idx]
            idx += 1

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



