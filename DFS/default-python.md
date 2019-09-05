```python
dx = [0, 0, -1, 1]
dy = [-1, 1, 0, 0]

def dfs(chk, x, y):
    if (chk[y][x] == 0):
        return False
    
    chk[y][x] = 0
    
    for j in range(4):
        nx = x + dx[j]
        ny = y + dy[j]
        
        if (nx >= 0 and nx < len(chk[0]) and ny >= 0 and ny < len(chk)):
            dfs(chk, nx, ny)
    
    return True
```



- Recursion Limit
```python
from sys import *
setrecursionlimit(10 ** 6)
```