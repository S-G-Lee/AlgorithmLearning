```python
T = int(input())

for tc in range(1, T + 1):

    N, K = list(map(int, input().split()))
    score_list = [ list(map(int, input().split())) for _ in range(N)]
    
    effective_score_list = [0] * N # [(order1, score1), (order2, score2), ...] structure will be made
    for idx, val in enumerate(score_list):
        effective_score_list[idx] = [idx, val[0] * 0.35 + val[1] * 0.45 + val[2] * 0.2]
    
    effective_score_list.sort(key=lambda x:x[1], reverse=True)
    grade_list = ['A+', 'A0', 'A-', 'B+', 'B0', 'B-', 'C+', 'C0', 'C-', 'D0']

    result = ''
    for idx, i in enumerate(effective_score_list):
        if K - 1 == i[0]:
            result = grade_list[idx // (N // 10)]
            break
    
    print(f'#{tc} {result}')
```



