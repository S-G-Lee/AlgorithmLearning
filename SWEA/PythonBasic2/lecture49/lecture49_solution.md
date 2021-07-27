```python
class Shape:
    
    def __init__(self, length):
        self.length = length
    
    def getarea(self):
        return 0

    
class Square(Shape):
    
    def __init__(self, length):
        Shape.__init__(self, length)
    
    def getarea(self):
        return self.length * self.length
    

rec = Square(3)
print(f"정사각형의 면적: {rec.getarea()}")
        
```



