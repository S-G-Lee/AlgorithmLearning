```python
class Rectangle:
    
    def __init__(self):
        self.__width = 4
        self.__height = 5
    
    def getarea(self):
        return self.__width * self.__height
    
rec = Rectangle()
print(f"사각형의 면적: {rec.getarea()}")

```



