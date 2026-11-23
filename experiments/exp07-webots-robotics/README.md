# Experiment 07 — Webots Robotics Simulation

**Name:** Naman Chanana
**SAP ID:** 500119485
**Roll No.:** R2142230993
**Batch:** 2 — AI & ML

## Aim

Study autonomous robot navigation in Webots using:

- an e-puck swarm with reactive/Braitenberg control
- a Pioneer 3-DX robot using lidar-based navigation

The experiment evaluates how controller parameters affect robot movement, environment coverage, path length, speed, and stuck time.

## Environment

- Webots R2025a
- Python 3
- e-puck robots
- Pioneer 3-DX
- SICK lidar
- Windows

## Swarm Experiment

Three 60-second runs were performed with different cruise-speed settings.

| Cruise | Coverage |
|---:|---:|
| 0.5 | 58% |
| 0.8 | 61% |
| 1.1 | **73%** |

Increasing cruise speed improved environment coverage, although the highest speed also produced more stuck time for some robots.

## Pioneer Experiment

Three 60-second runs were performed using different safety-bubble parameters.

| Bubble | Path Length | Mean Speed | Stuck | Coverage |
|---:|---:|---:|---:|---:|
| 0.25 | 24.85 m | 0.418 m/s | 0% | 20% |
| **0.40** | 25.38 m | 0.426 m/s | 0% | **23%** |
| 0.60 | 26.11 m | 0.439 m/s | 0% | 21% |

All Pioneer runs completed without becoming stuck. A bubble value of **0.40** produced the highest measured coverage.

## Files

- `swarm_arena.wbt` — e-puck swarm world
- `pioneer_lidar.wbt` — Pioneer lidar world
- `controllers/` — robot controllers
- `analysis/` — metrics and trajectory plotting utilities
- `run_experiment.py` — automated Webots experiment runner
- `results/` — CSV trajectories and plots from the six executed runs

## Conclusion

The experiment demonstrates autonomous navigation with two different robotic platforms. Increasing e-puck cruise speed increased swarm coverage, while the Pioneer experiment showed that obstacle-safety parameters influence exploration behaviour. Automated trajectory logging allowed the different controller configurations to be compared quantitatively.