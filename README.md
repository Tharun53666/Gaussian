# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
## Step 1:
Import the required libraries numpy and sys.

## Step 2:
Input the size of the matrix n and define augmented matrix a as a NumPy array of size (n, n+1). Initialize the solution array x as a NumPy array of size n.

## Step 3:
Perform forward elimination to transform the augmented matrix into an upper triangular form:

For each pivot row, ensure the pivot element is non-zero.
Subtract multiples of the pivot row from the rows below to eliminate the elements below the pivot.
## Step 4:
Perform backward substitution to compute the solution:

Start with the last variable and substitute back into the equations to find the remaining variables.
## Step 5:
Display the solution values of all variables using formatted output.

## Step 6:
Verify the results for correctness.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: THARRUN D
RegisterNumber: 212224240170
'''
import numpy as np

def gaussian_elimination(data):
    import numpy as np

    n = int(data[0])
    matrix = np.array(data[1:], dtype=float).reshape((n, n + 1))

  
    for i in range(n):
        pivot = matrix[i][i]
        for j in range(i + 1, n):
            factor = matrix[j][i] / pivot
            matrix[j, i:] -= factor * matrix[i, i:]

  
    x = [0 for _ in range(n)]
    for i in range(n - 1, -1, -1):
        x[i] = (matrix[i][-1] - sum(matrix[i][j] * x[j] for j in range(i + 1, n))) / matrix[i][i]

   
    for i in range(n):
        print(f"X{i} = {x[i]:.2f}",end=" ")


input_data = [
    3,
    1, 2, 4, 18,
    2, 12, -2, 9,
    5, 26, 5, 14
]

gaussian_elimination(input_data)
```
## Output:
![Screenshot 2025-05-16 223859](https://github.com/user-attachments/assets/130dbacb-6f8f-4e2b-955c-a6839259af5c)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

