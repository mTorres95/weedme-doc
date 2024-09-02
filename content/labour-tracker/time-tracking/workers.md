+++
title= "Workers"
+++

This section details the system's tracking of worker availability and activity.

## Facility Status

- **Onsite:** Worker has clocked in and is physically present in the facility.
- **Offsite:** Worker has clocked out and is not currently in the facility.

## Labor Status

- **Idle:** Worker is onsite and available for task assignment.
- **Labour:** Worker is actively working on an assigned task.
- **Break:** Worker is currently taking a break from an active task.

## Worker Logs _(Stopwatch)_

The system utilizes a stopwatch to track labour time:

- **Start:** When a worker clocks in, the stopwatch starts, and their Facility
Status changes to "Onsite" and Labor Status to "Idle"
- **Stop:** The stopwatch stops when the worker clocks out.
