# 🗝️ Solutions Guide

### 🟢 Task 0: Setup

```bash
git config --global user.name "Name"
git config --global user.email "email@lau.edu"
git clone <url>
cd git-training-lab
```

### 🌿 Task 1 & 2: Branching & Amending

```bash
git checkout -b feature/auth
# [Edit app.js]
git add app.js
git commit -m "Add auth module logs"
# [Edit app.js again]
git add app.js
git commit --amend -m "Add auth module and version comment"
```

### 💥 Task 3 & 4: Conflict Resolution

```bash
git checkout main
# [Edit app.js]
git add app.js
git commit -m "Update main system logs"
git merge feature/auth
# [Manually fix app.js markers]
git add app.js
git commit -m "Resolve merge conflict"
```

### 🛡️ Task 5 & 6: Stash & Reset

```bash
# [Edit config.txt]
git stash
git stash pop
git add config.txt
git commit -m "Set to production"

# [Edit todo.txt]
git add notes/todo.txt
git commit -m "bad commit"
git reset --hard HEAD~1
```

### 🧬 Task 7 & 8: Rebase & Ignore

```bash
git checkout -b feature/ui
# [Edit notes/todo.txt]
git add notes/todo.txt
git commit -m "Add UI task"

git checkout main
# [Edit app.js]
git add app.js
git commit -m "Minor update"

git checkout feature/ui
git rebase main

# Security
touch password.txt
echo "password.txt" > .gitignore
git status
```
