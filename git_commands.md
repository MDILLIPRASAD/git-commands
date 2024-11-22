Here’s the refined and properly formatted version in Markdown for GitHub:

```markdown
# Git Commands

### Table of Contents
1. [Basic Git Commands](#basic-git-commands)
2. [Git Merge vs Git Rebase vs Git Pull vs Git Fetch](#git-merge-vs-git-rebase-vs-git-pull-vs-git-fetch)
3. [Recover Deleted Branches](#recover-deleted-branches)
4. [Git Stash Commands](#git-stash-commands)
5. [Branching Best Practices](#branching-best-practices)
6. [Real-World Git Workflow](#real-world-git-workflow)
7. [Advanced Commands](#advanced-commands)

---

## Basic Git Commands

| **Command**                                 | **Description**                                                                                       |
|---------------------------------------------|-------------------------------------------------------------------------------------------------------|
| `git pull origin dev/main`                  | Fetch and merge the latest code from the remote to your local environment.                           |
| `git checkout -b <branchname>`              | Create and switch to a new branch for working on a task.                                             |
| `git add <filename>`                        | Add specific files to the staging area.                                                              |
| `git commit -m '<message>'`                 | Commit changes locally with a descriptive message.                                                   |
| `git push origin <branchname>`              | Push the local branch to the remote repository.                                                      |
| `git branch -d <branchname>`                | Delete a merged branch locally.                                                                      |
| `git branch -D <branchname>`                | Forcefully delete a branch locally, even if it has unmerged changes.                                 |
| `git fetch origin main`                     | Fetch details from the remote repository without merging the code.                                   |
| `git merge <branchname>`                    | Merge changes from another branch into the current branch.                                           |
| `git stash`                                 | Save your local changes temporarily to a stash.                                                     |
| `git stash apply`                           | Apply the most recent stash to your working directory, leaving it in the stash list.                |
| `git status`                                | Show the status of the project directory.                                                            |
| `git branch`                                | Show the list of branches.                                                                           |
| `git branch -a`                             | List both local and remote branches.                                                                 |
| `git branch -r`                             | List remote branches only.                                                                           |
| `git log`                                   | Display the commit history.                                                                          |
| `git cherry-pick <commit-hash>`             | Apply specific commits from one branch to another.                                                   |
| `git reflog`                                | Show a log of recent Git actions, useful for recovering deleted branches.                            |

---

## Git Merge vs Git Rebase vs Git Pull vs Git Fetch

| **Command**  | **Downloads Changes?** | **Integrates Changes?** | **Modifies History?** | **Creates Merge Commit?** | **Use Case**                                              |
|--------------|-------------------------|--------------------------|------------------------|---------------------------|----------------------------------------------------------|
| `git fetch`  | Yes                     | No                       | No                     | No                        | Inspect remote changes before integration.               |
| `git merge`  | No                      | Yes                      | No                     | Yes                       | Safely combine branches while preserving history.        |
| `git rebase` | Yes (if fetched)        | Yes                      | Yes                    | No                        | Create a clean, linear history for private branches.     |
| `git pull`   | Yes                     | Yes                      | No                     | Yes (if necessary)        | Quickly synchronize and merge with the remote branch.    |

---

## Recover Deleted Branches

If you have deleted a branch and want to recover it:

1. Use `git reflog` to view recent Git actions:
    ```bash
    git reflog
    ```
2. Find the commit hash for the deleted branch.
3. Recreate the branch using the commit hash:
    ```bash
    git branch <branch-name> <commit-hash>
    ```

### Example:
```bash
git branch recovered-branch abc1234
```

---

## Git Stash Commands

| **Command**                              | **Description**                                                                                   |
|------------------------------------------|---------------------------------------------------------------------------------------------------|
| `git stash save "message"`               | Save your local changes to the stash with a descriptive message.                                 |
| `git stash list`                         | List all stashed changes.                                                                        |
| `git stash show`                         | Show the changes in the most recent stash.                                                      |
| `git stash apply`                        | Apply the most recent stash to your working directory, leaving it in the stash list.            |
| `git stash pop`                          | Apply the most recent stash to your working directory and remove it from the stash list.        |
| `git stash branch <branch_name>`         | Create a new branch from a specific stash.                                                      |

---

## Branching Best Practices

1. **Use Feature Branches**: Always create a new branch for each task or feature.
2. **Avoid Pushing to `main/dev`**: Use pull requests for merging.
3. **Name Branches Clearly**: Use concise, descriptive names like `feature-login-page` or `fix-auth-bug`.
4. **Review Before Merging**: Ensure code is reviewed and tested.

---

## Real-World Git Workflow

1. Pull the latest code:
    ```bash
    git pull origin dev/main
    ```
2. Create a new branch:
    ```bash
    git checkout -b <branchname>
    ```
3. Make changes and stage them:
    ```bash
    git add <filename>
    ```
4. Commit your changes:
    ```bash
    git commit -m "Add feature XYZ"
    ```
5. Push your branch:
    ```bash
    git push origin <branchname>
    ```
6. Merge your branch (after review):
    ```bash
    git checkout main
    git merge <branchname>
    ```

---

## Advanced Commands

| **Command**                              | **Description**                                                                                   |
|------------------------------------------|---------------------------------------------------------------------------------------------------|
| `git clone <repo-url>`                   | Clone a remote repository to create a local copy.                                                |
| `git reset --hard <commit_hash>`         | Reset the repository to a specific commit, discarding changes.                                   |
| `git cherry-pick <commit_hash>`          | Apply a specific commit from one branch to another.                                              |
| `git remote -v`                          | List remote repositories.                                                                        |
| `git diff`                               | Show differences in files or commits.                                                            |
| `git stash clear`                        | Remove all stashed changes.                                                                      |
