# CPU Scheduling Visualizer

This project provides C++ implementations and visualizations for a variety of CPU scheduling algorithms. The supported algorithms include First Come First Serve (FCFS), Round Robin (RR), Shortest Process Next (SPN), Shortest Remaining Time (SRT), Highest Response Ratio Next (HRRN), Feedback (FB), and Aging.

## Table of Contents

- [Overview](#overview)
- [Algorithms](#algorithms)
  - [FCFS](#fcfs)
  - [Round Robin (RR)](#round-robin-rr)
  - [SPN](#spn)
  - [SRT](#srt)
  - [HRRN](#hrrn)
  - [Feedback (FB)](#feedback-fb)
  - [Feedback with Variable Quantum (FBV)](#feedback-with-variable-quantum-fbv)
  - [Aging](#aging)
- [Input Format](#input-format)
- [Contributors](#contributors)

## Overview

This tool is designed to help users understand and analyze the behavior of different CPU scheduling strategies. It can be used for both educational and experimental purposes.

## Algorithms

### FCFS

First Come First Serve (FCFS) schedules processes in the order they arrive. It is simple and non-preemptive, but can result in long waiting times for short processes if a long process arrives first.

### Round Robin (RR)

Round Robin divides CPU time into fixed or variable time slices (quanta) and cycles through processes in the ready queue. Each process receives a time slice in turn, which helps prevent starvation but may increase context switching overhead.

### SPN

Shortest Process Next (SPN) selects the process with the shortest required CPU time from the ready queue. It is non-preemptive and aims to reduce average waiting time, but longer processes may experience delays.

### SRT

Shortest Remaining Time (SRT) is a preemptive version of SPN. If a new process arrives with a shorter remaining time than the currently running process, it preempts the CPU.

### HRRN

Highest Response Ratio Next (HRRN) schedules the process with the highest response ratio, calculated as (waiting time + service time) / service time. This approach balances fairness and efficiency.

### Feedback (FB)

Feedback scheduling uses multiple queues with different priority levels. Processes move between queues based on their behavior and CPU usage, allowing the system to adapt to varying workloads.

### Feedback with Variable Quantum (FBV)

Similar to FB, but each queue can have a different time quantum, allowing finer control over process scheduling.

### Aging

Aging is used to prevent starvation by gradually increasing the priority of waiting processes. Over time, even low-priority processes will get CPU time.

## Input Format

- **Line 1:** Mode of operation: `"trace"` or `"stats"`
- **Line 2:** Comma-separated list of scheduling algorithms and their parameters (e.g., `2-4` for RR with quantum 4, `8-1` for Aging with quantum 1). Algorithms are numbered as follows:
  1. FCFS
  2. RR
  3. SPN
  4. SRT
  5. HRRN
  6. FB-1 (Feedback with all queues having quantum 1)
  7. FB-2i (Feedback with quantum = 2^i)
  8. Aging
- **Line 3:** Integer specifying the simulation end time.
- **Line 4:** Number of processes.
- **Line 5 onward:** Each process on a new line. For algorithms 1–7, format is:
    - Process Name, Arrival Time, Service Time

  For Aging (algorithm 8), format is:
    - Process Name, Arrival Time, Priority

Processes should be listed in order of arrival. If two processes arrive at the same time, the one with lower priority is listed first.

> For detailed examples, see the [testcases](https://github.com/nilimsankar123/CPU-Scheduling-Visualizer/tree/main/testcases) directory.

## Contributors

- [Nilim Sankar Bora](https://github.com/nilimsankar123)