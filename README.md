# rl
Consider a Markov Decision Process (MDP) with three states, S1, S2, and S3. 
1. Transition probabilities:
- From S1, you can transition to S2 with a probability of 0.3 and stay in S1 with a
probability of 0.7.
- From S2, you can transition to S1 with a probability of 0.2 and stay in S2 with a
probability of 0.8.
- From S3, you can transition to S1 with a probability of 0.4 and stay in S3 with a
probability of 0.6.
2. Immediate rewards:
S1 to S2 has a reward of 5. 
S2 to S3 has a reward of 2. 
S3 toS1 has a reward of 1.
Assuming an initial value of V(S1)=0, Calculate the value of V(s1) after one iteration 
using bellman equation. 
Solution 1:

![image](https://github.com/sujith87r/rl/assets/113872741/9d77398c-5fe7-4e46-92b5-f7891b598920)

Solution 2:

States: S1, S2, S3 
Actions: Implicitly assumed to be the possible transitions between states. 
Transition probabilities:
• P(S2 | S1) = 0.3, P(S1 | S1) = 0.7
• P(S1 | S2) = 0.2, P(S2 | S2) = 0.8
• P(S1 | S3) = 0.4, P(S3 | S3) = 0.6
Immediate rewards:
• R(S1, S2) = 5,
• R(S2, S3) = 2,
• R(S3, S1) = 1
Discount factor: Assumed to be 1 for this specific calculation (no discounting).
Initial value: V(S1) = 0
Bellman equation for iterative value estimation:
V(S) = R(S) + γ Σ P(S'|S, a) * V(S')
Calculating V(S1) after one iteration:
1. Apply the Bellman equation to S1:
V(S1) = R(S1) + γ (P(S2 | S1) * V(S2) + P(S1 | S1) * V(S1))
Since the discount factor is 1 and V(S1) is initially 0:
V(S1) = R(S1) + P(S2 | S1) * V(S2) + P(S1 | S1) * V(S1)
2. Substitute known values:
V(S1) = 5 + 0.3 * V(S2) + 0.7 * 0 (V(S1) is initially 0)
3. Calculate V(S2) first.
Apply the Bellman equation to S2:
V(S2) = R(S2) + γ (P(S1 | S2) * V(S1) + P(S2 | S2) * V(S2))
Substituting known values and the updated V(S1) equation:
V(S2) = 2 + 0.2 * V(S1) + 0.8 * V(S2)
4. Solve for V(S2):
0.2 * V(S1) = 0.8 * V(S2) - 2 
V(S2) = V(S1) * 4 - 10
5. Substitute solved V(S2) back into the equation for V(S1):
V(S1) = 5 + 0.3 * (V(S1) * 4 - 10) + 0.7 * 0
0.7 * V(S1) = 5 - 1.2 + 0.3 * V(S1) * 4 3.7 * V(S1) = 3.8 V(S1) = 1.03 (rounded to two 
decimal places)
Therefore, the value of V(S1) after one iteration using the Bellman equation is 1.03
********************************************************************************
States: S1, S2, S3 Actions: Left, Right Transition probabilities:
• P(S2 | S1, Left) = 0.8, P(S3 | S1, Left) = 0.2
• P(S1 | S2, Left) = 1.0 (cannot move left further from S1)
• P(S2 | S3, Left) = 0.4, P(S1 | S3, Left) = 0.6
• P(S1 | S1, Right) = 0.7, P(S2 | S1, Right) = 0.3
• P(S2 | S2, Right) = 1.0 (cannot move right further from S2)
• P(S3 | S3, Right) = 0.5, P(S2 | S3, Right) = 0.5
Immediate rewards:
• R(S1, S2) = 2, R(S2, S3) = -1, R(S3, S1) = 4
• All other transitions have a reward of 0.
Discount factor: 1 (no discounting)
Initial values: V(S1) = V(S2) = V(S3) = 0
Question: Calculate the value of V(S2) after one iteration using the Bellman 
equation

*************************************************************

Consider a Markov Decision Process (MDP) with three states, S1, S2, and S3. 
1. Transition probabilities:
- From S1, you can transition to S2 with a probability of 0.3 and stay in S1 with a
probability of 0.7.
- From S2, you can transition to S1 with a probability of 0.2 and stay in S2 with a
probability of 0.8.
- From S3, you can transition to S1 with a probability of 0.4 and stay in S3 with a
probability of 0.6.
2. Immediate rewards:
S1 to S2 has a reward of 5. 
S2 to S3 has a reward of 2. 
S3 toS1 has a reward of 1.
Assuming an initial value of V(S1)=0, Calculate the value of V(s1) after one iteration 
using bellman equation. 
*********************************************************************************
Consider a Markov Decision Process (MDP) with four states, S1, S2, S3, and S4.
Transition probabilities:
From S1, you can transition to S2 with a probability of 0.4 and stay in S1 with a 
probability of 0.6.
From S2, you can transition to S3 with a probability of 0.5 and stay in S2 with a 
probability of 0.5.
From S3, you can transition to S4 with a probability of 0.6 and stay in S3 with a 
probability of 0.4.
From S4, you can transition to S1 with a probability of 0.7 and stay in S4 with a 
probability of 0.3.
Immediate rewards:
S1 to S2 has a reward of 4.
S2 to S3 has a reward of 3.
S3 to S4 has a reward of 5.
S4 to S1 has a reward of 2.
Assuming an initial value of V(S1) = 0, calculate the value of V(S1) after one iteration 
using the Bellman equation
