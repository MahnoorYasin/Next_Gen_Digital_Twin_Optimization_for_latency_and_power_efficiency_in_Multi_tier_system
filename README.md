# Next-Gen Digital Twin Optimization for Latency and Power Efficiency in Multi-Tier Systems

## Overview
This project addresses the challenges of latency and power efficiency in multi-tier computing systems by leveraging digital twins and advanced machine learning techniques. The goal is to optimize resource allocation, task offloading, and digital twin migration to ensure real-time synchronization and minimal latency for mobile users in dynamic network environments.

---

## Problem Statement
Multi-tier computing systems, which integrate edge servers and cloud centers, face significant challenges in managing user mobility and resource constraints. Key issues include:
1. **Latency in Digital Twin Synchronization**: Delays occur when users move between edge servers, disrupting real-time updates of their digital twins.
2. **Dynamic Resource Allocation**: Traditional deterministic methods struggle to adapt to varying network conditions and user demands.
3. **Efficient Task Offloading**: Balancing computational loads across edge and cloud resources while minimizing latency is complex.
4. **Scalability**: Existing solutions lack the flexibility to handle heterogeneous resources and unpredictable network conditions.

---

## Solution Approach
The project proposes a dynamic framework combining reinforcement learning (RL) and predictive analytics to optimize digital twin migration and resource allocation. Key techniques include:

### 1. **Latency Reduction with Dijkstra's Algorithm**
   - **Purpose**: Minimize communication latency between users and servers.
   - **Implementation**: The network is modeled as a graph with weighted edges (latency). Dijkstra's algorithm computes the shortest path for efficient task routing.
   - **Formula**:  
     \[
     P_{opt} = \arg \min_{P \in P} \sum_{e \in P} l(e)
     \]

### 2. **Dynamic Resource Allocation with Q-Learning**
   - **Purpose**: Decentralized decision-making for optimal server selection.
   - **Implementation**: Q-Learning updates Q-values based on rewards (successful/failed allocations). The policy selects servers to maximize resource utilization.
   - **Formula**:  
     \[
     Q(s_t, a_t) \leftarrow Q(s_t, a_t) + \alpha \left[r_t + \gamma \max_{a_{t+1}} Q(s_{t+1}, a_{t+1}) - Q(s_t, a_t)\right]
     \]

### 3. **Digital Twin Migration with Proximal Policy Optimization (PPO)**
   - **Purpose**: Optimize migration decisions to reduce latency.
   - **Implementation**: PPO trains a policy to migrate digital twins efficiently, using a clipped objective function for stability.
   - **Formula**:  
     \[
     L^{CLIP}(\theta) = \mathbb{E}_t \left[\min \left(r_t(\theta) \hat{A}_t, \text{clip}(r_t(\theta), 1-\epsilon, 1+\epsilon) \hat{A}_t\right)\right]
     \]

### 4. **Real-Time Synchronization with LSTM**
   - **Purpose**: Predict latency for real-time updates.
   - **Implementation**: LSTM models temporal patterns in synchronization data to forecast system states.

### 5. **Cooperative Decision-Making with Multi-Agent RL (MARL)**
   - **Purpose**: Enable collaboration among edge servers for task allocation.
   - **Implementation**: Agents learn joint policies to maximize collective rewards.

### 6. **System Complexity Reduction with PCA**
   - **Purpose**: Simplify high-dimensional data for analysis.
   - **Implementation**: PCA reduces feature dimensions while preserving critical information.

---

## Results
The framework demonstrated significant improvements in key metrics:
1. **Latency Reduction**:  
   - Worst-case latency dropped from **1000 ms** to **4.76 ms** after optimization.
   - Average synchronization latency: **12.59 ms** (LSTM predictions: **0.04–0.06 ms** per user).

2. **Resource Utilization**:  
   - Server allocation efficiency reached **100%** (Q-Learning).
   - Average server utilization: **54%** (up from baseline).

3. **Task Allocation**:  
   - Total latency components (migration, communication, computation) ranged from **0.23 ms to 1.14 ms** per user.

4. **Learning Performance**:  
   - Q-Learning achieved stable rewards (**~10 per episode**) after 100 episodes.  
   - MARL improved cooperative task distribution by **20%**.

---

## Dependencies
- Python 3.8+
- Libraries: `pandas`, `numpy`, `tensorflow`, `networkx`, `scikit-learn`, `matplotlib`, `seaborn`.

---

## Contributors
- Alishba Bacha  
- Mahnoor Yasin  

For questions, contact:  
- alishbabacha@gmail.com  
- mahnooryasin660@gmail.com  

---
