# AISR Lab — Semester 7

Laboratory experiments for **Artificial Intelligence and Smart Robotics (AISR)** completed during Semester 7.

**Student:** Naman Chanana
**SAP ID:** 500119485
**Roll No.:** R2142230993
**Batch:** 2 — AI & ML

## Experiments

| # | Experiment | Environment |
|---|---|---|
| 1 | Time/Frequency Domain Analysis & Pendulum Simulation | Google Colab |
| 2 | Eight Queens — Generate-and-Test & Backtracking | Google Colab |
| 3 | Breadth-First Search & Depth-First Search | Google Colab |
| 4 | Hill Climbing & Random Restarts | Google Colab |
| 5 | Tabular Q-Learning | Google Colab |
| 6 | Neural Network for XOR | Google Colab |
| 7 | Webots Robotics — e-puck Swarm & Pioneer Lidar Navigation | Webots R2025a |
| 8 | Cross-Embodiment Manipulation Transfer with PyBullet | Google Colab |

## Highlights

### Experiment 1 — Signals & Pendulum

FFT recovered the expected **5 Hz, 20 Hz and 50 Hz** signal components. The experiment also demonstrates spectral leakage, aliasing and the increase in pendulum period at large initial angles.

### Experiment 2 — Eight Queens

Both generate-and-test and backtracking found all **92 solutions**, including **12 fundamental solutions** after accounting for rotations and reflections. Backtracking was substantially faster as board size increased.

### Experiment 3 — BFS & DFS

BFS and DFS were compared on maze-search problems. In a maze containing alternative routes, BFS returned a **40-step shortest path**, while DFS returned a longer **54-step path**.

### Experiment 4 — Hill Climbing

Plain hill climbing solved the Eight Queens problem from **12.5%** of random starts. Random restarts greatly improved reliability, reaching **97.5% success with 20 restarts** in the executed trials.

### Experiment 5 — Q-Learning

A tabular Q-learning agent learned an optimal **10-step Grid World path**. Exploration rate affected convergence and final policy quality, with learned policies reaching the goal for all tested settings.

### Experiment 6 — Neural Network for XOR

A **2–4–1 neural network implemented from scratch using NumPy** successfully learned XOR. The best run produced predictions approximately:

```text
[0.002, 0.998, 0.998, 0.003]
```

The experiment also demonstrates why symmetric zero initialization prevents effective learning.

### Experiment 7 — Webots Robotics

Real Webots R2025a simulations were performed using:

- an e-puck robot swarm with reactive navigation
- a Pioneer 3-DX robot with lidar-based navigation

Three swarm and three Pioneer parameter configurations were executed and logged.

The highest swarm coverage was **73%** at cruise speed `1.1`.

For the Pioneer experiments, a safety bubble of `0.40` produced the highest measured coverage of **23%**, with **0% stuck time**.

See [`exp07-webots-robotics`](experiments/exp07-webots-robotics/) for the worlds, controllers, trajectory CSVs and generated plots.

### Experiment 8 — Cross-Embodiment Transfer

Pick-and-place manipulation was evaluated across:

- KUKA iiwa
- Franka Panda
- xArm6
- scaled KUKA Mini

Naive joint-space replay failed to transfer to different embodiments, while task-space control with robot-specific inverse kinematics achieved **100% success** on KUKA iiwa, Franka Panda and xArm6.

Embodiment-agnostic behaviour cloning also transferred substantially better than policies relying directly on robot-specific proprioceptive state.

## Repository Structure

```text
experiments/
├── exp01-signals-pendulum/
├── exp02-eight-queens/
├── exp03-bfs-dfs/
├── exp04-hill-climbing/
├── exp05-q-learning/
├── exp06-neural-xor/
├── exp07-webots-robotics/
└── exp08-cross-embodiment/
```

Experiments 1–6 and 8 contain notebooks with outputs from the actual executed Google Colab runs.

Experiment 7 contains the Webots worlds, controllers, analysis utilities, and results from the actual executed robot simulations.

## Tools

- Python
- NumPy
- Matplotlib
- SciPy
- PyBullet
- Webots R2025a
- Google Colab

## Notes

- Large downloaded dependencies and simulator installations are not stored in this repository.
- Experiment 7 requires Webots R2025a for reproduction.
- PyBullet in Experiment 8 runs in headless/DIRECT mode and does not require a graphical simulation window.