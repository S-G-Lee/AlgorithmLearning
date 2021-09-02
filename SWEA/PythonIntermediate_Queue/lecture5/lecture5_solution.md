```python
T = int(input())

class Node:

    def __init__(self, arg):
        self.item = arg
        self.next = None


class Queue:

    def __init__(self):
        self.length = 0
        self.front = None
        self.rear = None

    def enQueue(self, arg):
        if self.front == None:
            self.front = Node(arg)
        else:
            new = Node(arg)            
            if self.front.next == None:
                self.front.next = new
            if self.rear != None:
                self.rear.next = new
            self.rear = new
        self.length += 1

    def deQueue(self):
        item = self.front.item
        self.front = self.front.next
        if self.front == None:
            rear = None
        self.length -= 1
        return item

    def isEmpty(self):
        if self.front == self.rear == None:
            return True
        return False

    def isFull(self):
        return False

    def Qpeek(self):
        return self.front.item


answer = []
for tc in range(1, T + 1):

    N, M = map(int, input().split())
    numbers = list(map(int, input().split()))

    q = Queue()
    for num in numbers:
        q.enQueue(num)
    
    for _ in range(M):
        a = q.deQueue()
        q.enQueue(a)
    
    result = q.Qpeek()
    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



