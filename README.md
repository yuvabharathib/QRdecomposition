# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.Intialize the matrix Q and u

2.The vector u and e is given by

eqn1: u=a1

eqn2: a2-(a2.e1)e1

eqn3: a3-(a3.e1)e1-(a3.e2)e2

3.Obtain the Q matrix

4.Construct the upper triangular matrix R


## Program:
### Gram-Schmidt Method
```python
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: yuvabharathib
RegisterNumber: 22002787
'''
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    
    Q = np.empty((n,n))
    u = np.empty((n,n))
    
    u[:,0] = A[:,0]
    Q[:,0] = u[:,0]/np.linalg.norm(u[:,0])
    
    for i in range(1,n):
        
        u[:,i] = A[:,i]
        for j in range(i):
            u[:,i] -= (A[:,i] @ Q[:,j]) * Q[:,j]
            
        Q[:,i] = u[:,i]/np.linalg.norm(u[:,i])
        
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j] = A[:,j] @ Q[:,i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![QR decomposition](https://user-images.githubusercontent.com/113497406/192082534-f3cdbb2c-6dd9-4cae-9a17-779d5483b191.png)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
