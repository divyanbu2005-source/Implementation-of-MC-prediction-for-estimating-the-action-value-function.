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

```python

```

---

## Output

```text


```


## Result

Thus, the Monte Carlo Prediction algorithm was successfully implemented for estimating the action-value function \(Q(s,a)\). The expected returns for different state-action pairs were calculated using sampled episodes generated from the environment.

---


---



---

---
