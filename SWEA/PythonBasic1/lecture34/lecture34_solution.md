```python
def ReverseStr(str) : 
    result = ""
    for i in range(0, len(str)) :
        result = result + str[len(str)-i-1]
    return result

T = input()

reverse = ReverseStr(T)
print(reverse)
if reverse == T :
    print("입력하신 단어는 회문(Palindrome)입니다.")
else :
    print("입력하신 단어는 회문(Palindrome)이 아닙니다.")



```



