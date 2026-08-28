# Reinforcement Learning Sandbox

A sandbox for implementing and analyzing reinforcement learning algorithms, built on
**Gymnasium** environments with **Stable Baselines3** and **PyTorch** available for
future agent training. Managed with `uv` for fast, reproducible Python environments.

## What's Here

### Q-Learning on CartPole (10,000 episodes)

`cartpool-rl-lab-4-23-2026.ipynb` implements tabular Q-Learning on `CartPole-v1`:
continuous state values (position, velocity, angle, angular velocity) are discretized
into bins so they fit into a Q-table, then trained over 10,000 episodes.

`cartpool-rl-lab.md` is a plain-language write-up of the training run, covering:
- **Rapid learning** (episodes 1–1,000): reward jumps from ~20 to ~180 as the agent
  moves past random exploration.
- **Long plateau** (episodes 1,000–9,900): reward oscillates around ~185 because the
  learning rate (alpha) is held constant instead of decayed, so the agent keeps
  over-correcting instead of settling.
- **Late breakthrough** (episode 10,000): reward jumps to 360.9 when exploration
  (epsilon) turns up a better move sequence for handling extreme pole tilts.

## Setup

```bash
uv sync
uv run main.py
```

To run the CartPole lab notebook:

```bash
uv run jupyter notebook cartpool-rl-lab-4-23-2026.ipynb
```

## Roadmap

Stable Baselines3, TensorBoard, and torchvision are already in the dependency set for
follow-up work benchmarking PPO/DQN/SAC against the tabular Q-Learning baseline above.

## Tech Stack

Python 3.14, Gymnasium, Stable Baselines3, PyTorch, TensorBoard, `uv`.
