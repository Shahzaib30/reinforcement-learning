# Q-Learning CartPole Training Analysis (10,000 Episodes)

This document explains what happened during the Reinforcement Learning training process in simple terms.

## 1. The Setup
We used **Q-Learning**, a fundamental AI algorithm, to teach a computer how to balance a pole on a moving cart. 

* **The Environment:** CartPole-v1.
* **The Problem:** The computer gets 4 decimal numbers (position, velocity, angle, angular velocity).
* **The Solution:** We used "Binning" to turn those decimals into simple integers (like putting them into buckets) so the AI could remember them in a **Q-Table**.

## 2. Phase 1: Rapid Learning (Episodes 1–1,000)
At the start, the AI knew nothing. 
* **Action:** It moved randomly because **Epsilon** was high.
* **Result:** It quickly learned that keeping the pole upright for any amount of time is good.
* **Observation:** The reward jumped from ~20 to ~180.

## 3. Phase 2: The Long Plateau (Episodes 1,000–9,900)
For most of the 10,000 episodes, the reward stayed around **185**. 
* **Why?** We kept **Alpha (Learning Rate) constant**. 
* Imagine a student who always listens to the very last thing they heard with 100% intensity. Because the AI never "slowed down" its learning, it kept over-correcting its mistakes.
* **Convergence:** It reached a point where it was "good enough" but couldn't get "perfect" because the constant Alpha caused it to oscillate (wobble) around its best strategy.

## 4. Phase 4: The Late Breakthrough (Episode 10,000)
Suddenly, the reward jumped to **360.9**.
* **What happened?** Even though the AI was mostly acting on what it knew (low Epsilon), that 1% chance of trying something new finally paid off. 
* It discovered a specific sequence of moves that handled the "extreme" tilts of the pole better than before.

## 5. Summary of Tasks
1.  **Constant Alpha:** By not decreasing Alpha, we ensured the agent never stopped learning, but this created a "noisy" plateau where the agent stayed around 180-190 reward for a long time.
2.  **CartPole Result:** The agent successfully learned to balance the pole, moving from a few seconds of stability to several hundred steps of success.