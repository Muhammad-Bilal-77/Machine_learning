# Reinforcement Learning: Teaching an AI to play Tic-Tac-Toe

Welcome to the Reinforcement Learning (RL) section! This is one of my personal favorite projects in this repository. Unlike Supervised Learning (where we feed the algorithm the "correct" answers) or Unsupervised Learning (where the algorithm finds hidden clusters), Reinforcement Learning is about **teaching an agent to make decisions through trial and error**.

### The Goal
The objective of this project is to build an AI agent from scratch that learns how to play a perfect game of Tic-Tac-Toe without ever being explicitly programmed with the rules of strategy. It doesn't know what a "corner" is or what a "block" is; it has to figure it out mathematically.

### How the RL Agent Learns (Q-Learning)
I implemented a **Q-Learning** algorithm to solve this environment. Here is how the AI learns:
1. **The Environment**: I built a custom Tic-Tac-Toe environment. The board has 9 tiles, leading to thousands of possible board states. 
2. **Exploration vs Exploitation**: When the AI starts, it plays randomly (Exploration). Over time, as it figures out what moves lead to a win, it starts favoring those known good moves (Exploitation). 
3. **The Q-Table**: The AI maintains a massive internal memory bank called a Q-Table. Every time it makes a move, it updates this table. If a move leads to a win, that specific board state gets a positive reward (+). If it leads to a loss, it gets a negative penalty (-).
4. **Self-Play**: The true power of this project is that the AI plays thousands of games against *itself* (or against a random bot). By constantly trying to beat strategies, it eventually discovers the optimal strategy (where the worst-case scenario is a draw).

### What's Inside the Notebook?
- **Custom Environment**: I coded the game mechanics, win-state checking, and board rendering manually to act as the gym for the AI.
- **The AI Class**: The Q-learning agent is built with logic for updating Q-values based on tracking immediate rewards and calculating future state values.
- **Training Loop**: The agent plays simulated games at hyper-speed to populate its Q-Table and master the game!