```python
def changeval_bottomup(heap, idx):
    while idx > 0 and heap[idx] > heap[(idx-1)//2]:
        heap[idx], heap[(idx-1)//2] = heap[(idx-1)//2], heap[idx]
        idx = (idx-1)//2

def changeval_topdown(heap, idx):
    tempidx = 0
    while tempidx < idx:
        if heap[tempidx*2 + 1] > heap[tempidx*2 + 2]:
            if heap[tempidx] < heap[tempidx*2 + 1]:
                heap[tempidx], heap[tempidx*2 + 1] =  heap[tempidx*2 + 1], heap[tempidx]
                tempidx = tempidx*2 + 1
            elif heap[tempidx] < heap[tempidx*2 + 2]:
                heap[tempidx], heap[tempidx*2 + 2] =  heap[tempidx*2 + 2], heap[tempidx]
                tempidx = tempidx*2 + 2
            else:
                break
        else:
            if heap[tempidx] < heap[tempidx*2 + 2]:
                heap[tempidx], heap[tempidx*2 + 2] =  heap[tempidx*2 + 2], heap[tempidx]
                tempidx = tempidx*2 + 2
            elif heap[tempidx] < heap[tempidx*2 + 1]:
                heap[tempidx], heap[tempidx*2 + 1] =  heap[tempidx*2 + 1], heap[tempidx]
                tempidx = tempidx*2 + 1
            else:
                break


T = int(input())

answer = []
for tc in range(1, T + 1):

    N = int(input())

    heap = [0] * 1000000
    result = []
    idx = -1
    for _ in range(N):
        command = list(map(int, input().split()))
        if len(command) == 2:
            val = command[1]
            idx += 1
            heap[idx] = val
            changeval_bottomup(heap, idx)
        else:
            if idx == -1:
                result.append(-1)
            else:
                result.append(heap[0])
                heap[0] = heap[idx]
                heap[idx] = 0
                idx -= 1
                changeval_topdown(heap, idx)


    result = ' '.join(map(str, result))
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



