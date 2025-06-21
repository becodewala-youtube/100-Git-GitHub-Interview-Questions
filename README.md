# 100 Git-GitHub-Interview-Question



### ✅ **Basic Git Interview Questions and Answers**



### **1. What is Git?**

**Git** is a **distributed version control system (DVCS)** used to track changes in source code during software development. It allows multiple developers to work on a project simultaneously without interfering with each other's work.

#### Example:

You can use Git to track the history of your project files. If something breaks, you can go back to the last working version.



### **2. What is the difference between Git and GitHub?**

| Git                          | GitHub                                             |
| ---------------------------- | -------------------------------------------------- |
| A tool to track code changes | A hosting service for Git repositories             |
| Runs locally on your machine | Web-based interface                                |
| Doesn't require internet     | Requires internet                                  |
| Open-source version control  | Platform for collaboration, sharing, pull requests |

#### Example:

You use Git on your local machine to manage code versions. GitHub is where you push your code to share it with your team or store it in the cloud.



### **3. What are the advantages of using Git?**

* **Distributed**: Every developer has a full copy of the project history.
* **Efficient branching and merging**: Supports feature branching and collaborative workflows.
* **Performance**: Operations are very fast.
* **Security**: SHA-1 hash ensures code integrity.
* **Data Recovery**: Easily revert changes or recover deleted files.



### **4. Explain the Git workflow.**

**Git Workflow Steps:**

```
Working Directory → Staging Area → Local Repository → Remote Repository
```

1. **Modify files** in the working directory.
2. **Stage** the files using `git add`.
3. **Commit** the changes using `git commit`.
4. **Push** them to a remote server like GitHub using `git push`.

#### Example:

```bash
git add index.js
git commit -m "Added homepage functionality"
git push origin main
```



### **5. What is a repository in Git?**

A **repository** (or **repo**) is a directory or storage space where your project lives. It contains all files and folders along with the `.git` folder to track version history.

#### Example:

```bash
git init  # Initializes a new repository
```



### **6. What is a commit in Git?**

A **commit** is a snapshot of your staged changes. It records changes to files along with a message and a unique commit ID.

#### Example:

```bash
git commit -m "Added login form UI"
```



### **7. What is the difference between `git add`, `git commit`, and `git push`?**

| Command      | Purpose                                       |
| ------------ | --------------------------------------------- |
| `git add`    | Stages changes                                |
| `git commit` | Saves staged changes to local repo            |
| `git push`   | Uploads commits to remote repo (e.g., GitHub) |

#### Example:

```bash
git add app.js
git commit -m "Fixed navbar issue"
git push origin main
```


### **8. What is the purpose of `.gitignore`?**

The **`.gitignore`** file tells Git which files or folders to ignore. These are usually files like:

* `node_modules/`
* `.env`
* `*.log`

#### Example:

In `.gitignore`:

```
node_modules/
.env
```

These files will not be tracked or pushed to GitHub.



### **9. What is a branch in Git?**

A **branch** is a pointer to a commit. It allows you to develop features, fix bugs, or experiment **without affecting the main codebase**.

#### Example:

```bash
git branch feature/login
```

This creates a new branch named `feature/login`.



### **10. How do you create a new branch?**

```bash
git branch feature/signup
```

Or, create and switch to it in one command:

```bash
git checkout -b feature/signup
```



### **11. What is the command to switch branches?**

```bash
git checkout branch-name
```

Or in newer Git versions:

```bash
git switch branch-name
```

#### Example:

```bash
git switch main
```



### **12. How do you delete a branch in Git?**

To delete a **local** branch:

```bash
git branch -d branch-name
```

Force delete (unsafe):

```bash
git branch -D branch-name
```

To delete a **remote** branch:

```bash
git push origin --delete branch-name
```


### **13. What is the command to merge branches?**

```bash
git checkout main
git merge feature/login
```

This merges the `feature/login` branch into `main`.


### **14. What is the difference between `git merge` and `git rebase`?**

| Feature  | `git merge`                                 | `git rebase`             |
| -------- | ------------------------------------------- | ------------------------ |
| History  | Creates a new merge commit                  | Rewrites commit history  |
| Use case | Non-linear history (good for collaboration) | Linear history (cleaner) |
| Safe?    | Yes                                         | Needs caution            |

#### Example:

```bash
# Merge
git checkout main
git merge feature

# Rebase
git checkout feature
git rebase main
```



### **15. What is the HEAD in Git?**

**HEAD** is a pointer to the **latest commit** in the current branch. When you make new commits, HEAD moves forward.

#### Example:

```bash
git log
```

The first commit listed is what HEAD points to.



### **16. What is the difference between HEAD, working directory, and staging area?**

| Area                     | Description                      |
| ------------------------ | -------------------------------- |
| **Working Directory**    | Your actual files on disk        |
| **Staging Area (Index)** | Files marked for the next commit |
| **HEAD**                 | Latest commit snapshot           |

#### Diagram:

```
Working Directory → git add → Staging Area → git commit → HEAD
```



### **17. What is the command to initialize a Git repository?**

```bash
git init
```

This creates a `.git/` directory that tracks all version control info.



### **18. What is the difference between a local and remote repository?**

| Repository Type | Description                            |
| --------------- | -------------------------------------- |
| **Local**       | On your machine                        |
| **Remote**      | Hosted on services like GitHub, GitLab |

#### Example:

* Local: `git commit`
* Remote: `git push origin main`



### **19. How do you clone a GitHub repository?**

```bash
git clone https://github.com/username/repo-name.git
```

This downloads the repository and sets up the remote `origin`.



### **20. How do you check the status of a repository?**

```bash
git status
```

This shows:

* Modified files
* Staged/unstaged changes
* Branch info

#### Example:

```bash
On branch main
Changes not staged for commit:
    modified:   index.html
```



### ✅ **21. What is the difference between `git pull` and `git fetch`?**

* **`git fetch`**: Downloads commits, files, and refs from a remote repository into your local repo **but does not merge** them into your current branch.
* **`git pull`**: It is essentially `git fetch` **followed by** `git merge`. It downloads and then tries to **integrate** (merge) the fetched changes into the current branch.

**Example:**

```bash
git fetch origin
# Updates local tracking branches, but does not merge

git pull origin main
# Fetches and automatically merges the 'main' branch into your current branch
```

> 🔁 Use `fetch` when you want to preview changes before merging.


### ✅ **22. How do you resolve merge conflicts?**

A **merge conflict** happens when Git can't automatically merge changes.

**Steps to resolve:**

1. Run:

   ```bash
   git merge branch-name
   ```
2. Git will stop and show conflicting files. You'll see conflict markers like:

   ```plaintext
   <<<<<<< HEAD
   Your changes
   =======
   Incoming changes
   >>>>>>> branch-name
   ```
3. Manually edit the file to resolve the conflict.
4. After resolving:

   ```bash
   git add conflicted-file
   git commit
   ```



### ✅ **23. What is a fast-forward merge?**

A **fast-forward merge** happens when there is **no divergent history** and Git can simply move the branch pointer forward.

**Example:**

```bash
# main is behind feature
git checkout main
git merge feature
```

If `main` has not diverged from `feature`, Git just updates the pointer to match `feature`. No merge commit is created.



### ✅ **24. What is a pull request (PR)?**

A **pull request (PR)** is a way to **propose changes** in one branch (usually a feature or fork) to be **merged into another** (typically the main repository).

* Used for code review, discussion, and approvals.
* GitHub automatically shows diff and merge status.


### ✅ **25. How do you create a pull request on GitHub?**

1. Push your branch to GitHub:

   ```bash
   git push origin feature-branch
   ```
2. Go to the GitHub repository.
3. GitHub will prompt: “Compare & pull request.”
4. Add title, description, and create PR.
5. Team members can review, discuss, approve, and merge.

 

### ✅ **26. What is forking a repository?**

**Forking** is creating a **personal copy of someone else’s repository** under your GitHub account.

* Allows you to freely experiment without affecting the original.
* Common in open-source contributions.



### ✅ **27. What is the difference between a fork and a clone?**

| Feature  | Fork                                  | Clone                            |
| -------- | ------------------------------------- | -------------------------------- |
| Location | Creates a copy on your GitHub account | Copies to your **local machine** |
| Use Case | Contribution & collaboration          | Local development                |
| Command  | Done via GitHub UI                    | `git clone <repo-url>`           |



### ✅ **28. What is Git stash?**

**`git stash`** temporarily saves your uncommitted changes so you can work on something else without losing progress.

**Example:**

```bash
git stash
# Clean working directory, changes stored safely

git stash apply
# Applies the most recent stash

git stash drop
# Removes the stash from the list
```



### ✅ **29. How do you apply and drop stashes?**

```bash
git stash list
# Shows all stashes

git stash apply stash@{1}
# Applies a specific stash

git stash drop stash@{1}
# Deletes a specific stash

git stash clear
# Deletes all stashes
```



### ✅ **30. How do you view commit history?**

```bash
git log
# Full history with commit hashes, authors, messages

git log --oneline --graph --all
# Compact graphical view
```



### ✅ **31. How do you revert a commit?**

```bash
git revert <commit-hash>
```

* This creates a **new commit** that undoes the changes of the specified commit.

> ✅ Safe for public branches.



### ✅ **32. What is the difference between `git revert` and `git reset`?**

| Feature          | `git revert`                 | `git reset`                       |
| ---------------- | ---------------------------- | --------------------------------- |
| Action           | Creates a new commit to undo | Moves the HEAD and branch pointer |
| History          | Preserved                    | Can rewrite history               |
| Safe for shared? | Yes                          | No (if pushed already)            |



### ✅ **33. What is the difference between soft, mixed, and hard resets?**

```bash
git reset --soft HEAD~1
# Moves HEAD, keeps staging and working directory

git reset --mixed HEAD~1
# Moves HEAD, clears staging area, working directory stays

git reset --hard HEAD~1
# Discards everything (staging + working directory)
```



### ✅ **34. What is a tag in Git?**

Tags are used to **mark specific points** in history (commonly used for releases).

* Two types: **lightweight** and **annotated**



### ✅ **35. How do you create and delete a tag?**

**Create:**

```bash
git tag v1.0
# lightweight

git tag -a v1.0 -m "Version 1.0"
# annotated
```

**Push to remote:**

```bash
git push origin v1.0
```

**Delete:**

```bash
git tag -d v1.0
git push origin --delete tag v1.0
```



### ✅ **36. What is `git cherry-pick`?**

Used to **apply a specific commit** from one branch onto another.

**Example:**

```bash
git cherry-pick <commit-hash>
```

> Helpful if you want a fix from a feature branch but not the entire branch.



### ✅ **37. What is `git bisect`?**

Binary search to **find the commit that introduced a bug**.

**Steps:**

```bash
git bisect start
git bisect bad
git bisect good <commit-hash>
# Git will now checkout commits one by one. You test and run:
git bisect good
# or
git bisect bad
```

Eventually, Git will tell you the exact commit that caused the issue.



### ✅ **38. What is `git blame`?**

Shows **who changed what line** in a file.

**Example:**

```bash
git blame index.js
```

* Displays author, commit hash, and timestamp for each line.



### ✅ **39. How do you undo the last commit?**

If you want to undo but **keep changes**:

```bash
git reset --soft HEAD~1
```

If you want to undo and **remove changes**:

```bash
git reset --hard HEAD~1
```



### ✅ **40. What is `.gitconfig`?**

It’s Git’s configuration file. It stores **user preferences** like name, email, editor, aliases, and more.

**Global config:**

```bash
~/.gitconfig
```

**Example:**

```ini
[user]
  name = Vikash Kumar
  email = vikash@example.com

[alias]
  co = checkout
  st = status
```

> View with: `git config --global --edit`


