## Workflow 1: synchronize dev and main

When I ask you to synchronize `dev` and `main`, follow this workflow:

### Goal

Bring changes from `main` into `dev` first, then merge the updated `dev` back into `main`.

### Required steps

1. Fetch the latest remote refs:

   git fetch origin

2. Verify the working tree is clean:

   git status --short

3. If there are uncommitted changes, stop and explain them.

4. Switch to `dev`:

   git switch dev

5. Update `dev` with the latest `main` changes:

   git merge --no-ff origin/main

6. If there are merge conflicts, stop and ask me how to proceed.

7. Run the project checks or tests if available.

8. Switch to `main`:

   git switch main

9. Update `main` from remote:

   git pull --ff-only origin main

10. Merge the synchronized `dev` branch into `main`:

    git merge --no-ff dev

11. If there are merge conflicts, stop and ask me how to proceed.

12. Run the project checks or tests again if needed.

13. Push `main` to origin:

    git push origin main

14. Report whether the synchronization completed cleanly or required conflict resolution.

### Safety rules

- Do not force push.
- Do not rewrite history.
- Do not delete branches.
- Do not resolve conflicts automatically unless I explicitly ask.