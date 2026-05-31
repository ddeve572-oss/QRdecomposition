# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: DEVENDRAN G
RegisterNumber: 212225240030
'''
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"

import numpy as np

A = np.array(eval(input()), dtype=float)

m, n = A.shape
Q = np.zeros((m, n))
R = np.zeros((n, n))

for j in range(n):
    v = A[:, j]

    for i in range(j):
        R[i, j] = np.dot(Q[:, i], A[:, j])
        v = v - R[i, j] * Q[:, i]

    R[j, j] = np.linalg.norm(v)
    Q[:, j] = v / R[j, j]

print("The Q Matrix is")
print("",Q)

print("The R Matrix is")
print("",R)






```

## Output
<img width="979" height="386" alt="Screenshot 2026-05-31 142249" src="https://github.com/user-attachments/assets/efdfa3db-aa2a-4e7a-a62f-7c572325feb8" />
<img width="1062" height="720" alt="Screenshot 2026-05-31 142302" src="https://github.com/user-attachments/assets/b1e08f1b-3aa1-46a9-b035-c32d8e0adadd" />
<img width="1246" height="728" alt="Screenshot 2026-05-31 142321" src="https://github.com/user-attachments/assets/f67d5f80-8cbf-4184-8c61-08a4e00f44f1" />



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
