 POLICY EVALUATION

AIM
To evaluate and compare different policies in the Frozen Lake environment and find the best policy for reaching the goal successfully.

PROBLEM STATEMENT
In the Frozen Lake environment, an agent must navigate from the start to the goal while avoiding holes. Movements are uncertain due to slipperiness. A policy guides the agent’s actions, but not all policies are effective. The task is to:

Evaluate a given policy (V1) using policy evaluation. Create and test a new policy (V2) to improve performance. Compare both policies based on success rate and rewards. Find the best policy for safely reaching the goal. This helps in identifying the most efficient way to complete the task.

POLICY EVALUATION FUNCTION

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


OUTPUT:
policies:
policy 1:



![image](https://github.com/user-attachments/assets/a63d340f-8a75-4be6-8993-8d307babac5e)




policy 2:


![image](https://github.com/user-attachments/assets/065235e5-cf9c-43da-9319-844424020f02)



State Value function:


State value function 1:


![image](https://github.com/user-attachments/assets/3648a080-0f14-4d4e-af66-6ee4a1b0ac14)



state value function 2:


![image](https://github.com/user-attachments/assets/f8d3af88-a861-42e3-b2b8-05c9e2c18239)


Best Policy

![image](https://github.com/user-attachments/assets/c97ce762-1445-4ea0-bdb8-10ccea20d1d4)

 RESULT:

Thus, The Python program to evaluate the given policy is successfully executed.

