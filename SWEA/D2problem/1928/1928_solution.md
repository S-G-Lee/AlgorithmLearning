```python
encoding_dict = {}
for i in range((ord('Z')-ord('A')) + 1):
    encoding_dict[chr(i + ord('A'))] = i
for i in range((ord('z')-ord('a')) + 1):
    encoding_dict[chr(i + ord('a'))] = i + (ord('Z')-ord('A')) + 1
for i in range(10):
    encoding_dict[str(i)] = i + (ord('Z')-ord('A')) + 1 + (ord('z')-ord('a')) + 1
encoding_dict['+'] = 62
encoding_dict['/'] = 63    

T = int(input())

for tc in range(1, T + 1):   

    encoded = input()

    result = ''
    for i in range(0,len(encoded),4):

        a = bin(encoding_dict[encoded[i]])[2:].rjust(6, '0')
        b = bin(encoding_dict[encoded[i+1]])[2:].rjust(6, '0')
        c = bin(encoding_dict[encoded[i+2]])[2:].rjust(6, '0')
        d = bin(encoding_dict[encoded[i+3]])[2:].rjust(6, '0')
        binary = a + b + c + d
        word = chr(int(binary[0:8], base=2)) + chr(int(binary[8:16], base=2)) + chr(int(binary[16:24], base=2))

        result += word

    print(f'#{tc} {result}')
```



