# Implementation-of-MC-prediction-for-estimating-the-action-value-function.

## Aim

To implement the Monte Carlo (MC) Prediction algorithm for estimating the action-value function \(Q(s,a)\) using sampled episodes and to analyze the learned action values in a Grid World environment.

---

## Objective

- To understand Monte Carlo Prediction for action-value estimation.
- To estimate the action-value function \(Q(s,a)\).
- To learn state-action values from complete episodes.
- To evaluate the quality of actions under a given policy.

---

## Theory

Monte Carlo Prediction is a model-free reinforcement learning technique used to estimate value functions directly from experience.

The action-value function is defined as:

\[
Q(s,a) = E[G_t \mid S_t=s, A_t=a]
\]

Where:

- \(Q(s,a)\) = Expected return for taking action \(a\) in state \(s\)
- \(G_t\) = Discounted return after time step \(t\)

Monte Carlo methods estimate action values by averaging returns obtained after visiting each state-action pair over many episodes.

---

## Algorithm

### Monte Carlo Prediction for Action-Value Function

1. Initialize:
   - Action-value function \(Q(s,a)\)
   - Returns list for every state-action pair

2. Generate an episode using a policy.

3. For every state-action pair in the episode:
   - Calculate the return \(G\)
   - Store the return for that pair
   - Update \(Q(s,a)\) using the average return

4. Repeat the process for many episodes.

5. Display the estimated action-value function.

---

## Program

```
Name:Divya A
Register no.: 2305002007
import numpy as np

# Define states and actions
n_states = 3
n_actions = 2

# Initialize action-value function Q(s,a)
Q = np.zeros((n_states, n_actions))

# Store returns for each state-action pair
returns = {}

for s in range(n_states):
    for a in range(n_actions):
        returns[(s, a)] = []

# Discount factor
gamma = 0.9

# Sample episodes
# Format: (state, action, reward)
episodes = [
    [(0, 0, 1), (1, 1, 2), (2, 0, 3)],
    [(0, 1, 2), (1, 0, 1), (2, 1, 4)],
    [(1, 1, 3), (2, 0, 2)]
]

# Monte Carlo Prediction
for episode in episodes:
    G = 0

    # Traverse episode backward
    for t in reversed(range(len(episode))):
        state, action, reward = episode[t]

        # Calculate return
        G = gamma * G + reward

        # First-visit MC check
        if (state, action) not in [(x[0], x[1]) for x in episode[:t]]:
            returns[(state, action)].append(G)

            # Update Q value
            Q[state][action] = np.mean(returns[(state, action)])

# Display Q-values
print("Estimated Action-Value Function Q(s,a):\n")

for s in range(n_states):
    for a in range(n_actions):
        print(f"Q({s},{a}) = {Q[s][a]:.2f}")

```


## Output

<img width="610" height="192" alt="image" src="https://github.com/user-attachments/assets/e1c24032-08e8-4eb6-a838-b33cec01193c" />


## Result

Thus, the Monte Carlo Prediction algorithm was successfully implemented for estimating the action-value function \(Q(s,a)\). The expected returns for different state-action pairs were calculated using sampled episodes generated from the environment.

---


---



---

---
