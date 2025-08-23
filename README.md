# Call Centre Optimisation with MDP & Reinforcement Learning (PPO)

This project explores **optimising call centre operations** using two approaches:  
1. **Markov Decision Process (MDP) with Value Iteration**  
2. **Reinforcement Learning with Proximal Policy Optimisation (PPO)**  

The goal is to minimise **customer waiting cost**, reduce **queue length**, and improve **server utilisation** in a two-queue, two-server system. We compare a **model-based (Value Iteration)** method with a **model-free (PPO)** method to highlight their strengths and limitations.

---

## 📌 Part A – Value Iteration with MDP
- Models the call centre as a **Markov Decision Process (MDP)**  
- Uses **Bellman’s equation** in a value iteration framework  
- Optimises skill-based routing: assigning calls to servers based on expertise and service rate  
- Objective: **minimise waiting cost** over a finite horizon  
- Outcome: MDP-based routing reduced **queue length** and **waiting cost** significantly compared to FIFO methods  

---

## 📌 Part B – Reinforcement Learning with PPO
- Develops a **custom Gymnasium environment** for a call centre  
- Trains a **PPO agent** (via Stable-Baselines3) to minimise waiting costs  
- Compares RL results against Value Iteration baseline  
- Key metrics:  
  - ✅ Cumulative waiting cost  
  - ✅ Queue length  
  - ✅ Server utilisation  

**Findings:**  
- PPO → More adaptive, stable, and effective in minimising waiting costs in dynamic environments  
- VI → Performs well initially but degrades with increasing system complexity  

---

## 🧮 Assumptions & Definitions
- **System:** Two types of calls, two servers with different skills & service rates  
- **Arrival process:** Poisson distribution (finite horizon)  
- **Reward function:** Negative waiting cost  
- **Optimal Policy:** Assign calls dynamically to minimise customer waiting time  

---

## 📂 Dataset
**Modified Call Centre Dataset** (two agents only)  
- Features:  
  - Agent  
  - Date / Time  
  - Topic  
  - Answered (Y/N)  
  - Resolved  
  - Speed of Answer (sec)  
  - Average Talk Duration  
  - Satisfaction Rating  

---

## 🛠️ Tools & Technologies
- **Python**  
- Libraries:  
  - Data: `pandas`, `numpy`  
  - Simulation/Math: `scipy`, `scikit-learn`  
  - RL Environment: `gymnasium`, `stable-baselines3`  
  - Visualisation: `matplotlib`, `seaborn`  
- **Jupyter Notebook**  

---

## 📂 Repository Structure
```
.
├── ModifiedCallCenterTwo.xlsx              # Raw dataset
├── Call_Centre_Optimisation_Part_A.ipynb   # MDP + Value Iteration
├── Call_Centre_Optimisation_Part_B.ipynb   # PPO Reinforcement Learning
├── requirements.txt                        # Dependencies
└── README.md                               # Project documentation
```

---

## 🚀 Getting Started

### 1) Clone the repo
```bash
git clone https://github.com/tauhid6069/call-centre-optimisation.git
cd call-centre-optimisation
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Run the notebooks
```bash
jupyter notebook
```

---

## 📊 Results

- **Value Iteration (VI)**  
  - Low queue length in early stages  
  - Performance degraded over time (higher waiting cost and penalties)  

- **Proximal Policy Optimisation (PPO)**  
  - Consistent, stable performance  
  - Lower cumulative penalties  
  - Better server utilisation and reduced waiting times  

**Summary:**  
VI provides a strong mathematical baseline, but PPO adapts better to complex, uncertain environments.

---

## 🔮 Future Work
- Explore advanced PPO variants (e.g., **TR-PPO-RB**)  
- Extend to multi-skill, multi-server call centres  
- Test on **real-world call centre datasets**  
- Explore hybrid MDP + RL frameworks  

---

## 👤 Author
**Md Tauhidul Islam**  
[LinkedIn](https://www.linkedin.com/in/tauhidul-islam) 
