# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1: Input the Augmented Matrix
Read the number of equations n.

Initialize matrix A[n][n+1] to store coefficients and constants.

Input each element A[i][j] where 0 ≤ i < n, 0 ≤ j ≤ n.

Step 2: Forward Elimination (Convert to Upper Triangular Matrix)
For each row i from 0 to n-1:

If A[i][i] == 0, report division by zero and exit.

For each row j from i+1 to n-1:

Compute ratio = A[j][i] / A[i][i]

For each column k from 0 to n:

Update: A[j][k] = A[j][k] - ratio * A[i][k]

Step 3: Back Substitution
Initialize solution vector x[n]

Set x[n-1] = A[n-1][n] / A[n-1][n-1]

For i from n-2 to 0:

Set x[i] = A[i][n]

For each j from i+1 to n-1:

Update: x[i] = x[i] - A[i][j] * x[j]

Divide: x[i] = x[i] / A[i][i]

Step 4: Output the Solution

Print each x[i] with appropriate formatting.
## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
*/
```
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f "%(i,x[i]),end='')
```

## Output:
![gaussian elimination]()

![Screenshot (100)](https://github.com/user-attachments/assets/a8d5e238-71cf-4879-98e6-cd4d8e8f81a1)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

