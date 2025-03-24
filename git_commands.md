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

- `git stash save "message"`                --> This command saves your local changes to the stash with a descriptive message.
- `git stash list`                          --> Lists all stashed changes.
- `git stash show`                          --> Shows the changes in the most recent stash.
- `git stash show -p`                       --> Shows the changes in the most recent stash in patch format.
- `git stash apply`                         --> Applies the most recent stash to your working directory, leaving it in the stash list.
- `git stash apply stash@{n}`               --> Applies a specific stash from the stash list.
- `git stash pop`                           --> Applies the most recent stash to your working directory and removes it from the stash list.
- `git stash drop`                          --> Deletes the most recent stash from the stash list.
- `git stash clear`                         --> Removes all stashed changes from the stash list.
- `git stash branch <branch_name>`          --> Creates a new branch from a specific stash.

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
5. 


To reset your working directory and discard all changes (including untracked files), you can run the following commands:

1. **Reset to the latest commit**:

```bash
git reset --hard
```
This will reset your working directory and the index (staging area) to the most recent commit, discarding all changes that haven't been committed.

2. **Remove untracked files** (like `.next/`, `.vscode/`, `node_modules/`):

```bash
git clean -fd
```
This will remove all untracked files and directories from your working directory. Be careful with this command as it will permanently delete untracked files.

After that, your repository should be cleaned up and reset to the latest commit. 



# Main Porcelain Commands
- **add**: Add file contents to the index
- **am**: Apply a series of patches from a mailbox
- **archive**: Create an archive of files from a named tree
- **backfill**: Download missing objects in a partial clone
- **bisect**: Use binary search to find the commit that introduced a bug
- **branch**: List, create, or delete branches
- **bundle**: Move objects and refs by archive
- **checkout**: Switch branches or restore working tree files
- **cherry-pick**: Apply the changes introduced by some existing commits
- **citool**: Graphical alternative to git-commit
- **clean**: Remove untracked files from the working tree
- **clone**: Clone a repository into a new directory
- **commit**: Record changes to the repository
- **describe**: Give an object a human-readable name based on an available ref
- **diff**: Show changes between commits, commit and working tree, etc.
- **fetch**: Download objects and refs from another repository
- **format-patch**: Prepare patches for email submission
- **gc**: Cleanup unnecessary files and optimize the local repository
- **gitk**: The Git repository browser
- **grep**: Print lines matching a pattern
- **gui**: A portable graphical interface to Git
- **init**: Create an empty Git repository or reinitialize an existing one
- **log**: Show commit logs
- **maintenance**: Run tasks to optimize Git repository data
- **merge**: Join two or more development histories together
- **mv**: Move or rename a file, a directory, or a symlink
- **notes**: Add or inspect object notes
- **pull**: Fetch from and integrate with another repository or a local branch
- **push**: Update remote refs along with associated objects
- **range-diff**: Compare two commit ranges (e.g. two versions of a branch)
- **rebase**: Reapply commits on top of another base tip
- **reset**: Reset current HEAD to the specified state
- **restore**: Restore working tree files
- **revert**: Revert some existing commits
- **rm**: Remove files from the working tree and from the index
- **scalar**: A tool for managing large Git repositories
- **shortlog**: Summarize `git log` output
- **show**: Show various types of objects
- **sparse-checkout**: Reduce your working tree to a subset of tracked files
- **stash**: Stash the changes in a dirty working directory away
- **status**: Show the working tree status
- **submodule**: Initialize, update, or inspect submodules
- **switch**: Switch branches
- **tag**: Create, list, delete, or verify a tag object signed with GPG
- **worktree**: Manage multiple working trees

# Ancillary Commands / Manipulators
- **config**: Get and set repository or global options
- **fast-export**: Git data exporter
- **fast-import**: Backend for fast Git data importers
- **filter-branch**: Rewrite branches
- **mergetool**: Run merge conflict resolution tools
- **pack-refs**: Pack heads and tags for efficient repository access
- **prune**: Prune all unreachable objects from the object database
- **reflog**: Manage reflog information
- **remote**: Manage set of tracked repositories
- **repack**: Pack unpacked objects in a repository
- **replace**: Create, list, delete refs to replace objects

# Ancillary Commands / Interrogators
- **annotate**: Annotate file lines with commit information
- **blame**: Show what revision and author last modified each line of a file
- **bugreport**: Collect information for user to file a bug report
- **count-objects**: Count unpacked objects and their disk consumption
- **diagnose**: Generate a zip archive of diagnostic information
- **difftool**: Show changes using common diff tools
- **fsck**: Verify the connectivity and validity of the objects in the database
- **gitweb**: Git web interface
- **help**: Display help information about Git
- **merge-tree**: Perform merge without touching index or working tree
- **rerere**: Reuse recorded resolution of conflicted merges
- **show-branch**: Show branches and their commits
- **verify-commit**: Check the GPG signature of commits
- **verify-tag**: Check the GPG signature of tags
- **version**: Display version information about Git
- **whatchanged**: Show logs with differences each commit introduces

# Interacting with Others
- **archimport**: Import a GNU Arch repository into Git
- **cvsexportcommit**: Export a single commit to a CVS checkout
- **cvsimport**: Salvage data out of another SCM
- **cvsserver**: A CVS server emulator for Git
- **imap-send**: Send a collection of patches from stdin to an IMAP folder
- **p4**: Import from and submit to Perforce repositories
- **request-pull**: Generate a summary of pending changes
- **send-email**: Send a collection of patches as emails
- **svn**: Bidirectional operation between a Subversion repository and Git

# Low-level Commands / Manipulators
- **apply**: Apply a patch to files and/or to the index
- **checkout-index**: Copy files from the index to the working tree
- **commit-tree**: Create a new commit object
- **hash-object**: Compute object ID and optionally create an object from a file
- **merge-file**: Run a three-way file merge
- **pack-objects**: Create a packed archive of objects
- **read-tree**: Reads tree information into the index
- **symbolic-ref**: Read, modify, and delete symbolic refs
- **update-index**: Register file contents in the working tree to the index

# Low-level Commands / Interrogators
- **cat-file**: Provide contents or details of repository objects
- **cherry**: Find commits yet to be applied to upstream
- **diff-files**: Compare files in the working tree and the index
- **diff-index**: Compare a tree to the working tree or index
- **ls-files**: Show information about files in the index and the working tree
- **ls-remote**: List references in a remote repository
- **ls-tree**: List the contents of a tree object
- **rev-list**: Lists commit objects in reverse chronological order
- **rev-parse**: Pick out and massage parameters
- **show-index**: Show packed archive index
- **show-ref**: List references in a local repository

# Low-level Commands / Syncing Repositories
- **daemon**: A simple server for Git repositories
- **fetch-pack**: Receive missing objects from another repository
- **send-pack**: Push objects over Git protocol to another repository
- **update-server-info**: Update auxiliary info file to help dumb servers

# User-facing Repository, Command, and File Interfaces
- **attributes**: Defining attributes per path
- **cli**: Git command-line interface and conventions
- **hooks**: Hooks used by Git
- **ignore**: Specifies intentionally untracked files to ignore
- **modules**: Defining submodule properties
- **revisions**: Specifying revisions and ranges for Git

# Developer-facing File Formats, Protocols, and Other Interfaces
- **format-bundle**: The bundle file format
- **format-commit-graph**: Git commit-graph format
- **protocol-pack**: How packs are transferred over the wire
- **protocol-v2**: Git Wire Protocol, Version 2

# External Commands
- **askpass**
- **askyesno**
- **credential-helper-selector**
- **credential-manager**
- **flow**
- **lfs**
- **update-git-for-windows**

