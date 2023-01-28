# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.  Initialize a square matrix 'a' of size 'n' and a vector 'x' of size 'n' to store the solutions.
2. Read the matrix elements and the right-hand side vector elements from the user.
3. Loop through the rows of the matrix starting from the first row.
4. Check if the pivot element (the element on the main diagonal) is zero. If it is, exit the program
as it will result in a divide by zero error.
5. Loop through the rows below the current row.
6. Calculate the ratio of the element in the current column of the lower row to the pivot element.
7. Loop through the columns of the lower row.
8. Subtract the product of the ratio and the element in the current column of the upper row from
the element in the current column of the lower row.
9. Back substitute to find the solutions by starting from the last row and then moving towards the
first row.
10. Divide the element in the last column of the current row by the pivot element to find the
solution for the current variable.
11. Subtract the product of the solutions of the variables above the current variable and the
corresponding elements in the current row from the element in the last column of the current
row.
12. Divide the result by the pivot element to find the solution for the current variable.
13. Print the solutions




## Program:


Program to find the solution of a matrix using Gaussian Elimination.
Developed by: vidhyasri.k
RegisterNumber: 22008468

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

        sys.exit("Divide by zero 
        
        detected!")

    for j in range(i+1,n):

        ratio=a[j][i]/a[i][i]

        for k in range(n+1):

            a[j][k]=a[j][k]

            -ratio*a[i][k]

x[n-1]=a[n-1][n]/a[n-1][n-1] 

for i in range(n-2,-1,-1):

    x[i]=a[i][n]

    for j in range(i+1,n):

        x[i]=x[i]-a[i][j]*x[j]

    x[i]=x[i]/a[i][i]

for i in range(n):

    print('X%d = %0.2f' %(i,x
    
    [i]),end=' ')

## Output

![gaussian](https://user-images.githubusercontent.com/119477817/215280996-a0bd09d4-15b5-4c97-bfa9-5310a8cdbd0a.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

