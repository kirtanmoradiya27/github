Here’s a comprehensive list of **Git commands** along with their descriptions to help you with common tasks in Git:

### **Basic Git Commands**
- **`git init`**: Initialize a new Git repository in the current directory.
  ```bash
  git init
  ```
  
- **`git clone <repository-url>`**: Clone an existing Git repository to your local machine.
  ```bash
  git clone https://github.com/user/repository.git
  ```

- **`git status`**: Check the status of the repository to see changes to files, whether they’re staged or unstaged.
  ```bash
  git status
  ```

- **`git add <file>`**: Stage a file for commit.
  ```bash
  git add file.txt
  ```

- **`git add .`**: Stage all changes in the working directory (including new, modified, and deleted files).
  ```bash
  git add .
  ```

- **`git commit -m "message"`**: Commit staged changes with a message.
  ```bash
  git commit -m "Initial commit"
  ```

- **`git commit --amend`**: Amend the last commit. This allows you to change the last commit message or add new changes.
  ```bash
  git commit --amend
  ```

- **`git log`**: Show the commit history of the repository.
  ```bash
  git log
  ```

- **`git log --oneline`**: Show the commit history with each commit on one line.
  ```bash
  git log --oneline
  ```

- **`git show <commit-hash>`**: Show details of a specific commit.
  ```bash
  git show abc1234
  ```

### **Branching and Merging**
- **`git branch`**: List all branches in the repository.
  ```bash
  git branch
  ```

- **`git branch <branch-name>`**: Create a new branch.
  ```bash
  git branch new-feature
  ```

- **`git checkout <branch-name>`**: Switch to a different branch.
  ```bash
  git checkout new-feature
  ```

- **`git checkout -b <branch-name>`**: Create and switch to a new branch in one command.
  ```bash
  git checkout -b new-feature
  ```

- **`git merge <branch-name>`**: Merge the changes from a specified branch into the current branch.
  ```bash
  git merge new-feature
  ```

- **`git branch -d <branch-name>`**: Delete a branch after it’s merged.
  ```bash
  git branch -d new-feature
  ```

- **`git branch -D <branch-name>`**: Force delete a branch (even if not merged).
  ```bash
  git branch -D new-feature
  ```

### **Remote Repositories**
- **`git remote -v`**: Show the list of remote repositories.
  ```bash
  git remote -v
  ```

- **`git remote add <name> <url>`**: Add a new remote repository.
  ```bash
  git remote add origin https://github.com/user/repository.git
  ```

- **`git push <remote> <branch>`**: Push changes to a remote repository.
  ```bash
  git push origin main
  ```

- **`git push -u <remote> <branch>`**: Push and set the upstream tracking branch.
  ```bash
  git push -u origin new-feature
  ```

- **`git pull <remote> <branch>`**: Pull changes from a remote repository into your current branch.
  ```bash
  git pull origin main
  ```

- **`git fetch`**: Fetch changes from the remote without merging them into your local branch.
  ```bash
  git fetch
  ```

- **`git fetch <remote>`**: Fetch from a specific remote repository.
  ```bash
  git fetch origin
  ```

### **Undoing Changes**
- **`git restore <file>`**: Discard changes to a file (restores to the last commit).
  ```bash
  git restore file.txt
  ```

- **`git restore --staged <file>`**: Unstage a file that has been added to the staging area.
  ```bash
  git restore --staged file.txt
  ```

- **`git reset <commit>`**: Reset the current branch to a specific commit.
  ```bash
  git reset abc1234
  ```

- **`git reset --hard <commit>`**: Reset the current branch to a commit and discard changes in the working directory.
  ```bash
  git reset --hard abc1234
  ```

- **`git reset --soft <commit>`**: Reset to a specific commit but keep the changes staged.
  ```bash
  git reset --soft abc1234
  ```

- **`git revert <commit>`**: Create a new commit that undoes the changes of a previous commit.
  ```bash
  git revert abc1234
  ```

### **Stashing Changes**
- **`git stash`**: Temporarily store changes that are not yet committed.
  ```bash
  git stash
  ```

- **`git stash pop`**: Apply the latest stashed changes and remove them from the stash.
  ```bash
  git stash pop
  ```

- **`git stash apply`**: Apply stashed changes without removing them from the stash.
  ```bash
  git stash apply
  ```

- **`git stash list`**: List all stashed changes.
  ```bash
  git stash list
  ```

### **Configuration and Info**
- **`git config --global user.name "Your Name"`**: Set the global Git username.
  ```bash
  git config --global user.name "Your Name"
  ```

- **`git config --global user.email "youremail@example.com"`**: Set the global Git email.
  ```bash
  git config --global user.email "youremail@example.com"
  ```

- **`git config --list`**: List all Git configuration settings.
  ```bash
  git config --list
  ```

### **Tagging**
- **`git tag`**: List all tags in the repository.
  ```bash
  git tag
  ```

- **`git tag <tag-name>`**: Create a tag at the current commit.
  ```bash
  git tag v1.0
  ```

- **`git tag -a <tag-name> -m "message"`**: Create an annotated tag with a message.
  ```bash
  git tag -a v1.0 -m "First release"
  ```

- **`git push origin <tag-name>`**: Push a specific tag to a remote repository.
  ```bash
  git push origin v1.0
  ```

- **`git push --tags`**: Push all tags to a remote repository.
  ```bash
  git push --tags
  ```

### **Miscellaneous**
- **`git diff`**: Show differences between the working directory and the index (staging area).
  ```bash
  git diff
  ```

- **`git show`**: Show information about a commit (e.g., commit message, changes).
  ```bash
  git show abc1234
  ```

- **`git bisect`**: Use binary search to find the commit that introduced a bug.
  ```bash
  git bisect start
  ```

- **`git blame <file>`**: Show who last modified each line of a file.
  ```bash
  git blame file.txt
  ```

- **`git gc`**: Perform garbage collection to clean up unnecessary files and optimize the repository.
  ```bash
  git gc
  ```

- **`git reflog`**: Show the history of the HEAD reference.
  ```bash
  git reflog
  ```

### **Common Aliases**
- **`git co`**: Alias for `git checkout` (commonly configured).
  ```bash
  git co <branch-name>
  ```

- **`git ci`**: Alias for `git commit` (commonly configured).
  ```bash
  git ci -m "message"
  ```

- **`git st`**: Alias for `git status` (commonly configured).
  ```bash
  git st
  ```

---

Here are some **advanced Git features** that allow you to work more efficiently and with greater flexibility, especially when dealing with complex workflows or large projects.

### 1. **Git Bisect**: Binary Search for Debugging
`git bisect` helps you identify the commit that introduced a bug using binary search. It’s useful for narrowing down the problematic commit between two known points (e.g., when a bug was introduced).

- **Start bisecting**:
  ```bash
  git bisect start
  ```

- **Mark the good and bad commits**:
  ```bash
  git bisect bad   # Commit with the bug
  git bisect good <commit-hash>  # Last known good commit
  ```

- **Repeat the process**: Git will automatically checkout a commit in between and you can test it. After testing:
  ```bash
  git bisect good  # If the bug is not in this commit
  git bisect bad   # If the bug is still present
  ```

- **End the bisect session**:
  ```bash
  git bisect reset
  ```

### 2. **Git Rebase**: Rewriting History
`git rebase` allows you to rewrite commit history. This is especially useful for linearizing commit history before merging or for cleaning up commit logs.

- **Basic rebase**:
  ```bash
  git checkout feature-branch
  git rebase main
  ```
  This applies all commits from the `feature-branch` on top of the `main` branch.

- **Interactive rebase**: Use this to modify commit history, such as squashing commits, reordering, or editing commit messages.
  ```bash
  git rebase -i <commit-hash>
  ```

- **Abort rebase**: If something goes wrong during the rebase, you can undo it:
  ```bash
  git rebase --abort
  ```

### 3. **Git Cherry-pick**: Apply Specific Commits
`git cherry-pick` allows you to apply a specific commit from one branch to another without merging the entire branch.

- **Cherry-pick a commit**:
  ```bash
  git checkout target-branch
  git cherry-pick <commit-hash>
  ```

- **Multiple commits**: You can also cherry-pick a range of commits:
  ```bash
  git cherry-pick <commit-hash1>^..<commit-hash2>
  ```

### 4. **Git Submodules**: Working with Nested Repositories
A submodule is a repository inside another repository. Submodules are useful for managing dependencies in projects.

- **Add a submodule**:
  ```bash
  git submodule add <repository-url> <path-to-directory>
  ```

- **Initialize submodules**:
  ```bash
  git submodule init
  ```

- **Update submodules**:
  ```bash
  git submodule update
  ```

### 5. **Git Stash**: Temporarily Storing Changes
Git’s stash command lets you temporarily save changes that you’re not ready to commit yet, without committing them to the repository.

- **Stash changes**:
  ```bash
  git stash
  ```

- **List stashes**:
  ```bash
  git stash list
  ```

- **Apply the latest stash**:
  ```bash
  git stash apply
  ```

- **Apply and remove the latest stash**:
  ```bash
  git stash pop
  ```

- **Drop a specific stash**:
  ```bash
  git stash drop stash@{0}
  ```

### 6. **Git Reflog**: Recover Lost Commits
`git reflog` tracks the history of HEAD and branch references, so even if a commit is "lost" (for example, after a `git reset --hard`), you can recover it.

- **View reflog history**:
  ```bash
  git reflog
  ```

- **Reset to a previous state**:
  ```bash
  git reset --hard <reflog-commit-hash>
  ```

### 7. **Git Hooks**: Automating Git Actions
Git hooks are scripts that run automatically on specific Git actions like committing, merging, or pushing. This allows you to enforce rules, automate workflows, or integrate with other tools.

- **Example hooks**:
  - `pre-commit`: Runs before a commit is created. Often used for linting or tests.
  - `post-commit`: Runs after a commit is created. Useful for notifications or logging.
  - `pre-push`: Runs before pushing to a remote. Ideal for pre-push tests.

Hooks are located in the `.git/hooks/` directory.

### 8. **Git Filter-Branch**: Rewriting Commit History (Advanced)
`git filter-branch` allows you to rewrite a large portion of your history, such as removing sensitive information or changing commit messages across many commits.

- **Remove a file from all commits**:
  ```bash
  git filter-branch --tree-filter 'rm -f <file-path>' --prune-empty --tag-name-filter cat -- --all
  ```

- **Rewrite author information**:
  ```bash
  git filter-branch --env-filter '
  if [ "$GIT_AUTHOR_NAME" = "Old Name" ]; then
    GIT_AUTHOR_NAME="New Name";
    GIT_AUTHOR_EMAIL="new-email@example.com";
  fi' HEAD
  ```

Note: `git filter-branch` is powerful but can be dangerous if misused. Make sure to back up your repository before using it.

### 9. **Git Worktree**: Managing Multiple Worktrees
Git Worktree allows you to have multiple working directories associated with a single repository. This is useful if you want to work on different branches at the same time.

- **Add a new worktree**:
  ```bash
  git worktree add <path-to-new-directory> <branch-name>
  ```

- **Remove a worktree**:
  ```bash
  git worktree remove <path-to-directory>
  ```

### 10. **Git Sparse-Checkout**: Checkout Part of the Repository
Git’s sparse-checkout allows you to checkout only part of a large repository instead of the whole repository.

- **Enable sparse-checkout**:
  ```bash
  git sparse-checkout init
  ```

- **Set the directories you want**:
  ```bash
  git sparse-checkout set <directory-path>
  ```

### 11. **Git Patches**: Export and Apply Patches
A patch in Git is a file that contains the difference between two versions of a repository, which you can apply to another repository.

- **Create a patch**:
  ```bash
  git format-patch -1 <commit-hash>
  ```

- **Apply a patch**:
  ```bash
  git apply <patch-file>
  ```

### 12. **Git Blame**: Tracking Line Changes
`git blame` allows you to see who last modified each line of a file.

- **Blame a file**:
  ```bash
  git blame <file-path>
  ```

### 13. **Git Merge Strategies**
Git provides different merge strategies, which can be specified while performing a merge:

- **Recursive (default)**: Merges two branches by creating a new merge commit.
- **Ours**: Keeps only the changes from the current branch and ignores changes from the other branch.
- **Theirs**: Keeps only the changes from the branch being merged into the current branch.

- **Example**:
  ```bash
  git merge --strategy=ours branch-name
  ```

### 14. **Git Submodules**: Nested Repositories (Advanced)
A **submodule** is a repository embedded inside another repository at a specific path. This is useful for including libraries or dependencies in your project.

- **Add a submodule**:
  ```bash
  git submodule add <repository-url> <directory-path>
  ```

- **Update submodules**:
  ```bash
  git submodule update --recursive
  ```

### Conclusion
These advanced Git features give you more control over how you manage your repository and streamline complex workflows. Whether you're debugging, managing history, or working with nested projects, these tools will help you handle more sophisticated use cases.
