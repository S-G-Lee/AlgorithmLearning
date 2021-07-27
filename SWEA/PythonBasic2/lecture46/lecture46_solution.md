```# 기본 제공코드는 임의 수정해도 관계 없습니다. 단, 입출력 포맷 주의
class Student:
    
    def __init__(self, name):
        self.__name = name
        
    @property
    def name(self):
        return self.__name

class GraduateStudent(Student):
    
    def __init__(self, name, major):
        Student.__init__(self, name)
        self.__major = major
    
    @property
    def major(self):
        return self.__major
    
    
inputparentname = "홍길동"
inputchildname = "이순신"
inputchildmajor = "컴퓨터"

parent = Student(inputparentname)
print(f"이름: {parent.name}")
child = GraduateStudent(inputchildname, inputchildmajor)
print(f"이름: {child.name}, 전공: {child.major}")
```



