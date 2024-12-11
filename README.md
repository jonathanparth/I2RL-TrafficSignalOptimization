# **Traffic Signal Control using RL**

## 🚦 **Overview**
This project implements **Reinforcement Learning (RL)** algorithms to optimize traffic signal control for a single intersection in a SUMO (Simulation of Urban MObility) environment (**SUMO-GUI will not work in Google Colab because Colab does not support GUI-based applications or visual display rendering like a standard desktop environment.**). The project is designed as a **single Jupyter Notebook** for use in **Google Colab**.  

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
   - Four different reward functions:
        1. **diff-waiting-times**
        2. **queue**
        3. **pressure**
        4. **combined**

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
   - Open the notebook in Google Colab.

### 2. **Environment Setup**
   - Run the initial setup cells to:
     - Install **SUMO** tools.
     - Upload `.net.xml` (network) and `.rou.xml` (route) files. *Currently **only** "single-intersection.net.xml" and "single-intersection-horizontal.net.xml" possible!*

---

## 💰 **Reward Functions**

| **Reward Function**   | **Objective**             | **Description**                                | **How It Works**                                   |
|------------------------|---------------------------|-----------------------------------------------|--------------------------------------------------|
| **`diff-waiting-time`** | Minimize waiting time     | Penalizes total waiting time for vehicles.     | -(Waiting Time)                     |
| **`queue`**            | Minimize queue length     | Penalizes number of halted vehicles.           | -(Halted Vehicles)                  |
| **`pressure`**         | Balance traffic flow      | Balances incoming and outgoing traffic flow.   | (Outgoing Vehicles) - (Incoming Vehicles) |
| **`combined`**         | Optimize multiple metrics | Combines waiting, queue, pressure, and balance.| Waiting Penalty + Queue Penalty + Balance Penalty + Change Penalty + Flow Reward               |

---

## ⚙️ **Training the RL Models**

### 1. **Q-Learning**
  - Adjust hyperparameters (alpha, gamma, epsilon) if needed.
  - Execute RandomSearch Algorithm to find optimal hyperparameters
  - Results include:
    - Learning curves
    - Average waiting time and throughput
    - Comparison with fixed-timing benchmark.
      
### 2. **SARSA**
  - SARSA uses slightly different hyperparameters for exploration and learning rate decay.
  - Execute RandomSearch Algorithm to find optimal hyperparameters
  - Results include:
    - Learning curves
    - Average waiting time and throughput
    - Comparison with fixed-timing benchmark.

### 3. **DQN**
  - Implements a Deep Q-Network using Stable Baselines3 library.
  - Execute RandomSearch Algorithm to find optimal hyperparameters
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
   
      ![image](https://github.com/user-attachments/assets/c498e235-c9a1-4eae-81fe-ddfe35c0209d)

  - Generated Plots
    
      **1. Average Reward Comparison**
      Comparison of rewards across all reward functions.
      ![image](https://github.com/user-attachments/assets/9251c31c-ed99-43c8-919e-cc573fc02b33)


      **2. Improvement Over Fixed-Timing**
      Improvement (%) of RL algorithms compared to the fixed-timing benchmark.
      ![image](https://github.com/user-attachments/assets/8e836ace-40e8-4d00-8c6e-1a23607a0579)


      **3. Average Waiting Time**
      Comparison of waiting times for all algorithms.
      ![image](https://github.com/user-attachments/assets/8704839e-4471-44ae-8c6a-40fe8afe93c8)


      **4. Throughput Comparison**
      Number of vehicles processed by the system.
      ![image](https://github.com/user-attachments/assets/4107e6d2-bf3f-40d4-b2a4-25cb2fe3c702)


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
  - Compatibility for additionaly .net and .route files
  - Support for multi-agent RL algorithms.
  - Integration with advanced RL algorithms (PPO, A3C).
