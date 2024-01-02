# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

   ![eqn](https://github.com/HariharanJayavel/QRdecomposition/assets/144870546/43478d2f-bc39-4ac4-ae34-2465f45316e0)


3.	Obtain the Q matrix   
    ![eqn1](https://github.com/HariharanJayavel/QRdecomposition/assets/144870546/7a781d93-7c09-4349-9817-d16ef4957f57)

4.	Construct the upper triangular matrix R
    ![eqn2](https://github.com/HariharanJayavel/QRdecomposition/assets/144870546/5093760f-57d8-4b3f-a8eb-7bc5b0f405b9)




## Program:
# Program to QR decomposition using the Gram-Schmidt method
# Developed by: HARIHARAN J
# RegisterNumber: 212223240047 
```
import numpy as np
def QR_Decomposition(A):
    n,m = A.shape
    
    Q = np.empty((n, n))
    u = np.empty((n, n))
    
    u[:, 0] = A[:, 0]
    Q[:, 0] = u[:, 0] / np.linalg.norm(u[:, 0])
    
    for i in range(1, n):
        
        u[:, i] = A[:, i]
        for j in range(i):
            u[:, i] -= (A[:, i] @ Q[:, j]) * Q[:, j]
            
        Q[:, i] = u[:, i] / np.linalg.norm(u[:, i])
        
    R = np.zeros((n, m))
    for i in range(n):
        for j in range(i, m):
            R[i, j] = A[:, j] @ Q[:, i]
    
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)
```

## Output
![image](https://github.com/HariharanJayavel/QRdecomposition/assets/144870546/3ce1f0c5-a265-4f98-bb83-d0a450a6cdbd)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
