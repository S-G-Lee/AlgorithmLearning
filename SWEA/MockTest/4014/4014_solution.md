```python
def is_possible(N, i, j):
    if (0 <= i < N) and (0 <= j < N):
        return True
    return False


T = int(input())

answer = []
for tc in range(1, T + 1):

    N, X = map(int, input().split())
    field = [list(map(int, input().split())) for _ in range(N)]

    result = 0
    for i in range(N):
        installed = [0] * N
        prev = 0
        
        for j in range(N):
            if field[i][prev] == field[i][j] - 1:
                flag = True
                for k in range(prev, prev - X, -1):
                    if is_possible(N, i, k) and field[i][k] == field[i][prev] and not installed[k]:
                        continue
                    else:
                        break
                else:
                    for k in range(prev, prev - X, -1):
                        installed[k] = 1
                    flag = False
                
                if flag:
                    break
            elif field[i][prev] == field[i][j] + 1:
                flag = True
                for k in range(j, j + X):
                    if is_possible(N, i, k) and field[i][k] == field[i][j] and not installed[k]:
                        continue
                    else:
                        break
                else:
                    for k in range(j, j + X):
                        installed[k] = 1
                    flag = False

                if flag:
                    break
            elif field[i][prev] == field[i][j]:
                pass
            else:
                break

            prev = j

        else:
            result += 1

    for j in range(N):
        installed = [0] * N
        prev = 0
        
        for i in range(N):
            if field[prev][j] == field[i][j] - 1:
                flag = True
                for k in range(prev, prev - X, -1):
                    if is_possible(N, k, j) and field[k][j] == field[prev][j] and not installed[k]:
                        continue
                    else:
                        break
                else:
                    for k in range(prev, prev - X, -1):
                        installed[k] = 1
                    flag = False
                
                if flag:
                    break
            elif field[prev][j] == field[i][j] + 1:
                flag = True
                for k in range(i, i + X):
                    if is_possible(N, k, j) and field[k][j] == field[i][j] and not installed[k]:
                        continue
                    else:
                        break
                else:
                    for k in range(i, i + X):
                        installed[k] = 1
                    flag = False

                if flag:
                    break
            elif field[prev][j] == field[i][j]:
                pass
            else:
                break

            prev = i
            
        else:
            result += 1
    
    answer.append(result)

for tc in range(1, T + 1):
    print(f'#{tc} {answer[tc-1]}')
```



