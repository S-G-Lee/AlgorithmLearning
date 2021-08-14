```python
def get_max_subsequence_length(numbers, len_log, idx):

    length = len(numbers)
    if length == 1:
        len_log[idx] = 1
    else:
        tempmax = 0
        for i in range(1, length):
            templength = 0
            if numbers[0] < numbers[i]:
                if len_log[idx+i] != -1:
                    templength = len_log[idx+i]
                else:
                    get_max_subsequence_length(numbers[i:], len_log, idx+i)
                    templength = len_log[idx+i]
            if tempmax < templength:
                tempmax = templength
            else:
                if len_log[idx+i] == -1:
                    get_max_subsequence_length(numbers[i:], len_log, idx+i)
        len_log[idx] = tempmax + 1

T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    numbers = list(map(int, input().split()))

    length_log = [-1 for _ in range(N)] # number의 i번째 항목부터 끝까지 봤을 떄 i번째 항목이 포함되는 최대 부분수열 길이

    get_max_subsequence_length(numbers, length_log, 0)

    result = max(length_log)

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



