## Call Centre Optimisation using Markov Decision Process (MDP) and Reinforcement Learning (Proximal Policy Optimisation (PPO))

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
