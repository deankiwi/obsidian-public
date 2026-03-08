---
description: description: Wrap up a task, verify against main, capture UI, and open a PR
---

When the user runs this workflow (e.g., `/finish-task`), follow these steps sequentially within the active worktree directory to safely finalize their work.

1. **Commit Lingering Work:** Check `git status`. If there are uncommitted changes, stage them and write a concise, descriptive commit message summarizing the final updates.
2. **Sync with Main:** Fetch the latest changes from the remote and merge or rebase the remote `main` branch into the current working branch (e.g., `git fetch origin`, followed by `git rebase origin/main` or `git merge origin/main`). Resolve any automated conflicts if possible, or pause and ask the user for help.
3. **Verify Functionality:** Run the project's standard build and test commands to ensure the recent sync with `main` did not break anything. 
4. **Capture UI Screenshots:** If the task involved UI changes, boot up the local development server. Use **Antigravity's screenshot tool** to capture visual proof of the changes, focusing on the specific components or pages that were modified.
5. **Push to Remote:** Push the branch to the remote repository (e.g., `git push -u origin <branch-name>`).
6. **Create the Pull Request:** Use the available CLI tools (e.g., `gh pr create`) to open a Pull Request. Structure the PR description with the following:
    * **Summary:** A high-level overview of what the branch accomplishes.
    * **Examples of Changes:** Bullet points highlighting the specific logic, files, or components modified.
    * **UI Changes:** Embed or link the screenshots captured by Antigravity in Step 4 directly into this section.
7. **Notify the User:** Provide the user with the direct link to the newly created Pull Request so they can do a final review.