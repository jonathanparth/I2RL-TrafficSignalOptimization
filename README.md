# **Traffic Signal Control using RL in SUMO**

## 🚦 **Overview**
This project implements **Reinforcement Learning (RL)** algorithms to optimize traffic signal control for a single intersection in a SUMO (Simulation of Urban MObility) environment. The project is designed as a **single Jupyter Notebook** for use in **Google Colab**.  

The algorithms used are:
- **Q-Learning**
- **SARSA**
- **Deep Q-Learning (DQN)**  

The goal is to minimize vehicle waiting times, optimize throughput, and compare RL algorithms against a **Fixed-Timing Benchmark**.

---

## 📂 **Project Structure**

The project consists of a **single Jupyter Notebook** file containing all the logic, split into the following sections:

1. **Environment Setup**  
   - Install SUMO tools and dependencies.  
   - Upload and dynamically load **network** (`.net.xml`) and **route** (`.rou.xml`) files.  

2. **Custom SUMO Environment**  
   - `SumoSingleIntersectionEnv`: A custom Gymnasium environment designed for a single traffic intersection.

3. **Fixed-Timing Benchmark**  
   - A baseline model using fixed-duration traffic signals for comparison.

4. **Training RL Algorithms**  
   - Q-Learning  
   - SARSA  
   - Deep Q-Learning (DQN)

5. **Evaluation and Visualization**  
   - Compare RL models against the Fixed-Timing Benchmark.  
   - Generate meaningful visualizations.

---

## 🚀 **Setup Instructions**

To get started, follow these steps:

### 1. **Open the Notebook**
   - Open the notebook (`traffic_signal_rl.ipynb`) in Google Colab.

### 2. **Environment Setup**
   - Run the initial setup cells to:
     - Install **SUMO** tools.
     - Upload `.net.xml` (network) and `.rou.xml` (route) files.

---

## ⚙️ **Training the RL Models**

### 1. **Q-Learning**
  - Adjust hyperparameters (alpha, gamma, epsilon) if needed.
  - Results include:
    - Learning curves
    - Average waiting time and throughput
    - Comparison with fixed-timing benchmark.
      
### 2. **SARSA**
  - SARSA uses slightly different hyperparameters for exploration and learning rate decay.
  - Results include:
    - Learning curves
    - Average waiting time and throughput
    - Comparison with fixed-timing benchmark.

### 3. **DQN**
  - Implements a Deep Q-Network using Stable Baselines3 library.
  - Results include:
    - Learning curves
    - Average waiting time and throughput
    - Comparison with fixed-timing benchmark.

---

### 📊 **Benchmark and Evaluation**

  - Compare Q-Learning, SARSA, and DQN against the Fixed-Timing Benchmark.
  - Results include:
    - Average rewards
    - Improvement percentages
    - Average waiting times
    - Throughput

  - Generated Plots
    - Average Reward Comparison
      Comparison of rewards across all reward functions.

    - Improvement Over Fixed-Timing
      Improvement (%) of RL algorithms compared to the fixed-timing benchmark.

    - Average Waiting Time
      Comparison of waiting times for all algorithms.

    - Throughput Comparison
      Number of vehicles processed by the system.

---

### 🛠️ **Dependencies**
The project uses the following tools and libraries:

  - SUMO (Simulation of Urban MObility) --> only necessary for GUI
  - Python Libraries:
    - gymnasium
    - numpy
    - matplotlib
    - pandas
    - stable-baselines3
    - google.colab for file uploads

---

### 📈 **Results**
The performance of Q-Learning, SARSA, and DQN algorithms is evaluated and compared to the fixed-timing benchmark on:

  - Average Reward (efficiency of traffic control).
 - Improvement Percentage over fixed-timing.
 - Average Waiting Time (time vehicles wait at intersections).
 - Throughput (vehicles processed).
 - Visualizations include:
   - Average Reward Comparison.
   - Improvement Over Fixed-Timing.
   - Average Waiting Time.
   - Throughput Comparison.

---

### 📚 **References**
  - SUMO Documentation
  - Stable Baselines3
  - Reinforcement Learning Algorithms (Q-Learning, SARSA, DQN).

---

### 🎯 **Future Improvements**
  - Multi-intersection environments.
  - Support for multi-agent RL algorithms.
  - Integration with advanced RL algorithms (PPO, A3C).
