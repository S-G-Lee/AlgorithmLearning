```python
student1 = (90, 80)
student2 = (85, 75)
student3 = (90, 100)

studentlist = [student1, student2, student3]
for idx, val in enumerate(studentlist):
    print("{0}번 학생의 총점은 {1}점이고, 평균은 {2:.1f}입니다.".format(idx+1, (val[0]+val[1]), (val[0]+val[1])/2))

```



