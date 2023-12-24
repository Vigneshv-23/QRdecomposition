# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

![image](https://github.com/Vigneshv-23/QRdecomposition/assets/110780412/dae2801e-f859-4b90-8f50-b8efaa6dac4e)
![image](https://github.com/Vigneshv-23/QRdecomposition/assets/110780412/a8fae2bc-b653-43b8-a5d7-4166eef0b98f)
![image](https://github.com/Vigneshv-23/QRdecomposition/assets/110780412/96991514-bc3c-4a57-8374-58ce3dc64f23)

3.	Obtain the Q matrix   
![image](https://github.com/Vigneshv-23/QRdecomposition/assets/110780412/9d09a524-7777-47d6-bce2-e2b0a565685b)

4.	Construct the upper triangular matrix R
![image](https://github.com/Vigneshv-23/QRdecomposition/assets/110780412/aec9ed4e-8191-4add-90cb-efb9f5712c4c)




## Program:
### Gram-Schmidt Method
```
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.zeros((n,n))
    U=np.zeros((n,n))
    U[:,0]=A[:,0]
    Q[:,0]=U[:,0]/np.linalg.norm(U[:,0])
    for i in range(1,n):
        U[:,i]=A[:,i]
        for j in range(i):
            U[:,i]-=(A[:,i]) @ Q[:,j]*Q[:,j]
        Q[:,i]=U[:,i]/np.linalg.norm(U[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j] @ Q[:,i]
    print(Q)
    print(R)
a = np.array(eval(input()))
QR_Decomposition(a)






```

## Output
<img width="581" alt="image" src="https://github.com/Vigneshv-23/QRdecomposition/assets/110780412/8ae81b53-f999-447b-95eb-9f8d66ca76bb">
## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
