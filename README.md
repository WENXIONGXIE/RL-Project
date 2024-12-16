# README: Custom Car Environment with Deep Q-Learning Agent

## Overview
This project demonstrates the use of a **Deep Q-Learning (DQN) Agent** to train a car in a custom environment. The agent learns to navigate the environment by avoiding obstacles, staying within bounds, and maintaining a moderate speed. The custom environment and DQN agent have been implemented using **Python**, leveraging libraries such as `gym`, `numpy`, `torch`, and `matplotlib`.

## Features
1. **Custom Car Environment:**
   - Action Space: 5 discrete actions (light accelerate, hard accelerate, brake, steer left, steer right).
   - Observation Space: 6-dimensional continuous space.
   - Obstacles are randomly generated while avoiding the center of the environment.

2. **Deep Q-Learning Agent:**
   - Experience replay for training stability.
   - Epsilon-greedy policy for exploration.
   - Separate target network for stable training.
   - Adjustable hyperparameters (e.g., gamma).

3. **Collision Detection Module:**
   - Detects collisions with obstacles or when the car goes out of bounds.

4. **Hyperparameter Experiments:**
   - Varying gamma values (0.5, 0.9, 0.99).
   - Comparative analysis of performance and training behavior.

5. **Visualization:**
   - Reward plots for different gamma values.
   - Cumulative rewards over episodes.
   - Collision heatmaps before and after training.
   - Path efficiency comparisons at different training stages.

## Code Structure
### 1. Custom Environment
```python
class CarEnv(gym.Env):
    # Defines action and observation spaces.
    # Includes methods for resetting and stepping through the environment.
```

### 2. Collision Detection Module
```python
class CollisionModule:
    # Detects collisions with obstacles or out-of-bounds scenarios.
```

### 3. DQN Agent
```python
class DQNAgent:
    # Deep Q-learning agent implementation.
    # Includes Q-network, target network, and experience replay.
```

### 4. Training Function
```python
def train_dqn_agent(env, agent, collision_module, ...):
    # Handles training loop with episode tracking and visualization.
```

### 5. Visualization
- Plots and heatmaps for analyzing performance metrics and collision rates.

## Key Hyperparameter Settings
| Parameter       | Value   |
|-----------------|---------|
| Gamma           | 0.5, 0.9, 0.99 |
| Batch Size      | 64      |
| Learning Rate   | 0.001   |
| Epsilon Decay   | 0.999   |
| Episodes        | 5000    |

## Results
### Rewards and Training Performance
- **Reward Plots:** Show episodic reward trends for each gamma value.
- **Cumulative Rewards:** Demonstrates long-term learning efficiency.

### Collision Heatmaps
- Heatmaps visualize collision points before and after training for each gamma value.

### Path Efficiency
- Comparison of paths taken by the agent at different training stages (e.g., Episode 1000, 3000, 5000).

## Requirements
### Dependencies
- `numpy`
- `gym`
- `torch`
- `matplotlib`
- `seaborn`

### Installation
Install the required libraries using the following command:
```bash
pip install numpy gym torch matplotlib seaborn
```

## How to Run
1. Clone the repository.
2. Install the required dependencies.
3. Run the script:
   ```bash
   python train_dqn_agent.py
   ```
4. Observe the training process and visualizations.

## Future Improvements
1. Introduce continuous action space for smoother control.
2. Implement multi-agent environments.
3. Use advanced models like Double DQN or Dueling DQN.
4. Add more detailed visualization of training behaviors.

