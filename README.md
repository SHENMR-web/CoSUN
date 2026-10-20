# CoSUN

### Interpretable Consensus-Based Shape-Aware Unfolded Networks for Multi-Robot Motion Planning

> [!IMPORTANT]
> **THE SOURCE CODE WILL BE RELEASED AFTER THE PAPER IS PUBLISHED.**
>
> The manuscript is currently under peer review. This repository currently provides the original experimental data and supplementary simulation videos.

## Overview

CoSUN studies distributed motion planning for robots with different body shapes in shared, crowded spaces. It combines explicit body geometry with trajectory consensus: each robot proposes future poses for itself and its neighbors, while owner updates and dual feedback reconcile their plans.

The method unfolds sequential convex programming (SCP) and the alternating direction method of multipliers (ADMM) into fixed-depth optimization layers for model predictive control (MPC). These layers preserve interpretable optimization states and support GPU batch execution. Offline learning adjusts three shared solver scales for the prescribed iteration budget. The accompanying simulations use 10–30 differential-drive robots with polygonal bodies and randomized start and goal configurations.

## Simulation Platform

The CoSUN implementation and simulation experiments are built on [IR-SIM](https://github.com/hanruihua/ir-sim), an open-source robot simulation platform.

## Experimental Data

The three CSV files are provided unchanged from the original experiment outputs.

| File | Contents |
| --- | --- |
| [per_robot.csv](data/per_robot.csv) | Per-robot outcomes, terminal times, path lengths, speeds, and processing times. |
| [per_run.csv](data/per_run.csv) | Per-scene results with seeds, scene hashes, success/collision/timeout rates, motion metrics, processing times, and solver residual statistics. |
| [summary.csv](data/summary.csv) | Both run records and aggregate records; select `record_type=summary` for aggregates. |

The uploaded data cover 100 randomized scenes for each robot count and each of four variants: CoSUN (`ours`), w/o Shaping (`wo_shaping`), w/o Priority (`wo_priority`), and w/o Learning (`wo_learning`). The CoSUN success rates below are the aggregate percentages of successful robots, as reported in `summary.csv`.

| Robots | Scenes | Success (%) |
| --- | --- | --- |
| 10 | 100 | 98.80 |
| 15 | 100 | 97.80 |
| 20 | 100 | 96.10 |
| 25 | 100 | 95.44 |
| 30 | 100 | 93.10 |

The `mp4_file` field in `summary.csv` records historical local output paths. The available demonstration videos are linked below.

## Simulation Videos

Representative successful runs are shown for each robot count. Click a video to play it directly on this page. These examples complement the aggregate results above.

### 10 Robots

https://github.com/user-attachments/assets/786b26ff-0e45-42df-9860-7c2100155576

[Download original MP4](<videos/success_episode_n10_T5_goals-random_a0p0992063-0p238095m2_ar1p3_seed100-24_m0p2_wc100_g1_ref-current_wp12-20_vp1_20261019_195722_398679.mp4>)

### 15 Robots

https://github.com/user-attachments/assets/9676bf05-22a9-4bd2-a72b-b17539754d14

[Download original MP4](<videos/success_episode_n15_T5_goals-random_a0p0992063-0p238095m2_ar1p3_seed97-26_m0p2_wc100_g1_ref-current_wp12-20_vp1_20261019_201516_255083.mp4>)

### 20 Robots

https://github.com/user-attachments/assets/8676e868-7694-4a90-9efa-423208575ca4

[Download original MP4](<videos/success_episode_n20_T5_goals-random_a0p0992063-0p238095m2_ar1p3_seed97-27_m0p2_wc100_g1_ref-current_wp12-20_vp1_20261019_202416_186622.mp4>)

### 25 Robots

https://github.com/user-attachments/assets/a6120c68-cde6-4976-9061-1884ef8e7dcc

[Download original MP4](<videos/success_episode_n25_T5_goals-random_a0p0992063-0p238095m2_ar1p3_seed96-27_m0p2_wc100_g1_ref-current_wp12-20_vp1_20261019_203257_953641.mp4>)

### 30 Robots

https://github.com/user-attachments/assets/f8d69333-4b24-4a22-adc3-e3cb72cc7d4b

[Download original MP4](<videos/success_episode_n30_T5_goals-random_a0p0992063-0p238095m2_ar1p3_seed100-27_m0p2_wc100_g1_ref-current_wp12-20_vp1_20261019_204245_874726.mp4>)

## Code Availability

**The source code will be made publicly available in this repository after the paper is published.**
