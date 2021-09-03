```python
class Node:

    def __init__(self, item):
        self.item = item
        self.prev = None
        self.next = None


class LinkedList:

    def __init__(self):
        self.head = Node(None)
        self.tail = Node(None)

    def append(self, item):
        prev = self.tail.prev
        new = Node(item)
        if self.head.next == None:
            self.head.next = new
        new.prev = prev
        if prev:
            prev.next = new
        self.tail.prev = new

    def prepend(self, item):
        next = self.head.next
        new = Node(item)
        if self.tail.prev == None:
            self.tail.prev = new
        new.next = next
        if next:
            next.prev = new
        self.head.next = new

    def insert(self, idx, item):
        if idx >= 0:
            count = 0
            cur = self.head
            while count < idx:
                cur = cur.next
                count += 1
            next = cur.next
            new = Node(item)
            if next:
                next.prev = new
            else:
                self.tail.prev = new
            new.next = next
            if cur != self.head:
                new.prev = cur
            cur.next = new
        else:
            count = 0
            cur = self.tail
            while count >= idx:
                cur = cur.prev
                count -= 1
            next = cur.next
            new = Node(item)
            if next:
                next.prev = new
            else:
                self.tail.prev = new
            new.next = next
            if cur != self.head:
                new.prev = cur
            cur.next = new

    def insert_ll(self, idx, first, last):
        if idx >= 0:
            count = 0
            cur = self.head
            while count < idx:
                cur = cur.next
                count += 1
            next = cur.next
            if next:
                next.prev = last
            else:
                self.tail.prev = last
            last.next = next
            if cur != self.head:
                first.prev = cur
            cur.next = first
        else:
            count = 0
            cur = self.tail
            while count >= idx:
                cur = cur.prev
                count -= 1
            next = cur.next
            if next:
                next.prev = last
            else:
                self.tail.prev = last
            last.next = next            
            if cur != self.head:
                first.prev = cur
            cur.next = first
            
    def getitem(self, idx):
        if idx >= 0:
            count = -1
            cur = self.head
            while count < idx:
                if cur == None:
                    break
                cur = cur.next
                count += 1
            if cur == None:
                return None
            return cur.item
        else:            
            count = -1
            cur = self.tail
            while count >= idx:
                if cur == None:
                    break
                cur = cur.prev
                count -= 1
            if cur == None:
                return None
            return cur.item
    
    def getfirst(self):
        return self.head.next
    
    def getlast(self):
        return self.tail.prev


T = int(input())

answer = []
for tc in range(1, T + 1):

    # N : initial list length, M : additional list number
    N, M = map(int, input().split())
    ll = LinkedList()

    for _ in range(M):
        input_seq = list(map(int, input().split()))
        input_ll = LinkedList()
        for item in input_seq:
            input_ll.append(item)

        firstitem = input_ll.getfirst().item
        idx = 0
        item = ll.getitem(idx)
        while item:
            if item > firstitem:
                break
            idx += 1
            item = ll.getitem(idx)

        ll.insert_ll(idx, input_ll.getfirst(), input_ll.getlast())
    
    result = []
    for i in range(-1, -11, -1):
        result.append(ll.getitem(i))
    result = ' '.join(map(str, result)) 

    answer.append(result)

for tc in range(1, T+1):
    print(f'#{tc} {answer[tc-1]}')
```



