## Call Centre Optimisation Using Markov Decision Process (MDP) and Reinforcement Learning (Proximal Policy Optimisation (PPO))

### Part A
This study involves the optimisation of skill-based routing that assigns incoming calls to agents based on specific skills required to address customer needs effectively. 
Unlike the traditional first-in-first-out method, skill-based routing improves the service quality and reduces waiting time as it considers both call types and agent expertise. 
To address the challenges in call centre operations, including call volume, agent availability and skills, variable service rate, and diverse types of calls, we propose a framework based on
Markov Decision Process (MDP). The framework aims to obtain a method that can dynamically maintain the queue and assign incoming calls to appropriate agents. 
In this study, we consider two types of incoming calls in a finite horizon handled by two servers with different skill sets and different service rates. 
The goal of part A of this project is to derive an optimal policy to minimise the total customer waiting cost using Bellman’s equation in a value iteration process. 
The outcome shows a significant reduction in waiting cost and queue length. This highlights the effectiveness of skill-based routing based on MDP in a real-time call centre environment.

### Part B
Part B involves the requirement of a reinforcement learning model to optimise call centre operations in a basic two-queue, two-server system. The goal is to compare the reinforcement
learning outcome with the value iteration method developed in Part A of this study. The study validates whether the system is following the assumptions taken into consideration in Part A
and emphasises the utilisation of a proximal policy optimisation (PPO) method. The PPO model is trained on a slightly modified call centre dataset, and a value iteration algorithm using
Bellman’s equation is implemented. A custom environment is developed to simulate the models to evaluate and compare the model performance. Several key operational metrics, including
cumulative waiting cost, waiting cost per episode, queue length, and server utilisation is considered to evaluate performance. The results suggest that while PPO learns more effectively in terms of
minimisig waiting cost and queue lengths and server utilisation, the value iteration approach performs well in the initial stages but degrades when complexity increases. This comparison highlights
the strengths and limitations of models that directly learn from experience by interacting with the environment (PPO) and models that build on the environment (Value iteration).

## Assumptions and Definitions
We consider a simple call centre where two types of incoming calls are handled by two servers with different service rates. We consider the arrival of incoming calls in a finite horizon
and it follows Poisson arrival rates. We develop an optimal policy for real-time call assignments using Bellman’s equation in a value iteration framework. The policy aims to mininmise the customer waiting cost.
We determine the most effective assignment strategy for every possible state by iterating over a finite time horizon and incorporating a reward function that penalises long waits.

1. Optimal policy: Allocating the best server to different types of calls.
2. Waiting cost: Dynamically maintaining queues by assigning calls to appropriate servers to minimise the customer wait time in queues.
3. Reward: Reward refers to the negative waiting cost incurred at a given time.


### Technologies & Tools Used
Python

Pandas, NumPy, Scikit-learn, scipy, gymnasium, stable_baselines3

Matplotlib, Seaborn

Jupyter Notebook


### Dataset
Modified call centre data (Number of agents revised to two)

Includes Agent, Date, Time, Topic, Answered (Y/N), Resolved, Speed of answer in seconds, AvgTalkDuration, Satisfaction rating

### Project Structure
📁 ModifiedCallCenterTwo.xlsx-----------------# Raw dataset

📁 Call_Centre_Optimisation_Part_A.ipynb------# Jupyter notebook - Part A

📁 Call_Centre_Optimisation_Part_B.ipynb------# Jupyter notebook - Part B

### Process Overview (Part A and B Combined)
1. Define environment
2. Mathematical model using MDP
3. Simulating the model using Value Iteration (VI)
4. Find an optimal policy to minimise call centre waiting time and queue length
5. Use a reinforcement learning model (PPO) and compare output from VI

### Results
We compared a model-free Proximal Policy Optimization (PPO) approach with a model based Value Iteration (VI) method to optimise operations of call centre in a two-queue, two-server system. The
primary goal is to minimise the call centre waiting cost by optimising the queue lengths and server utilisation.
It appeared that the value iteration maintained a low queue length initially, however, the performance degrades over time which was reflected in sharp rise in cumulative penaltiy and higher number of customers in
the queues in the final stages. This highlights the limitations of the method in a stochastic environment. In contrast, Proximal Policy Optimisation (PPO) showed resilience and stability across the entire simulation with lower cumulative penalties,
consistent queue length and higher server utilisation compared to the Value Iteration derived policy. It is undeniable that the value iteration provided a strong baseline
derived from the mathematical model. However, PPO methods adaptability in dynamic and unseen states highlights the efficiency of RL in complex and uncertain environments.
Additional research could improve this study further including exploring more advanced PPO variants such as TR-PPO-RB (Trust Region PPO with Rollback ) and exploring more complex call centre environment.
