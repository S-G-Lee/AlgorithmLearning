```python
N = int(input())

for _ in range(N):
    a_ddakgi = [0] * 4
    b_ddakgi = [0] * 4
    a_input = list(map(int, input().split()))
    for i in range(1, len(a_input)):
        a_ddakgi[a_input[i]-1] += 1
    b_input = list(map(int, input().split()))
    for i in range(1, len(b_input)):
        b_ddakgi[b_input[i]-1] += 1

    for i in range(3, -1, -1):
        if a_ddakgi[i] > b_ddakgi[i]:
            print('A')
            break
        elif a_ddakgi[i] < b_ddakgi[i]:
            print('B')
            break
    else:
        print('D')
```



