# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
Step 1: Import the required modules (numpy for array creation and sys for exiting in case of division by zero).
Step 2: Input the number of linear equations n.
Step 3: Initialize an augmented matrix a of size n × (n+1) with zeros, and a solution vector X of size n with zeros.
Step 4: Input the coefficients of the augmented matrix from the user.
Step 5 (Forward Elimination):
     For each pivot row i from 0 to n-1:
     If the pivot element a[i][i] is zero, terminate the program (division by zero not allowed).
     For each row j below the pivot row:
     Calculate the ratio = a[j][i] / a[i][i].
     Subtract (ratio × pivot row) from row j to eliminate the element below the pivot.
Step 6 (Back Substitution):
     Set the last variable X[n-1] = a[n-1][n] / a[n-1][n-1].
     For each row i from n-2 down to 0:
     Assign X[i] = a[i][n].
     Subtract the sum of a[i][j] * X[j] for all known values of j.
     Divide by the pivot element a[i][i] to get the value of X[i].
Step 7: Print all values of the solution vector X with two decimal places.
Step 8: End the program.
```

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: B.VIMALRAJ
RegisterNumber: 212224230304
'''
```
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
X=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0:
        sys.exit('Divide by zero detected')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
X[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    X[i]=a[i][n]
    for j in range(i+1,n):
        X[i]=X[i]-a[i][j]*X[j]
    X[i]=X[i]/a[i][i]
for i in range(n):
    print(f"X{i} = {X[i]:.2f}",end=' ')
```

## Output:

<img width="679" height="776" alt="Screenshot 2025-09-02 210459" src="https://github.com/user-attachments/assets/6551fa21-b4ca-493b-b886-83f6b2c0182b" />

<img width="509" height="359" alt="Screenshot 2025-09-02 210509" src="https://github.com/user-attachments/assets/792fbe2d-b222-40a1-939b-137898c9e40e" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

