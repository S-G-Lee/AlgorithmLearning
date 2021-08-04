```python
def indextocoord(i, j, n):
    #i, j are indices of array, n is size
    center = (n-1)/2
    return j - center, -i + center

def rotate90cw(x, y):
    # matrix for rotation is
    # |cos(θ) -sin(θ)|
    # |sin(θ) cos(θ) |
    # in this problem θ = -90 (90, clockwise)
    return y, -x

def coordtoindex(x, y, n):
    #i, j are indices of array, n is size
    center = (n-1)/2
    return int(round(-y + center)), int(round(x + center))

T = int(input())

for tc in range(1, T + 1):

    N = int(input())

    matrix = [list(map(int, input().split())) for _ in range(N)]

    mat1 = [[0 for col in range(N)] for row in range(N)]
    for i in range(N):
        for j in range(N):
            x, y = indextocoord(i, j, N)
            x, y = rotate90cw(x, y)
            new_i, new_j = coordtoindex(x, y, N)
            mat1[new_i][new_j] = matrix[i][j]

    mat2 = [[0 for col in range(N)] for row in range(N)]
    for i in range(N):
        for j in range(N):
            x, y = indextocoord(i, j, N)
            x, y = rotate90cw(x, y)
            new_i, new_j = coordtoindex(x, y, N)
            mat2[new_i][new_j] = mat1[i][j]

    mat3 = [[0 for col in range(N)] for row in range(N)]
    for i in range(N):
        for j in range(N):
            x, y = indextocoord(i, j, N)
            x, y = rotate90cw(x, y)
            new_i, new_j = coordtoindex(x, y, N)
            mat3[new_i][new_j] = mat2[i][j]

    print(f'#{tc} ')
    for i in range(N):
        result = ''.join(map(str, mat1[i])) + ' ' + ''.join(map(str, mat2[i])) + ' ' + ''.join(map(str, mat3[i]))
        print(result)
```



