```python
class Person:
    
    def __init__(self):
        a=0
    
    def getGender(self):
        return "Unknown"
    
    
class Male(Person):
    
    def __init__(self):
        Person.__init__(self)
        self.gender = "Male"
    
    def getGender(self):
        return self.gender
    
    
class Female(Person):
    
    def __init__(self):
        Person.__init__(self)
        self.gender = "Female"
    
    def getGender(self):
        return self.gender
    
    
man = Male()
woman = Female()
print(man.getGender())
print(woman.getGender())
```



