# Complete Git Command Reference Guide

A comprehensive, production-ready cheat sheet covering Git commands from basic operations to advanced repository workflows, remote management, and troubleshooting.

---

## 1. Fundamental Architecture & Workflow

Git tracks changes across four key areas:

```
+------------------+      git add      +------------------+     git commit    +------------------+      git push      +--------------------+
|  Working Space   | ----------------> |   Staging Area   | ----------------> | Local Repository | -----------------> | Remote Repository  |
| (Unstaged Files) | <---------------- |   (Index/Cache)  | <---------------- |   (HEAD / History) | <----------------- | (GitHub / GitLab)  |
+------------------+     git restore   +------------------+    git reset HEAD   +------------------+     git fetch/pull   +--------------------+
```

- **Working Directory**: Local directory containing active project files.
- **Staging Area (Index)**: Pre-commit holding area for changes to be included in the next snapshot.
- **Local Repository**: The `.git` metadata store containing committed commits and branch histories.
- **Remote Repository**: Central hosted repository (e.g., GitHub, GitLab) shared across team members.

---

## 2. Global Configuration

Set up identity, defaults, and global settings across your machine.

```bash
# Set global commit author name
git config --global user.name "Your Name"

# Set global commit author email
git config --global user.email "your.email@example.com"

# Set default branch name for new repositories to 'main'
git config --global init.defaultBranch main

# Set default command-line text editor
git config --global core.editor "code --wait"

# Enable automatic color formatting in terminal output
git config --global color.ui auto

# List all active configurations and their file origin
git config --list --show-origin
```

---

## 3. Initializing & Cloning Repositories

Create new repositories or clone existing remote projects.

```bash
# Initialize a new local Git repository in current directory
git init

# Initialize a new repository within a specific directory name
git init my-project

# Clone a remote repository using HTTPS protocol
git clone https://github.com/USERNAME/REPOSITORY.git

# Clone a remote repository using SSH protocol
git clone git@github.com:USERNAME/REPOSITORY.git

# Clone into a custom target folder name
git clone https://github.com/USERNAME/REPOSITORY.git custom-folder-name
```

---

## 4. Remote Repository Management

Connect, update, and manage remote repository endpoints.

```bash
# Connect local repository to a remote server ('origin')
git remote add origin https://github.com/USERNAME/REPOSITORY.git

# Display configured remote connections and their URLs (verbose)
git remote -v

# Update the URL of an existing remote connection
git remote set-url origin https://github.com/USERNAME/NEW-REPOSITORY.git

# Rename a remote connection reference
git remote rename origin upstream

# Remove a remote connection reference
git remote remove upstream

# Display detailed configuration information for a remote server
git remote show origin
```

---

## 5. Daily Development Workflow

Track, stage, and commit modifications.

```bash
# View workspace status (tracked, untracked, modified files)
git status

# View workspace status in short/condensed format
git status -s

# Stage a specific file for commit
git add path/to/file.ext

# Stage all new, modified, and deleted files in working space
git add .

# Stage all changes across the entire repository workspace
git add -A

# Interactively stage specific change blocks (hunks) within files
git add -p

# Commit staged changes with an inline commit message
git commit -m "feat: implement user login flow"

# Stage all tracked modified files and commit in one command
git commit -am "fix: correct navbar responsiveness issue"

# Amend the most recent commit message or include newly staged files
git commit --amend -m "feat: complete user login authentication flow"
```

---

## 6. Inspecting History & Changes

Review project commit history and file diffs.

```bash
# Show complete commit log history
git log

# Display commit history formatted as one line per commit
git log --oneline

# Display commit log with a visual ASCII branch graph
git log --graph --oneline --all

# Limit commit log output to the N most recent commits
git log -n 5

# View commit history filtering for a specific file
git log -p path/to/file.ext

# Show unstaged modifications between working space and staging index
git diff

# Show staged changes ready for commit vs last commit
git diff --staged

# Compare differences between two branches
git diff main feature-branch

# Inspect commit details and diff for a specific commit hash
git show <commit-hash>
```

---

## 7. Branching & Merging

Isolate feature development and integrate branch changes.

```bash
# List all local branches (active branch marked with *)
git branch

# List both local and remote-tracking branches
git branch -a

# Create a new branch (without switching to it)
git branch feature/checkout

# Switch working space to an existing branch
git switch feature/checkout
# Legacy alternative:
git checkout feature/checkout

# Create a new branch and switch to it immediately
git switch -c feature/payments
# Legacy alternative:
git checkout -b feature/payments

# Merge a specified branch into the currently active branch
git merge feature/checkout

# Delete a local branch (safely checks for unmerged changes)
git branch -d feature/checkout

# Force-delete an unmerged local branch
git branch -D feature/checkout

# Delete a branch on the remote server
git push origin --delete feature/checkout
```

---

## 8. Syncing with Remote Repositories

Fetch, pull, and push updates between local and remote environments.

```bash
# Push local branch to remote and set tracking upstream (first push)
git push -u origin main

# Push committed local changes to remote branch
git push

# Force push local changes (safely checks remote state before overwriting)
git push --force-with-lease

# Fetch updates from remote without merging into local branches
git fetch origin

# Fetch updates from all configured remote repositories
git fetch --all

# Download and automatically merge updates into current branch
git pull

# Download remote updates and rebase current branch onto target branch
git pull --rebase origin main
```

---

## 9. Undoing Changes & History Reset

Roll back changes, unstage files, or reset commit histories.

```bash
# Discard local uncommitted changes in a specific file
git restore path/to/file.ext

# Unstage a file while preserving working space modifications
git restore --staged path/to/file.ext

# Preview untracked files to be removed (dry-run)
git clean -nd

# Force-remove untracked files and directories
git clean -fd

# Safely undo a previous commit by appending a new inverse commit
git revert <commit-hash>

# Soft reset: move HEAD back N commits, keeping changes STAGED
git reset --soft HEAD~1

# Mixed reset (default): move HEAD back N commits, keeping changes UNSTAGED
git reset --mixed HEAD~1

# Hard reset: move HEAD back N commits, DISCARDING all working changes
git reset --hard HEAD~1
```

---

## 10. Stashing Temporary Modifications

Temporarily store uncommitted workspace changes without creating a commit.

```bash
# Stash current modified working files (staged and unstaged)
git stash

# Stash working changes with a descriptive label
git stash save "WIP: dark mode theme styling"

# Include untracked files in stash
git stash -u

# List all stashed entries
git stash list

# Re-apply most recent stash and remove it from stash list
git stash pop

# Apply specific stash entry without removing it from list
git stash apply stash@{1}

# Delete a specific stash entry
git stash drop stash@{0}

# Delete all stash entries
git stash clear
```

---

## Cheat Sheet Summary Table

| Category | Command | Description |
| :--- | :--- | :--- |
| **Config** | `git config --global user.name "Name"` | Set global author identity |
| **Init** | `git init` | Initialize local Git repository |
| **Clone** | `git clone <url>` | Download repository from remote |
| **Remote** | `git remote add origin <url>` | Connect local repository to remote URL |
| **Status** | `git status` | View workspace status & changes |
| **Stage** | `git add .` | Stage all working changes |
| **Commit** | `git commit -m "msg"` | Save staged snapshot with message |
| **Branch** | `git switch -c <name>` | Create & switch to new branch |
| **Merge** | `git merge <branch>` | Merge specified branch into current |
| **Push** | `git push -u origin <branch>` | Upload local commits to remote |
| **Pull** | `git pull` | Fetch and merge remote changes |
| **Stash** | `git stash` | Temporarily save uncommitted work |
