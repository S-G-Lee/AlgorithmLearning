```python
class Node:

    def __init__(self, item):
        self.item = item
        self.next = None


class LinkedList:

    def __init__(self):
        self.head = Node(None)

    def append(self, item):
        cur = self.head
        while cur.next != None:
            cur = cur.next
        cur.next = Node(item)

    def prepend(self, item):
        next = self.head.next
        self.head.next = Node(item)
        self.head.next.next = next

    def insert(self, idx, item):
        count = 0
        cur = self.head
        while count < idx:
            cur = cur.next
            count += 1
        next = cur.next
        cur.next = Node(item)
        cur.next.next = next

    def get(self, idx):
        count = -1
        cur = self.head
        while count < idx:
            cur = cur.next
            count += 1
        return cur.item


T = int(input())

answer = []
for tc in range(1, T + 1):

    # N : initial list length, M : additional list length, L : index to print
    N, M, L = map(int, input().split())
    input_seq = list(map(int, input().split()))
    ll = LinkedList()
    for item in input_seq:
        ll.append(item)

    for _ in range(M):
        idx, item = map(int, input().split())
        ll.insert(idx, item)
    
    result = ll.get(L)        

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



