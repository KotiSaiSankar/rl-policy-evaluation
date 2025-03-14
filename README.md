![image](https://github.com/user-attachments/assets/db37ea14-bd3d-4810-bc72-1cb26737b10e)# POLICY EVALUATION

## AIM
To develop a Python program to evaluate the given policy.

## PROBLEM STATEMENT
To find best policy from two policies which are defined by user using policy evaluation function. Where the mdp includes 16 states from 0-15, 0 is the starting state, assigning some 4 random state as holes and 15 is the goal state and then we need to calculate optimal state value function for each state such that we can reach goal using optimal policy using policy evaluation.

## POLICY EVALUATION FUNCTION
```
def policy_evaluation(pi, P, gamma=1.0, theta=1e-10):
    prev_V = np.zeros(len(P), dtype=np.float64)
    # Write your code here to evaluate the given policy
    while True:
      V=np.zeros(len(P))
      for s in range(len(P)):
        for prob,next_state,reward,done in P[s][pi(s)]:
           V[s]+=prob*(reward+gamma *prev_V[next_state]*(not done))
      if np.max(np.abs(prev_V-V))<theta:
        break
      prev_V=V.copy()
    return V
```

## OUTPUT:
### Policies:

Policy 1:


![image](https://github.com/user-attachments/assets/ddd0445d-09c0-4c43-9e95-a6c9d65ccf2b)



Policy 2:


![image](https://github.com/user-attachments/assets/e09cf78c-3ea4-4874-ba0c-a237f6abc315)    



### State value function:

State value function 1:


![image](https://github.com/user-attachments/assets/9ef31b32-9480-4366-a8d0-2b2af99532e3)

State value function 2:


![image](https://github.com/user-attachments/assets/2b17156e-1ac7-453f-9539-ca7bdc018d6b)



Best policy:


![image](https://github.com/user-attachments/assets/43a648ef-7143-4531-b7de-6514823784b6)


## RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.
