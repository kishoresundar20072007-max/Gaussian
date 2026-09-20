# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of unknowns and the augmented matrix from the user.
2. Apply Gaussian Elimination to transform the augmented matrix into an upper triangular matrix by eliminating the lower triangular elements.
3. Perform back substitution on the upper triangular matrix to find the values of the unknown variables.
4. Display the solution of the system of equations and end the program.
## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: SUNDAR K
RegisterNumber: 212225040438
'''
import os 
os.environ["OPENBLAS_NUM_THREADS"] = "1"

n = int(input())

a = [[0.0 for j in range(n + 1)] for i in range(n)]

for i in range(n):
    for j in range(n + 1):
        a[i][j] = float(input())
        
for i in range(n):
    for j in range(i + 1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n + 1):
            a[j][k] = a[j][k] - ratio * a[i][k]
            
            
x = [0.0 for i in range(n)]

x[n - 1] = a[n - 1][n] / a[n - 1][n - 1]

for i in range (n -2, -1, -1):
    x[i] = a[i][n]
    for j in range(i + 1 ,n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i] / a[i][i]
    
for i in range(n):
    print("X{} = {:.2f}".format(i, x[i]),end=" ")
```

## Output:

<img width="1342" height="881" alt="Screenshot 2026-09-20 170511" src="https://github.com/user-attachments/assets/4aa8c7e7-243f-4813-ab1e-447d5f8ea777" />

<img width="1355" height="317" alt="Screenshot 2026-09-20 170543" src="https://github.com/user-attachments/assets/7895326a-3bc6-48ac-b913-a43dccc70011" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

