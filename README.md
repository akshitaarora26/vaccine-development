# Vaccine Development with Dynamic Programming

This repository contains a simulation of a vaccine development process modeled as a Markov Decision Process (MDP). The goal of this project is to compute the optimal value function for a biotech company deciding on investments during the various phases of vaccine development. The company starts at phase 0, advances through different states of development, and may either succeed or fail. The objective is to maximize the value of the project through optimal investment strategies.

The code uses **Dynamic Programming** techniques, specifically **Value Iteration**, to determine the best investment policy at each stage of development.

## Problem Description

The vaccine development process is modeled as an MDP with the following characteristics:

- **States**:
  - State 0: Initial phase (preclinical phase)
  - State 1: Phase 1 with promising results
  - State 2: Phase 1 with disappointing results
  - State 3: Success (the vaccine is sold for $10 million)
  - State 4: Failure

- **Actions**:
  - Action 0: No additional investment (proceed with current phase)
  - Action 1: Invest an additional $100,000 (increases chances of success)

- **Transition Probabilities**: The probability of transitioning between states is influenced by the chosen action. There are two sets of transition matrices:
  - `P0`: Transition probabilities without additional investment
  - `P1`: Transition probabilities with an additional investment

- **Rewards**: Each state has a corresponding reward. The reward for reaching state 3 (success) is $10 million, while other states have no immediate monetary reward. There is a cost of $100,000 for investing in a state, which is reflected in the reward function.

- **Discount Factor**: The future rewards are discounted with a factor of `gamma = 0.996`.

## Key Features

- **Value Iteration**: The project uses value iteration to calculate the optimal value function for each state and derive the best policy for investment decisions.
  
- **Policy**: The policy is determined by selecting the action that maximizes the expected future rewards in each state.

