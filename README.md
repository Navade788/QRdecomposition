# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
```
1.Start with a matrix A that you want to decompose (having n rows and m columns).
2.Initialize two matrices:
 Q to store the orthonormal vectors (same shape as A).
 R to store coefficients (upper triangular with shape m x m).
3.Loop through each column of matrix A one by one.
4.For the current column, start with the original column from A.
5.Subtract projections on previously computed columns of Q to make the current vector orthogonal to them.
6.Store the projection coefficients in matrix R as you compute them.
7.Normalize the resulting orthogonal vector to make its length 1.
8.Store the normalized vector in the corresponding column of matrix Q.
9.Repeat this process for all columns of A.
10.Return or display the matrices Q (orthonormal) and R (upper triangular), such that multiplying Q and R gives you the original matrix A.
```



## Program:

### Gram-Schmidt Method

```
Program to QR decomposition using the Gram-Schmidt method
Developed by: S.Navadeep
RegisterNumber: 212224230180
```
```
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,m))
    u=np.empty((n,m))
    R=np.zeros((n,m))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(n):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q Matrix is")
    print("",Q)
    print("The R Matrix is")
    print("",R)
A=np.array(eval(input()))
QR_Decomposition(A)
```

## Output

![WhatsApp Image 2025-05-13 at 14 07 23_606e51a8](https://github.com/user-attachments/assets/f7e1e29c-d897-4203-84c0-9a3717106788)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
