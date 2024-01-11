##  Defining and Solving Reinforcement Learning Task

### Part I

#### Environment Description
The environment is a Mario Kart grid world where Mario navigates a 4x4 grid. Mario can move up, down, left, and right. Rewards (+4, +7) and penalties (-3, -5) are represented by coin bags and bombs, respectively. The goal is for Mario to reach the bottom-right cell, starting from the top-left. The objective is to maximize the score by collecting rewards and avoiding penalties, with a trophy reward of +10 for reaching the goal.

#### Theme
Mario Grid World with coin bags as positive rewards and bombs as negative rewards.

#### States
{S1 = (0,0), S2 = (0,1), ..., S16 = (3,3)}

#### Initial and Goal States
Initial state: S1 = (0,0)
Goal state: S16 = (3,3)

#### Actions
{Up, Down, Right, Left} => {3,2,0,1}

#### Rewards
{-3, -5, +4, +7, +10}

#### Objective
Reach the goal state with maximum reward

#### Visualization
Visualization of the grid world and agent's movements

### Safety in AI
To ensure safety, agent movements are confined to the 4x4 grid using np.clip. The state-space is defined, and the reset_state variable resets the agent's position to a valid state. Constraints are enforced on actions to prevent invalid moves.

### Part II and III

#### Tabular Methods Used
1. SARSA (State-Action-Reward-State-Action)
   - Update function: Q(s,a) <- Q(s,a) + α[r + γQ(s',a') - Q(s,a)]
   - Key features: On-policy, TD learning, Control algorithm

2. Q-learning
   - Update function: Q(s,a) <- Q(s,a) + α[r + γmax(Q(s',a')) - Q(s,a)]
   - Key features: Off-policy, TD learning, Control algorithm

#### Results after Applying SARSA and Q-learning
[Plots for SARSA: Total rewards per episode, Epsilon Decay]
[Plots for Q-learning: Total rewards per episode, Epsilon Decay]

#### Evaluation Results
[Plots for SARSA and Q-learning on test data]

#### Performance Comparison
[Comparison of SARSA and Q-learning performance]

### Hyperparameter Tuning

#### SARSA
- Setup 1: Tuning γ
  - γ = 0.8
  - γ = 0.4
  - γ = 1.0

- Setup 2: Tuning decay_rate
  - decay_rate = 0.8
  - decay_rate = 0.6
  - decay_rate = 0.3

#### Q-Learning
- Setup 1: Tuning γ
  - γ = 0.8
  - γ = 0.4
  - γ = 0.1

- Setup 2: Tuning decay_rate
  - decay_rate = 0.8
  - decay_rate = 0.6
  - decay_rate = 0.3

#### Conclusion
After tuning, optimal values for SARSA and Q-learning were found to be gamma = 0.99 and decay rate = 0.995.

