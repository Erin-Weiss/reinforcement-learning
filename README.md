# Warehouse Robot Path Optimization Using Reinforcement Learning

**Author:** Erin Weiss
[Portfolio](https://erin-weiss.github.io/index.html) | [LinkedIn](https://www.linkedin.com/in/erinweiss3/) | [GitHub](https://github.com/Erin-Weiss)

[View the Full Interactive Report](https://erin-weiss.github.io/articles/RL-Article.html) | [Open in Google Colab](https://colab.research.google.com/drive/1AdGevMypjOROYdtjgmwzJGFNswwUC5mm?usp=sharing)

---

## Objective

Optimize a mobile robot's navigation path in a simulated warehouse environment using reinforcement learning. The agent learns to travel from any starting cell to a target cell on a 10×10 grid while avoiding obstacles and minimizing total steps. The model uses Q-Learning with an epsilon-greedy strategy and the Bellman equation to iteratively build an optimal policy, demonstrating how reinforcement learning can streamline warehouse fulfillment operations.

---

## Dataset

| Property | Detail |
|----------|--------|
| Environment | 10 × 10 grid (100 discrete states) |
| Actions | Up, Down, Left, Right |
| Goal Reward | +100 |
| Obstacle Penalty | −20 |
| Step Penalty | −1 |
| Source | Simulated warehouse environment (author-designed) |

---

## Methodology

1. **Environment Design** — Constructed a 10×10 grid with configurable obstacle placements and reward assignments to simulate a warehouse floor layout.
2. **Reward Mapping** — Assigned +100 for reaching the goal cell, −20 for obstacle collisions, and −1 per step to incentivize shortest-path behavior.
3. **Q-Table Initialization** — Created a state-action value table initialized to zeros, updated iteratively via the Bellman equation.
4. **Training (Q-Learning)** — Ran 2,500 episodes with an epsilon-greedy exploration strategy, decaying epsilon from 1.0 to 0.01 to shift from exploration to exploitation.
5. **Hyperparameter Tuning** — Systematically tested combinations of learning rate (α), discount factor (γ), episode count, and exploration decay rate across multiple experiments.
6. **Consistency Evaluation** — Ran 100 independent training iterations to assess the stability and reliability of learned paths.
7. **Multi-Stop Extension** — Implemented an intermediary stop function to simulate multi-point retrieval tasks within a single route.

---

## Results

| Parameter | Default Value |
|-----------|---------------|
| Episodes | 2,500 |
| Learning Rate (α) | 0.99 |
| Discount Factor (γ) | 0.99 |
| Exploration Decay Rate | 0.001 |
| Epsilon (ε) | 1.0 → 0.01 |

**Key findings:**

- The agent reliably achieves the shortest path approximately 84% of the time at 2,500 training episodes.
- A high learning rate (α ≈ 0.99) accelerates convergence and produces more consistent results.
- Lower exploration decay rates allow sufficient environment exploration before shifting to exploitation, reducing the risk of local optima.
- Increasing episode count improves path consistency but introduces additional computation time.
- The epsilon decay strategy outperforms a constant epsilon approach by enabling faster convergence to the optimal policy.

> **Note:** Because the model retrains from scratch each run, specific numerical outputs may vary slightly between executions. Reported values represent typical results.

---

## Example Outputs

```python
final_path('D4', 'A10')
# Output:
D4 => C4 => B4 => A4 => A5 => A6 => A7 => A8 => A9 => A10

extra_stop('D4', 'D6', 'A10')
# Output:
D4 => D5 => D6 => C6 => B6 => A6 => A7 => A8 => A9 => A10
```

---

## Business Context

Companies with large warehouse operations (such as Amazon, Ocado, or Stitch Fix) use similar algorithms to optimize fulfillment routes. Reinforcement learning enables robots to self-adapt to new obstacles and layout changes, retrain quickly with minimal human intervention, increase throughput efficiency while minimizing operational costs, and scale automation without requiring new rule-based logic. These advantages make Q-Learning a practical foundation for developing autonomous warehouse systems that combine flexibility, efficiency, and intelligence.

---

## Tech Stack

| Category | Tool |
|----------|------|
| Language | `Python 3` |
| Core Library | `NumPy` |
| Visualization | `Matplotlib` / Inline Visuals |
| Algorithm | Q-Learning (Reinforcement Learning) |
| Platform | `Google Colab` |
| Documentation | `Markdown` (embedded in notebook) |

---

## Repository Structure

```
reinforcement-learning/
├── RL_Coding_Demo.ipynb       # Full Google Colab notebook with Q-Learning implementation
├── warehouse-grid.png         # Environment layout visualization
└── README.md                  # Project documentation and overview
```

---

## How to Reproduce

```bash
git clone https://github.com/Erin-Weiss/reinforcement-learning.git
cd reinforcement-learning
```

Open `RL_Coding_Demo.ipynb` in Google Colab. The notebook contains the full pipeline including environment setup, Q-Table training, hyperparameter tuning, path evaluation, and multi-stop extension. Requires Python 3 with NumPy installed.

> **Note:** This notebook was developed and tested in Google Colab. The embedded visualizations use Google Drive–hosted images, so running locally in Jupyter may cause images not to render. For the best experience, use the Colab link below.

Open the notebook directly in Google Colab: [Open in Colab](https://colab.research.google.com/drive/1AdGevMypjOROYdtjgmwzJGFNswwUC5mm?usp=sharing)

---

## Future Work

- Implement Deep Q-Networks (DQN) to handle larger or continuous state spaces beyond the 10×10 grid.
- Introduce dynamic obstacles that change position between episodes to test the agent's adaptability.
- Compare Q-Learning performance against A* and Dijkstra's algorithm for benchmarking path optimality.
- Extend the environment to three dimensions to simulate multi-floor warehouse navigation.
- Implement multi-agent reinforcement learning to coordinate multiple robots operating simultaneously in the same warehouse, optimizing for collision avoidance and shared task completion.
