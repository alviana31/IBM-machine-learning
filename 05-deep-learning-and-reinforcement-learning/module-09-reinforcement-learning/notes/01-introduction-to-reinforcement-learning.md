# Introduction to Reinforcement Learning

## 1. What Is Reinforcement Learning?

Reinforcement Learning (RL) is a machine learning approach in which an agent learns by interacting with an environment.

The agent takes actions and receives rewards based on the results of those actions.

Unlike supervised learning, reinforcement learning does not rely on predefined labels for every action. Instead, the agent learns from feedback received through interaction.

## 2. Main Components

Reinforcement Learning consists of several important components:

### Agent

The agent is the decision-making entity that interacts with the environment.

### Environment

The environment is the system or situation in which the agent operates.

### Action

An action is a decision or movement selected by the agent.

### Reward

A reward is feedback received by the agent after taking an action.

The reward helps the agent estimate whether an action is beneficial.

### Policy

A policy is a strategy that maps states to actions. It determines which action the agent should take in a particular state.

## 3. How Reinforcement Learning Works

The general process is:

1. The agent observes the current state of the environment.
2. The agent selects an action based on its policy.
3. The environment responds to the action.
4. The agent receives a reward.
5. The agent uses the feedback to improve its decision-making.
6. The process continues as the agent learns to maximize expected rewards over time.

```text
       Environment
            |
         State
            |
            v
          Agent
            |
          Action
            |
            v
       Environment
            |
          Reward
            |
            v
          Agent
```

## 4. The Role of Rewards

At the beginning, the agent may not know which actions will produce the best results.

It estimates the rewards associated with different actions through experience.

The objective is not simply to obtain a high reward from one action, but to maximize the expected reward over time.

## 5. Policy

A policy defines how an agent chooses actions based on the current state.

It can be represented as:

```text
State → Policy → Action
```

Through interaction and feedback, the agent improves its policy to make better decisions.

## 6. Reinforcement Learning vs. Typical Machine Learning

| Aspect | Typical Supervised Learning | Reinforcement Learning |
|---|---|---|
| Feedback | Known target labels | Rewards from interaction |
| Learning Process | Learns from labeled examples | Learns through actions and feedback |
| Environment | Usually a fixed dataset | An environment that responds to actions |
| Objective | Predict target values or classes | Maximize expected rewards over time |

## 7. Key Takeaways

- Reinforcement Learning involves an agent interacting with an environment.
- The agent selects actions and receives rewards.
- A policy maps states to actions.
- The agent learns from feedback rather than predefined labels.
- The main objective is to maximize expected rewards over time.