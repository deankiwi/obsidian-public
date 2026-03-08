---
description: Create a new git worktree for a task
---

When the user runs this workflow (e.g., `/start-task [task description]`), follow these steps automatically to completely isolate your changes from the main branch.

1. Analyze the `[task description]` provided by the user and generate a short, descriptive branch name in the format `feature-xxx` or `fix-xxx` (e.g., `feature-add-login`). Also, determine the current `<project-name>` based on the name of the current repository directory.
2. Create a new git worktree in a sibling directory (one level up) to avoid dirtying the current checkout. Make sure to create and checkout a new branch in this step.
// turbo
3. Run `git worktree add ../<project-name>_<branch-name> -b <branch-name>` from the original repository directory.
4. **CRITICAL:** From this point forward, map ALL file edits (`TargetFile` paths) and ALL terminal commands (`Cwd` paths) to target the newly created sibling worktree directory (e.g., `/Users/deanwelchmain/github/deankiwi/<project-name>_<branch-name>`). Do not make any edits or run commands in the original project directory to keep it clean.
5. Notify the user that the worktree was successfully created and you have switched context to it. Proceed to start working on the user's task in the new worktree.