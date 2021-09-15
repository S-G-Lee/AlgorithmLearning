```python
def hashing(string_list):
    hash_list = []
    for string in string_list:
        hash_num = 0
        length = len(string)
        mult = 1
        for i in range(length-1,-1,-1):
            hash_num += mult*ord(string[i])
            mult *= 2
        hash_list.append(hash_num)
    return hash_list


T = int(input())

answer = []
for tc in range(1, T + 1):

    N, M = map(int, input().split())
    string_list1 = [input() for _ in range(N)]
    string_list2 = [input() for _ in range(M)]
    if N > M:
        string_list1, string_list2 = string_list2, string_list1
        N, M = M, N
    
    result = 0
    string_hash_list1 = hashing(string_list1)
    string_hash_list2 = hashing(string_list2)
    for i in range(N):
        for j in range(M):
            if string_hash_list1[i] == string_hash_list2[j]:
                if string_list1[i] == string_list2[j]:
                    result += 1
                    break

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



