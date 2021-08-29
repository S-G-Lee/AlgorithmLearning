```python
T = int(input())

for tc in range(1, T + 1):

    str_N = input()
    str_M = input()

    length_N = len(str_N)
    length_M = len(str_M)

    pivot_M = length_N
    result = 0
    while pivot_M < length_M:

        pivot_N = length_N - 1
        tmppivot = pivot_M
        chkmatch = 0
        while pivot_N >= 0:
            if str_M[tmppivot] == str_N[pivot_N]:
                tmppivot -= 1
                chkmatch += 1
            else:
                tmppivot = pivot_M
                chkmatch = 0
            pivot_N -= 1
        
        if chkmatch == length_N:
            result = 1
            break
        else:
            pivot_M += length_N - chkmatch        

    print(f'#{tc} {result}')
```



