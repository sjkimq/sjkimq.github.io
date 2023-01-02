---

layout: post
title:  "Shared Autonomy via Deep Reinforcement Learning"
categories: shared-autonomy
tag: [robotics, shared-autonomy]

---

# Shared Autonomy via Deep Reinforcement Learning [1]

- 카메라가 달린 드론을 원격으로 조종해서 착륙
  - 다양한 원인으로 사람이 원격으로 제어하기 힘들다
    - unfamiliar flight dynamics
    - terrain
    - network latency

- Shared autonomy
  - human controlled user input과 automated assistance를 augmenting 한다

## Background
- 1949
- 1969
- 1980
- 2015 Review of the DARPA Robotics Challenge
  - interfacing between a human operator and a remote-controlled robot remains a challenge
  - the most cost effective research area to improve robot performance is Human-Robot Interaction....
  - The biggest enemy of robot stability and performance in the DRC was operator errors.
  - Developing ways to avoid and survive operator errors is crucial for real-world robotics.
  - Human operators make mistakes under pressure, especially without extensive training and practice in realistic conditions.
- possible solution
  - inferring the user's goals and autonomously acting to achieve them
  - but require prior knowledge about the world
    - a dynamics model that predicts the consequences of taking a given action in a given state of the environment
    - the set of possible goals for the user
    - an observation model that describes the user's behavior given their goal
- Model-based shared autonomy algorithms
  - well-suited for knowledge can be directly hard-coded or learned
  - challenged by unstructured environments with ill-defined goals and unpredictable user behavior
- model-free shared autonomy via deep reinforcement learning
  - Deep reinforcement learning
    - uses neural network function approximation
      - to tackle the curse of dimensionality in high-dimensional, continuous state and action spaces
  - can deep reinforcement learning be useful for building flexible and practical assistive systems?


## Model-Free RL with a Human in the Loop
- To enable shared-control teleoperation with minimal prior assumptions
  - a model-free deep reinforcement learning algorithm for shared autonomy
    - key idea
      - to learn an end-to-end mapping from environmental observation and user input to agent action
      - with task reward as the only form of supervision
      - agent's perspective
        - the user acts like 
          - a prior policy that can be fine-tuned
          - an additional sensor generating observations from which the agent can implicitly decode the user's private information
      - user's perspective
        - agent behaves like an adaptive interface
          - that learns a personalized mapping from user commands to actions that maximizes task reward
    - core challenge
      - adapting standard deep RL techniques to leverage control input from a human without significantly interfering with the user's feedback control loop or tiring them with a long training period
      - To address these issues
        - used deep Q-learning to learn an approximate state-action value function that computes the expected future return of an action given the current environmental observation and the user's input.
        - Equipped with this value function, the assistive agent executes the closest high-value action to the user's control input.
        - The reward function for the agent is a combination of known terms computed for every state, and a terminal reward provided by the user upon succeeding or failing at the task.


## Learning to Assist





## Incorporating User Input


## Q-Learning with User Control


## User Studies

### The Lunar Lander Game

### Quadrotor Landing Task

## What's Next?


## References
[1] [Shared Autonomy via Deep Reinforcement Learning](https://bair.berkeley.edu/blog/2018/04/18/shared-autonomy/)





