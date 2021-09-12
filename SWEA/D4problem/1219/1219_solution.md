```python
class Stack:

    def __init__(self):
        self.stack = [-1] * 100
        self.idx = -1

    # 스택이 비어있는지 검사하는 함수
    def is_empty(self):
        if self.idx == -1:
            return True
        return False

    # 스택 푸시
    def push(self, item):
        self.idx += 1
        self.stack[self.idx] = item

    # 스택 팝
    def pop(self):
        if self.idx == -1:
            return None
        item = self.stack[self.idx]
        self.stack[self.idx] = -1
        self.idx -= 1
        return item

    # 스택 맨 위의 값을 반환하는 함수
    def peek(self):
        return self.stack[self.idx]


def DFS(stack: Stack, V, E, graph, S, G):

    visited = [False for _ in range(V)]

    stack.push(S)
    visited[S] = True
    if S == G:
        return 1
    while not stack.is_empty():
        i = stack.peek()
        w = None
        for j in range(V):
            if (graph[i][j] == 1) and (not visited[j]):
                w = j
                visited[j] = True
                stack.push(w)
                break
        while w:
            i = stack.peek()
            if i == G:
                return 1
            w = None
            for j in range(V):
                if (graph[i][j] == 1) and (not visited[j]):
                    w = j
                    visited[j] = True
                    stack.push(w)
                    break
        stack.pop()

    return 0


# T = int(input())
T = 10

answer = []
for tc in range(1, T+1):
    stack = Stack()
    V = 100
    testcase, E = map(int, input().split())
    graph = [[0 for _ in range(V)] for _ in range(V)]
    input_seq = list(map(int, input().split()))
    for i in range(E):
        a = input_seq[i*2]
        b = input_seq[(i*2)+1]
        graph[a][b] = 1
    S, G = 0, 99

    result = DFS(stack, V, E, graph, S, G)

    answer.append(result)

for tc in range(1, T+1):
    print('#{} {}'.format(tc, answer[tc-1]))
```



