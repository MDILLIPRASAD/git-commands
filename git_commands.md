**Git Commands:**

- `git pull origin dev/main`               --> Fetch and merge the latest code from the remote to your local environment.
- `git checkout -b <branchname>`           --> Create and switch to a new branch for working on a task.
- `git add <filename>`                     --> Add specific files to the staging area.
- `git commit -m '<message>'`              --> Commit changes locally with a descriptive message.
- `git push origin <branchname>`           --> Push the local branch to the remote repository.
- `git push origin main/dev`               --> Push changes to the main branch when they are production-ready.
- `git branch -d <branchname>`             --> Delete a merged branch locally.
- `git branch -D <branchname>`             --> Forcefully delete a branch locally, even if it has unmerged changes.
- `git fetch origin main`                  --> Fetch details from the remote repository without merging the code.
- `git merge <branchname>`                 --> Merge changes from another branch into the current branch.
- `git stash`                              --> Save your local changes temporarily to a stash.
- `git stash apply`                        --> Apply the most recent stash to your working directory, leaving it in the stash list.
- `git stash pop`                          --> Apply the most recent stash to your working directory and remove it from the stash list.
- `git status`                             --> Show the status of the project directory.
- `git branch`                             --> Show the list of branches.
- `git branch -a`                          --> List both local and remote branches.
- `git branch -r`                          --> List remote branches only.
- `git log`                                --> Display the commit history.
- `git cherry-pick <commit-hash>`          --> Apply specific commits from one branch to another.
- `git reflog`                             --> Show a log of recent Git actions, useful for recovering deleted branches.
- `git reset --hard <commit_hash>`         --> Reset the repository to a specific commit, discarding changes.
- `git remote -v`                          --> List remote repositories.
- `git diff`                               --> Show differences in files or commits.
- `git stash clear`                        --> Remove all stashed changes.

## Git Stash Commands:

- `git stash save "message"` --> This command saves your local changes to the stash with a descriptive message.
- `git stash list`           --> Lists all stashed changes.
- `git stash show`           --> Shows the changes in the most recent stash.
- `git stash show -p`        --> Shows the changes in the most recent stash in patch format.
- `git stash apply`          --> Applies the most recent stash to your working directory, leaving it in the stash list.
- `git stash apply stash@{n}` --> Applies a specific stash from the stash list.
- `git stash pop`             --> Applies the most recent stash to your working directory and removes it from the stash list.
- `git stash drop`            --> Deletes the most recent stash from the stash list.
- `git stash clear`           --> Removes all stashed changes from the stash list.
- `git stash branch <branch_name>` --> Creates a new branch from a specific stash.

**Recover Deleted Branches:**

If you have deleted a branch and want to recover it:
- `git reflog`--> Use `git reflog` to view recent Git actions.
Find the commit hash for the deleted branch.
- `git branch <branch-name> <commit-hash>` --> Recreate the branch using the commit hash
Example:
```bash
git branch recovered-branch abc1234
```

**Git Merge vs Git Rebase vs Git Pull vs Git Fetch:**

- `git fetch`        --> Downloads changes but does not integrate them. No modification to history. No merge commit.
- `git merge`        --> Does not download changes but integrates them. Does not modify history but creates a merge commit.
- `git rebase`       --> Downloads changes (if fetched). Integrates changes, modifies history, and does not create a merge commit.
- `git pull`         --> Downloads and integrates changes. No modification to history but may create a merge commit.

**Git Branching Best Practices:**

1. **Use Feature Branches**: Always create a new branch for each task or feature.
2. **Avoid Pushing to `main/dev`**: Use pull requests for merging.
3. **Name Branches Clearly**: Use concise, descriptive names like `feature-login-page` or `fix-auth-bug`.
4. **Review Before Merging**: Ensure code is reviewed and tested.
