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




### ✅ **41. What is the Git Flow Branching Model?**

**Git Flow** is a branching model for managing features, releases, and hotfixes in large projects.

**Main branches:**

* `main`: always contains production-ready code.
* `develop`: integrates features and is used for testing before release.

**Supporting branches:**

* `feature/*`: for new features.
* `release/*`: for preparing a new release.
* `hotfix/*`: for urgent production fixes.

**Flow:**

1. Create a feature branch from `develop`.
2. Merge feature into `develop`.
3. Create a release branch from `develop`, test, and fix bugs.
4. Merge release into both `main` and `develop`.
5. Tag the release.
6. Create hotfix from `main` if needed, then merge back.

> Tools like `git-flow` CLI automate this process.



### ✅ **42. What is `git reflog` and why is it useful?**

**`git reflog`** records updates to the **HEAD** (every time it moves).

**Why useful?**

* You can **recover lost commits** even after a reset or rebase.

**Example:**

```bash
git reflog
# Shows history like:
# abc1234 HEAD@{0}: reset: moving to HEAD~1
```

You can then do:

```bash
git checkout abc1234
# or
git reset --hard abc1234
```


### ✅ **43. How do you squash commits?**

**Squashing** combines multiple commits into one.

**During rebase:**

```bash
git rebase -i HEAD~3
```

You’ll see:

```bash
pick a1b2c3 First commit
pick d4e5f6 Second commit
pick g7h8i9 Third commit
```

Change to:

```bash
pick a1b2c3 First commit
squash d4e5f6 Second commit
squash g7h8i9 Third commit
```

Then save and edit the commit message.

> Useful before PRs to keep history clean.

 

### ✅ **44. What is the difference between `origin/master` and `master`?**

| Term            | Meaning                            |
| --------------- | ---------------------------------- |
| `master`        | Local branch pointer               |
| `origin/master` | Remote-tracking branch of `master` |

> They may differ if you've made changes locally or the remote has updated.

**Example:**

```bash
git fetch
git diff master origin/master
# Shows difference between local and remote
```

 

### ✅ **45. What are hooks in Git?**

**Git hooks** are scripts triggered by Git actions like commit, push, or merge.

* Located in `.git/hooks/`
* Examples:

  * `pre-commit`: run linters/tests before committing
  * `post-commit`: send notifications
  * `pre-push`: run CI checks

**Example:**
Create `.git/hooks/pre-commit`:

```bash
#!/bin/sh
npm run lint
```

Make it executable:

```bash
chmod +x .git/hooks/pre-commit
```



### ✅ **46. How does Git handle binary files?**

Git **does not efficiently store binary files** because:

* It can’t diff or merge them well.
* They bloat the repo history.

> Use **Git LFS (Large File Storage)** for binary assets like images, videos, or models.



### ✅ **47. How do you rename a file in Git?**

Use:

```bash
git mv oldname.js newname.js
git commit -m "Renamed file"
```

Alternatively:

```bash
mv oldname.js newname.js
git add newname.js
git rm oldname.js
git commit -m "Renamed manually"
```



### ✅ **48. How do you ignore tracked files?**

If a file is already tracked and you add it to `.gitignore`, it will **not be ignored** unless you untrack it:

```bash
git rm --cached filename
git commit -m "Stop tracking file"
```

Then add it to `.gitignore`.

 

### ✅ **49. What is a submodule in Git?**

**Submodules** let you keep a Git repository **as a subdirectory** of another Git repo.

Used when:

* You want to include another repo (e.g., a library) without copying its files.

**Commands:**

```bash
git submodule add https://github.com/user/repo.git subdir-name
git submodule update --init --recursive
```



### ✅ **50. What is the difference between `git clean` and `git reset --hard`?**

| Command            | Purpose                                 |
| ------------------ | --------------------------------------- |
| `git clean -fd`    | Deletes **untracked files/directories** |
| `git reset --hard` | Resets **tracked files** to last commit |

Use both together to fully clean your working directory:

```bash
git reset --hard
git clean -fd
```



### ✅ **51. How do you permanently delete a file from a Git repository?**

To delete a file **from history** (e.g., sensitive data):

1. Use `filter-repo` (recommended) or `filter-branch`:

```bash
git filter-repo --path secret.txt --invert-paths
```

2. Force push:

```bash
git push origin --force --all
```

3. Invalidate caches (on GitHub or GitLab if needed).



### ✅ **52. What is the difference between `.gitignore` and `.gitkeep`?**

| File         | Purpose                                           |
| ------------ | ------------------------------------------------- |
| `.gitignore` | Tells Git to **ignore files/folders**             |
| `.gitkeep`   | Not an official file—used to **track empty dirs** |

> Git doesn’t track empty folders, so `.gitkeep` is a workaround.



### ✅ **53. How do you push code to multiple remotes?**

Add multiple remotes:

```bash
git remote add origin https://github.com/user/repo.git
git remote add backup https://gitlab.com/user/repo.git
```

Push to both:

```bash
git push origin main
git push backup main
```

Or:

```bash
git remote set-url --add --push origin https://github.com/user/repo.git
git remote set-url --add --push origin https://gitlab.com/user/repo.git

git push origin
```



### ✅ **54. How do you undo a merge?**

#### Case 1: Merge not committed yet

```bash
git merge --abort
```

#### Case 2: Merge already committed

```bash
git reset --hard HEAD~1
```

> ⚠️ Use with caution, especially on shared branches.



### ✅ **55. What is Git LFS (Large File Storage)?**

**Git LFS** replaces large files (e.g., media, models) in your repo with text pointers, storing the real content in a separate location.

**Setup:**

```bash
git lfs install
git lfs track "*.mp4"
git add .gitattributes
git add video.mp4
```

> Helps keep repo size manageable.



### ✅ **56. How does Git handle large repositories?**

Git can become slow with:

* Huge history
* Large binary files
* Too many refs or tags

**Best practices:**

* Use **Git LFS**
* Clean old branches/tags
* Use **shallow clones**:

```bash
git clone --depth 1 https://github.com/user/repo.git
```

* Split monoliths into multiple repos (monorepo vs polyrepo discussion)







### **57. What is GitHub Actions?**

**GitHub Actions** is GitHub's built-in **CI/CD tool** (Continuous Integration/Continuous Deployment).

* Automates tasks like building, testing, and deploying code.
* Defined using **YAML** files in `.github/workflows/`.

**Example Use Case:**
Run tests when you push code to the repo.



### **58. How do you set up CI/CD with GitHub Actions?**

1. Create a file:

   ```
   .github/workflows/ci.yml
   ```

2. Example workflow:

   ```yaml
   name: Node.js CI

   on: [push, pull_request]

   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
         - uses: actions/checkout@v2
         - name: Set up Node
           uses: actions/setup-node@v2
           with:
             node-version: '18'
         - run: npm install
         - run: npm test
   ```

> This workflow installs dependencies and runs tests on every push or PR.


### **59. How do you add collaborators to a GitHub repository?**

1. Go to your repository.
2. Click on **Settings > Collaborators & Teams**.
3. Add by GitHub username/email.
4. They’ll receive an invitation.

> You must have at least **Admin access** to do this.



### **60. What are GitHub Issues and how are they used?**

GitHub **Issues** are used for:

* Bug reports
* Feature requests
* Task tracking

**Example:**

```markdown
Title: 🐛 Fix navbar not responsive
Description: The navbar breaks on screen widths < 400px.
```

You can assign, label, comment, and close issues.

### **61. What are GitHub Projects?**

**GitHub Projects** is a **Kanban-style board** that lets you manage and track issues, PRs, and tasks.

Features:

* Columns like “To Do,” “In Progress,” “Done”
* Link Issues and PRs
* Great for agile workflow


### **62. What is the use of a `README.md` file?**

The `README.md`:

* Provides a **summary of the project**
* Explains how to **install, run, or contribute**
* Uses **Markdown syntax** for formatting

**Example:**

````markdown
# My Project
A web app to manage tasks.

## Installation
```bash
npm install
npm start
````





### **63. What is a GitHub Gist?**

A **Gist** is a **simple way to share code snippets**, configs, or notes.

- Can be public or secret.
- Supports versioning.
- You can embed them anywhere.

[Create Gist here](https://gist.github.com/)


### **64. What are GitHub Pages?**

**GitHub Pages** lets you host **static websites** from a GitHub repo.

**Use cases:**
- Portfolios
- Documentation
- Blogs (via Jekyll)

**Setup:**
1. Push static files to a branch (`main`, `docs/`, or `gh-pages`).
2. Go to **Settings > Pages**, choose source branch.


### **65. How do you set branch protection rules on GitHub?**

1. Go to **Settings > Branches**.
2. Click “Add rule”.
3. Select branch (e.g., `main`).
4. Enable protections like:
   - Require pull request review
   - Require status checks
   - Restrict who can push


### **66. What is the difference between private and public repositories?**

| Repository Type | Who Can See | Use Cases                      |
|-----------------|-------------|--------------------------------|
| Public          | Everyone    | Open-source, learning          |
| Private         | Only invited| Commercial, internal projects  |



### **67. What are GitHub Workflows and Secrets?**

- **Workflows** = automation scripts defined in `.github/workflows/`.
- **Secrets** = encrypted variables used in workflows.

**Set secrets:**
Go to **Settings > Secrets > Actions**

Use in YAML:
```yaml
env:
  API_KEY: ${{ secrets.API_KEY }}
````



### **68. What are CODEOWNERS in GitHub?**

* File: `.github/CODEOWNERS`
* Automatically **requests review** from specified people for changes.

**Example:**

```
/src/ @vikash
*.js @frontend-team
```

> Useful for enforcing responsibility over critical code.



### **69. What is the purpose of the `.github` directory?**

Holds GitHub-specific configurations like:

* `workflows/`
* `CODEOWNERS`
* `ISSUE_TEMPLATE/`
* `PULL_REQUEST_TEMPLATE.md`
* `FUNDING.yml`



## ✅ Git Best Practices & Real-World Scenarios



### **70. What are some Git best practices?**

* Use feature branches.
* Write meaningful commit messages.
* Commit small, logical changes.
* Rebase before merging (if required).
* Use `.gitignore`.
* Use Pull Requests for review.



### **71. How do you handle sensitive information in a Git repository?**

* Use `.env` files.
* Add `.env` to `.gitignore`.
* Never hardcode secrets.
* If leaked:

  * Remove from history (`filter-repo`)
  * Revoke exposed credentials



### **72. How do you collaborate using Git in a team?**

* Use **feature branches**.
* Follow **PR-based reviews**.
* Sync frequently:

  ```bash
  git pull origin main --rebase
  ```
* Resolve conflicts carefully.



### **73. How do you review code in GitHub?**

1. Go to Pull Request.
2. Use “Files changed” tab.
3. Add comments, suggest changes.
4. Approve or Request changes.

> Great for learning and quality control.



### **74. How do you rollback production code using Git?**

* Find last stable commit:

  ```bash
  git log
  ```
* Create a new branch or revert:

  ```bash
  git revert <bad_commit>
  ```
* Or reset and force push (only if safe):

  ```bash
  git reset --hard <good_commit>
  git push origin main --force
  ```



### **75. What do you do if your branch is behind main or master?**

Update your branch:

#### Option 1: Merge

```bash
git checkout feature
git pull origin main
```

#### Option 2: Rebase (cleaner)

```bash
git checkout feature
git fetch
git rebase origin/main
```


### **76. How do you safely delete a remote branch?**

1. Delete locally:

   ```bash
   git branch -d feature-branch
   ```

2. Delete remotely:

   ```bash
   git push origin --delete feature-branch
   ```



### **77. How do you fix a detached HEAD?**

Detached HEAD = you're not on a branch.

**Fix:**

```bash
git checkout -b new-branch
```

This saves your current changes to a new branch.


### **78. What to do if your commit has sensitive information (like passwords)?**

1. **Remove the file**:

   ```bash
   git rm --cached .env
   ```

2. **Rewrite history**:

   ```bash
   git filter-repo --path .env --invert-paths
   ```

3. **Rotate credentials immediately**



### **79. How do you recover a deleted branch?**

Use `reflog` to find its last HEAD:

```bash
git reflog
git checkout -b old-branch-name <commit-hash>
```



### **80. How do you test changes locally before pushing to remote?**

* Run the app: `npm start`, `yarn dev`
* Run tests: `npm test`, `jest`
* Use linters: `eslint .`
* Build: `npm run build`
* Preview CI locally using tools like `act` or Docker



## ✅ **Git Commands Cheat Sheet (Commonly Asked)**



### 🔹 `git init`

Initializes a new **empty Git repository** in your project directory.

```bash
git init
```

> 📁 Creates a `.git/` directory — start tracking changes.



### 🔹 `git status`

Shows the **current state** of your working directory and staging area.

```bash
git status
```

> ✅ See untracked, modified, and staged files.



### 🔹 `git add .`

Stages **all modified and untracked files** for the next commit.

```bash
git add .
```

> 📌 Use before `git commit`.



### 🔹 `git commit -m "message"`

Records changes to the repository with a **commit message**.

```bash
git commit -m "Add login page"
```

> 📝 Commit often with meaningful messages.



### 🔹 `git push origin branch-name`

Pushes your commits from the current branch to the **remote branch**.

```bash
git push origin main
```

> 🔼 Upload local changes to GitHub or any remote.



### 🔹 `git pull origin branch-name`

Fetches and merges changes from the remote branch into your **local branch**.

```bash
git pull origin main
```

> 🔄 Sync with the latest remote updates.



### 🔹 `git clone repo-url`

Clones a remote repository to your **local machine**.

```bash
git clone https://github.com/user/repo.git
```

> 📥 Copies the full code and history.



### 🔹 `git checkout branch-name`

Switches to an **existing branch**.

```bash
git checkout feature-login
```

> 🚀 Use to work on different features or versions.



### 🔹 `git checkout -b new-branch`

Creates and switches to a **new branch**.

```bash
git checkout -b feature-payment
```

> 🌿 Great for starting new features.



### 🔹 `git branch`

Lists all **local branches**.

```bash
git branch
```

> 🧭 Shows current branch with `*`.



### 🔹 `git merge branch-name`

Merges another branch into your current branch.

```bash
git merge feature-login
```

> 🔀 Brings in changes from another branch.



### 🔹 `git reset --soft HEAD~1`

Moves HEAD back one commit, **keeps changes staged**.

```bash
git reset --soft HEAD~1
```

> 🧼 Undo commit, but keep your changes ready to re-commit.



### 🔹 `git reset --hard HEAD~1`

Resets everything — **commit + staging + working directory** — to the previous state.

```bash
git reset --hard HEAD~1
```

> ⚠️ **Destructive** — be cautious.


### 🔹 `git stash`

Temporarily saves your **uncommitted changes**.

```bash
git stash
```

> 📦 Useful if you need to switch branches without committing.



### 🔹 `git stash apply`

Reapplies the most recent stash to your working directory.

```bash
git stash apply
```

> 🎯 Doesn’t delete the stash.



### 🔹 `git stash drop`

Deletes the most recent stash.

```bash
git stash drop
```

> 🗑️ Clean up stash list after applying.



### 🔹 `git log`

Shows a **list of commits**, with hashes, messages, dates.

```bash
git log
```

> 📚 Use `--oneline --graph` for a prettier log:

```bash
git log --oneline --graph --all
```



### 🔹 `git diff`

Shows changes between:

* Working directory and staging area
* Two commits or branches

```bash
git diff
```

> 🔍 See what’s changed before committing.



### 🔹 `git remote -v`

Lists **remote repositories** and their URLs.

```bash
git remote -v
```

> 🔗 Verify where you're pushing and pulling from.


### 🔹 `git remote add origin url`

Adds a remote repository named `origin`.

```bash
git remote add origin https://github.com/user/repo.git
```

> 🔌 Connect your local repo to GitHub.

