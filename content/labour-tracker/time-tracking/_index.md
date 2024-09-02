+++
title = "Time Tracking"
weight = 100
+++

This document explains how time tracking works within the system, utilizing a
stopwatch analogy for easy understanding.

## Stopwatch Logs

Imagine a stopwatch starts for each worker and task record when a worker enters
the facility or a task begins. Every change in the worker's labour status creates
a new "lap" on the stopwatch.

- There is only one lap in progress per stopwatch
- The stopwatch starts when
  - A Task is started
  - A Worker clocks in
- The stopwatch stops
  - A Task is completed
  - A Worker clocks out
- The "laps" or labour statuses depends on the Task Management