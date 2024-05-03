+++
title= "Tasks"
+++

Track duration time and labour time for each task.

## Task Status

Track the progress of a task through its workflow:

- **Pending:** Supervisor created the task and is ready to assign workers.
- **Active:** Supervisor started the task, and workers are actively working.
- **Completed:** Supervisor completed the task, and fill the production result.

### Labour Status

Track the current state of active work on a task.

- **Labour:** Workers are currently working on the task.
- **Break:** Supervisor has temporarily paused the task for a break.

## Logs _(Stopwatch)_

- **Start:** The supervisor starts the stopwatch when initiating the task,
changing the Labor Status to "In Labor."
- **Stop:** Stop the stopwatch when the task is completed.
- **Breaks:** The task can have recorded break intervals when the supervisor
sets a break.