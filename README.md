# Norm of a matrix
## Aim
To write a program to find the 1-norm, 2-norm and infinity norm of the matrix and display the result in two decimal places.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
	1. Get the input matrix using np.array()   
    2. Find the 2-norm of the matrix using np.linalg.norm()
	3. Print the norm of the matrix in two decimal places.
## Program:
```

# Register No: 212223230181
# Developed By:R SAKETRAM
# 1-Norm of a Matrix
import ast

A = ast.literal_eval(input())

rows = len(A)
cols = len(A[0])

max_sum = 0

for j in range(cols):
    col_sum = 0
    for i in range(rows):
        col_sum += abs(A[i][j])
    if col_sum > max_sum:
        max_sum = col_sum

print(f"{max_sum:.2f}")



# 2-Norm of a Matrix
'''
Program to find 2-norm of a matrix.
Developed by: MONICA G
RegisterNumber: 212224040198
'''
import ast
import math

A = ast.literal_eval(input())

m = len(A)
n = len(A[0])

# Compute A^T * A
B = [[0]*n for _ in range(n)]

for i in range(n):
    for j in range(n):
        for k in range(m):
            B[i][j] += A[k][i] * A[k][j]

# Power iteration to find largest eigenvalue
x = [1]*n
for _ in range(20):
    y = [0]*n
    for i in range(n):
        for j in range(n):
            y[i] += B[i][j]*x[j]
    norm = max(abs(v) for v in y)
    x = [v/norm for v in y]

# Rayleigh quotient
num = 0
den = 0
for i in range(n):
    temp = 0
    for j in range(n):
        temp += B[i][j]*x[j]
    num += x[i]*temp
    den += x[i]*x[i]

largest_eigen = num/den

result = math.sqrt(largest_eigen)

print(f"{result:.2f}")



# Infinity Norm of a Matrix
import ast

A = ast.literal_eval(input())

max_sum = 0

for row in A:
    row_sum = sum(abs(x) for x in row)
    if row_sum > max_sum:
        max_sum = row_sum

print(f"{max_sum:.2f}")


```
## Output:
### 1-Norm of a Matrix
<img width="859" height="224" alt="Screenshot 2026-03-22 222636" src="https://github.com/user-attachments/assets/2b4eb3a2-c50d-4ac5-aa99-2f4fa2753ae1" />


### 2-Norm of a Matrix
<img width="776" height="273" alt="Screenshot 2026-03-22 222645" src="https://github.com/user-attachments/assets/83c3461a-c144-4835-ba6b-764e5bdc0b76" />

### Infinity Norm of a Matrix
<img width="640" height="229" alt="Screenshot 2026-03-22 222652" src="https://github.com/user-attachments/assets/9a997191-3b3e-43f2-a0e6-cbc46d8911f6" />

## Result
Thus the program for 1-norm, 2-norm and Infinity norm of a matrix are written and verified.
