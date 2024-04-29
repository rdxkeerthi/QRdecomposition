# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

3.	Obtain the Q matrix   
    
4.	Construct the upper triangular matrix R
 



## Program:
### Gram-Schmidt Method
```

''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: KEERTHIVASAN M
RegisterNumber: 212223100021
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    U=np.empty((n,n))
    
    U[:,0]=A[:,0]
    Q[:,0]=U[:,0]/np.linalg.norm(U[:,0])
    
    for i in range(1,n):
        U[:,i]=A[:,i]
        for j in range(i):
            U[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=U[:,i]/np.linalg.norm(U[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)





```

## Output

![image](https://github.com/rdxkeerthi/QRdecomposition/assets/147473120/9465533d-5c52-4a12-b478-5b42c401639a)


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
