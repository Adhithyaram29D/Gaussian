# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import  the NumPy library using the statement import numpy as np. 
2. Import the lu function from the scipy.linalg module using the statement from scipy.linalg import lu. 
3. Create a NumPy array A by evaluating user input using the eval(input()) function. 
4. Use the lu function to perform LU decomposition on the array A. 
5. Print the solutions

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: AdhithyaRam D
RegisterNumber: 212222230008
*/
import numpy as np
import sys

n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

for i in range(n):
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
    print("X%d = %0.2f"%(i,x[i]),end=" ")
```

## Output:
![Screenshot 2023-06-03 142439](https://github.com/Adhithyaram29D/Gaussian/assets/119393540/803b3b33-c15a-4c30-b28a-ba2289b8dd09)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

