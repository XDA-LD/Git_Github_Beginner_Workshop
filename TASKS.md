# 🧪 The Git Training Gauntlet

Welcome to the **LAU Byblos SE Club** Git simulation!

**⚠️ The Golden Rules:**

1. **Do not skip steps.** Each task builds on the last one.
2. **Read your terminal.** Git is very talkative; it usually tells you how to fix errors.
3. **Try before you peek.** If you get stuck, check `SOLUTIONS.md`.

---

### 🟢 PHASE 1: The Setup

**Task 0: Identity & Cloning**

1. **Sign up:** Create an account at [github.com](https://github.com).
2. **Install:** Ensure Git is installed ([git-scm.com](https://git-scm.com)).
3. **Configure:** Tell Git who you are:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```
4. **Clone:** Download this lab to your machine:
   ```bash
   git clone <your-repository-url>
   cd git-training-lab
   ```

---

### 🌿 PHASE 2: Standard Development

**Task 1: The Feature Branch**

1. Create and switch to a branch: `git checkout -b feature/auth`
2. Open `app.js`. Change the log to: `console.log("App started - Auth Module loaded");`
3. Stage and commit:
   - `git add app.js`
   - `git commit -m "Add auth module logs"`

**Task 2: The Typo Fix (Amend)**

1. Realize you forgot a comment in `app.js`. Add `// Auth version 1.0` at the top.
2. Stage it: `git add app.js`.
3. Instead of a new commit, "fix" your last one:
   - `git commit --amend -m "Add auth module and version comment"`

---

### 💥 PHASE 3: The Conflict Zone

**Task 3: Simulation of a Teammate**

1. Switch to main: `git checkout main`
2. Change `app.js` line 1 to: `console.log("App started - Main System Active");`
3. Stage and commit:
   - `git add app.js`
   - `git commit -m "Update main system logs"`

**Task 4: The Merge Conflict**

1. While on `main`, try to bring your auth work in: `git merge feature/auth`
2. **Fix the Crash:** Git will stop. Open `app.js`.
3. Manually delete the `<<<<`, `====`, and `>>>>` markers. Edit the file so both log messages remain.
4. Save, then run:
   - `git add app.js`
   - `git commit -m "Resolve merge conflict between main and auth"`

---

### 🛡️ PHASE 4: Survival Skills

**Task 5: The Stash (Interrupt!)**

1. Open `config.txt` and change `mode=development` to `mode=production`. **Do not commit.**
2. Your boss needs a clean status NOW. Run: `git stash`
3. Check `git status`. Notice the change is "hidden."
4. Bring it back: `git stash pop`.
5. Stage and commit: `git add config.txt` && `git commit -m "Set to production"`

**Task 6: The Panic Button (Reset)**

1. Open `notes/todo.txt` and add "DELETE ALL USER DATA".
2. Stage and commit it.
3. Undo that mistake completely (delete the commit AND the bad text):
   - `git reset --hard HEAD~1`

---

### 🧬 PHASE 5: Advanced Workflow

**Task 7: The Rebase (History Rewrite)**

1. Create a branch: `git checkout -b feature/ui`
2. Add a line to `notes/todo.txt` and commit it.
3. Switch to `main`. Add a comment to `app.js` and commit it.
4. Switch back to `feature/ui`.
5. **Rebase:** Move your UI work so it starts _after_ the new commit on main:
   - `git rebase main`

**Task 8: Security (.gitignore)**

1. Create `password.txt` with some "secret" text.
2. Notice `git status` sees it.
3. Create a `.gitignore` file and type `password.txt` inside it.
4. Verify `git status` no longer sees the secret file.

---

🏁 **Final Step:** Run `git log --oneline --graph --all` to see your beautiful history!
