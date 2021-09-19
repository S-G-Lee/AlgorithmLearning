```python
def change_one(switches, i):
    if switches[i] == 0:
        switches[i] = 1
    elif switches[i] == 1:
        switches[i] = 0

def change_boy(switches, n):
    for i in range(len(switches)):
        if (i+1) % n == 0:
            change_one(switches, i)

def change_girl(switches, n):
    start = n-1
    end = n-1
    length = len(switches)
    while start >= 0 and end < length and switches[start] == switches[end]:
        start -= 1
        end += 1
    start += 1
    end -= 1
    
    for i in range(start, end+1):
        change_one(switches, i)


N = int(input())
switches = list(map(int, input().split()))
M = int(input())
students = []
for _ in range(M):
    students.append(list(map(int, input().split())))

for student in students:
    if student[0] == 1:
        change_boy(switches, student[1])
    elif student[0] == 2:
        change_girl(switches, student[1])


for i in range(len(switches)):
    if i != 0 and i % 20 == 0:
        print()
    print(switches[i], end=' ')
```



