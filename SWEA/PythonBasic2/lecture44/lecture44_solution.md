```python
class Student:
    korean = 0
    math = 0
    english = 0
    def __init__(self, korean, math, english):
        self.korean = korean
        self.math = math
        self.english = english
    def scoresum(self):
        return self.korean + self.math + self.english
    
inputarr = input().split(', ')

cheolsu = Student(int(inputarr[0]), int(inputarr[1]), int(inputarr[2]))
result = cheolsu.scoresum()
print(f"국어, 영어, 수학의 총점: {result}")
```



