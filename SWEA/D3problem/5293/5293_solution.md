```python
# seq_log = [[[['-1' for i in range(21)] for j in range(21)] for k in range(21)] for l in range(21)]

# def find_sequence(seq_list):
#     global seq_log
#     a, b, c, d = seq_list
#     if a+b+c+d == 1:
#         if a == 1:
#             seq_log[a][b][c][d] = '00'
#             return '00'
#         elif b == 1:
#             seq_log[a][b][c][d] = '01'
#             return '01'
#         elif c == 1:
#             seq_log[a][b][c][d] = '10'
#             return '10'
#         else:
#             seq_log[a][b][c][d] = '11'
#             return '11'
#     else:
#         if a > 0:
#             if seq_log[a-1][b][c][d] != '-1':
#                 sub_seq = seq_log[a-1][b][c][d]
#             else:
#                 sub_seq = find_sequence([a-1, b, c, d])                
#             if len(sub_seq) > 0 and sub_seq[-1] == '0':
#                 seq_log[a][b][c][d] = sub_seq + '0'
#                 return seq_log[a][b][c][d]
#         if b > 0:
#             if seq_log[a][b-1][c][d] != '-1':
#                 sub_seq = seq_log[a][b-1][c][d]
#             else:
#                 sub_seq = find_sequence([a, b-1, c, d])
#             if len(sub_seq) > 0 and sub_seq[-1] == '0':
#                 seq_log[a][b][c][d] = sub_seq + '1'
#                 return seq_log[a][b][c][d]
#         if c > 0:
#             if seq_log[a][b][c-1][d] != '-1':
#                 sub_seq = seq_log[a][b][c-1][d]
#             else:
#                 sub_seq = find_sequence([a, b, c-1, d])
#             if len(sub_seq) > 0 and sub_seq[-1] == '1':
#                 seq_log[a][b][c][d] = sub_seq + '0'
#                 return seq_log[a][b][c][d]
#         if d > 0:
#             if seq_log[a][b][c][d-1] != '-1':
#                 sub_seq = seq_log[a][b][c][d-1]
#             else:
#                 sub_seq = find_sequence([a, b, c, d-1])
#             if len(sub_seq) > 0 and sub_seq[-1] == '1':
#                 seq_log[a][b][c][d] = sub_seq + '1'
#                 return seq_log[a][b][c][d]
#         return ''

# T = int(input())

# answer = []
# for tc in range(1, T + 1):

#     A, B, C, D = map(int, input().split())
#     # A, B, C, D are the number of the sequences 00, 01, 10, 11, respectively
#     result = find_sequence([A, B, C, D])
#     if len(result) == 0:
#         result = 'impossible'
    
#     answer.append(result)

# for tc in range(1, T+1):
#     print(f'#{tc} {answer[tc-1]}')

T = int(input())

answer = []
for tc in range(1, T + 1):

    A, B, C, D = map(int, input().split())
    # A, B, C, D are the number of the sequences 00, 01, 10, 11, respectively
    result = 'impossible'
    if (B == 0 and C == 0) and(A != 0 and D != 0):
        pass
    elif (abs(B-C) > 1):
        pass
    elif A == B == C == D == 0:
        pass
    else:
        result = ''
        if B > C:
            result += '0'
            result += '0' * A
            result += '10' * C
            result += '1'
            result += '1' * D
        elif B < C:
            result += '1'
            result += '1' * D
            result += '01' * B
            result += '0'
            result += '0' * A
        else:
            if A > 0:
                result += '0'
                result += '0' * A
                if D > 0:
                    result += '1'
                    result += '1' * D
                    result += '0'
                    result += '10' * (B-1)
                else:
                    result += '10' * B
            else:
                result += '1'
                result += '1' * D
                result += '01' * B

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



