```python
def distance(i1, j1, i2, j2):
    return abs(i2-i1) + abs(j2-j1)


T = int(input())

answer = []
for tc in range(1, T + 1):

    M, A = map(int, input().split())

    move_A = list(map(int, input().split()))
    move_B = list(map(int, input().split()))
    bc = [list(map(int, input().split())) for _ in range(A)]

    delta = [(0, 0), (-1, 0), (0, 1), (1, 0), (0, -1)]

    pos_A = [1, 1]
    pos_B = [10, 10]
    time = 0
    result = 0
    while True:
        A_bc_list = []
        B_bc_list = []
        for i in range(len(bc)):
            if distance(pos_A[0], pos_A[1], bc[i][1], bc[i][0]) <= bc[i][2]:
                A_bc_list.append(i)
            if distance(pos_B[0], pos_B[1], bc[i][1], bc[i][0]) <= bc[i][2]:
                B_bc_list.append(i)
        
        if len(A_bc_list) == 0:
            tempmax = 0
            for i in B_bc_list:
                if tempmax < bc[i][3]:
                    tempmax = bc[i][3]
            result += tempmax
        elif len(B_bc_list) == 0:
            tempmax = 0
            for i in A_bc_list:
                if tempmax < bc[i][3]:
                    tempmax = bc[i][3]
            result += tempmax
        else:
            tempmax_A = 0
            tempidx_A = -1
            for i in A_bc_list:
                if tempmax_A < bc[i][3]:
                    tempmax_A = bc[i][3]
                    tempidx_A = i
            tempmax_B = 0
            tempidx_B = -1
            for i in B_bc_list:
                if tempmax_B < bc[i][3]:
                    tempmax_B = bc[i][3]
                    tempidx_B = i

            if tempidx_A == tempidx_B:
                A_bc_list.remove(tempidx_A)
                B_bc_list.remove(tempidx_B)
                temptempmax_A = 0
                for i in A_bc_list:
                    if temptempmax_A < bc[i][3]:
                        temptempmax_A = bc[i][3]
                temptempmax_B = 0
                for i in B_bc_list:
                    if temptempmax_B < bc[i][3]:
                        temptempmax_B = bc[i][3]

                result += tempmax_A
                result += max(temptempmax_A, temptempmax_B)
            else:
                result += tempmax_A + tempmax_B


        if time >= M:
            break
        time += 1
        di_A, dj_A = delta[move_A[time-1]]
        di_B, dj_B = delta[move_B[time-1]]
        pos_A[0] += di_A
        pos_A[1] += dj_A
        pos_B[0] += di_B
        pos_B[1] += dj_B
    
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')

```



