# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
step 1: Initialize Matrices and Variables
The program takes an integer n as input, representing the number of equations.

It initializes an augmented matrix a (size n × (n+1)) to store coefficients and constants.

A solution vector x is also initialized to store computed values.

Step 2: Input Matrix Elements
The user inputs values for the augmented matrix.

Step 3: Forward Elimination (Transform to Upper Triangular Form)
The program ensures no division by zero when performing row operations.


Step 4: Back Substitution (Compute Solutions)
The last equation is solved first since it contains only one unknown.

## Program:
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
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
        
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    sum=0
    for j in range(i+1,n):
       sum+=a[i][j]*x[j]
    x[i]=(a[i][n]-sum)/a[i][i]
for i in range(n):
    print(f"X{i} = {x[i]:.2f}",end=" ")
```

## Output:
![Screenshot 2025-04-21 181620](https://github.com/user-attachments/assets/cca06047-205c-4225-9122-75b3f237f7f9)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

