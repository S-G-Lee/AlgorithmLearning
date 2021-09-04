```python
number = 1


def inorder(node, N, idx):
    global number
    if idx*2 <= N:
        inorder(node, N, idx*2)
    node[idx] = number
    number += 1
    if (idx*2)+1 <= N:
        inorder(node, N, (idx*2)+1)


T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())
    
    number = 1

    node = [0] * (N+1)

    inorder(node, N, 1)

    result = f'{node[1]} {node[N//2]}'
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')

```



