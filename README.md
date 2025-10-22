# 🤖 Warehouse Robot Path Optimization using Reinforcement Learning (Google Colab Demo)  
**Author:** Erin Weiss  

---

## 🧠 Coding Demo

👉 [**Click here to open the full Google Colab notebook**](https://colab.research.google.com/github/Erin-Weiss/reinforcement-learning/blob/main/copy_of_coding_demo.ipynb)

---

## 📊 Project Overview  
This Google Colab project demonstrates how reinforcement learning—specifically **Q-Learning**—can be used to optimize a **mobile robot’s path** in a warehouse environment.  
The goal is for the robot to navigate from a starting location to a target cell while avoiding obstacles and minimizing travel steps. The model uses **rewards and penalties** to learn the most efficient routes dynamically.  

This work highlights how reinforcement learning can streamline warehouse operations, reduce travel time, and increase fulfillment efficiency for companies such as Amazon or Stitch Fix.  

---

## 🏁 About This Project  
This project demonstrates my ability to:  
- Design, train, and evaluate a **reinforcement learning agent** using Q-Learning  
- Implement **dynamic environment mapping** with adjustable goals and obstacles  
- Tune **hyperparameters** to balance accuracy, speed, and consistency  
- Translate a machine learning model into a clear, educational **Colab demo** with visual explanations  

---

## 🧩 Features & Functionality  
**Dynamic Path Planning** – The agent learns the optimal route in a 10×10 warehouse grid.  
**Obstacle Avoidance** – Cells with penalties simulate shelves or barriers in a real warehouse.  
**Flexible Start/Goal Selection** – Any valid cell can serve as the starting or goal position.  
**Q-Table Training** – Uses the Bellman equation to iteratively improve action–state values.  
**Hyperparameter Tuning** – Adjusts α (learning rate), γ (discount factor), and ε (exploration rate).  
**Extra Stop Functionality** – Includes an intermediary stop option to simulate multi-point retrieval.  
**Consistency Testing** – Evaluates stability by running 100 independent training iterations.  

---

## 🧰 Technologies & Tools Used  
- **Google Colab / Python 3** – Implementation and interactive visualization  
- **NumPy** – Matrix operations and environment simulation  
- **Matplotlib / Inline Visuals** – Grid visualizations of robot paths  
- **Reinforcement Learning (Q-Learning Algorithm)** – Path optimization method  
- **Markdown Documentation** – Embedded technical explanations within Colab  

---

## ⚙️ Project Details  
| Parameter | Description |
|------------|-------------|
| **Environment Size** | 10 × 10 grid (100 cells) |
| **Rewards** | +100 (goal), –20 (obstacle), –1 (step) |
| **Episodes** | 2,500 (default, tuned for accuracy vs speed) |
| **Learning Rate (α)** | 0.99 |
| **Discount Factor (γ)** | 0.99 |
| **Exploration Decay Rate** | 0.001 |
| **Epsilon (ε)** | Starts at 1.0 → decays to 0.01 |
| **File Type** | Python (.ipynb) Google Colab Notebook |

---

## 💡 Key Insights  
- Increasing **training episodes** improves consistency but raises computation time.  
- A **higher learning rate** (α ≈ 0.99) accelerates convergence.  
- Lower **decay rates** encourage sufficient exploration before exploitation.  
- The robot reliably achieves the **shortest path ≈ 84 %** of the time at 2,500 episodes.  
- Reinforcement learning enables **adaptive pathfinding** without explicit rule-based programming.

> **Note:** Because the model retrains from scratch each time the notebook is run, specific numerical results (such as rewards or episode averages) may vary slightly between runs.  
> Reported values and outputs represent *typical results* that are close but not always identical.

---

## 🧠 Analysis & Commentary  
This demonstration illustrates how Q-Learning can model real-world warehouse optimization.  
Each grid cell represents a discrete state, and the robot learns through iterative exploration to maximize cumulative reward.  

- **Epsilon Decay Strategy:** Balances exploration and exploitation to avoid local optima.  
- **Alpha (Learning Rate):** Controls how quickly the model updates knowledge from new experiences.  
- **Gamma (Discount Rate):** Determines the importance of future vs immediate rewards.  
- **Q-Table Updates:** Use the Bellman equation to iteratively refine expected outcomes.  

The results show that after training, the agent can **consistently select the most efficient route**, demonstrating reinforcement learning’s practical potential for logistics, robotics, and autonomous navigation systems.  

---

## 🧾 Example Outputs  

```python
final_path('D4', 'A10')
# Output:
D4 => C4 => B4 => A4 => A5 => A6 => A7 => A8 => A9 => A10

extra_stop('D4', 'D6', 'A10')
# Output:
D4 => D5 => D6 => C6 => B6 => A6 => A7 => A8 => A9 => A10
```

## 🧭 Business Context  
Companies with large warehouse operations (like **Amazon**, **Ocado**, or **Stitch Fix**) use similar algorithms to optimize fulfillment routes.  
Reinforcement learning enables robots to:

- **Self-adapt** to new obstacles and layout changes  
- **Retrain quickly** with minimal human intervention  
- **Increase throughput efficiency** while minimizing operational costs  
- **Scale automation** without requiring new rule-based logic  

These advantages make Q-Learning a practical foundation for developing real-world **autonomous warehouse systems** that combine flexibility, efficiency, and intelligence.  

---

## 📁 Repository Contents  

| File | Description |
|------|-------------|
| `copy_of_coding_demo.ipynb` | Full Google Colab notebook with Q-Learning implementation |
| `warehouse-grid.png` | Environment layout visualization |
| `README.md` | Project documentation and overview |

---

## 🔗 Links  

- **Live Colab Notebook:** [Open in Google Colab](https://colab.research.google.com/github/Erin-Weiss/reinforcement-learning/blob/main/copy_of_coding_demo.ipynb)
- **GitHub Repository:** [View Source Code](https://github.com/Erin-Weiss/reinforcement-learning)
- **Portfolio Page:** [View on Portfolio](https://erin-weiss.github.io/articles/RL-Article.html)

