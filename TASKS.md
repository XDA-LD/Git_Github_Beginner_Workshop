# 🧪 The Git Training Gauntlet

Welcome to the **LAU Byblos SWE Club** Git simulation!

**⚠️ The Golden Rules:**

1. **Do not skip steps.** Each task builds on the last one.
2. **Read your terminal.** Git is very talkative; it usually tells you how to fix errors.
3. **Try before you peek.** If you get stuck, ask the lab assistant. (if you are not in the workshop session, check `SOLUTIONS.md`)

---

### 🟢 PHASE 1: The Setup
**Task 0: Prerequisites, Forking & Cloning**

*Before we write any code, we need to set up your account, install the required tools, and get your own copy of the lab.*

**Step 1: Create a GitHub Account**
*Why? GitHub is the cloud where we will store and share our code.*
1. Go to [github.com](https://github.com) and click **Sign Up** in the top right.
2. Follow the prompts to create a free account. (Tip: Use a professional username, as employers will look at this later!)

**Step 2: Install Git on Your Computer**
*Why? Git is the engine that runs on your computer to track code changes.*
1. Go to [git-scm.com/downloads](https://git-scm.com/downloads).
2. Download the version for your operating system (Windows or Mac).
3. Run the installer and just keep clicking "Next" to accept all the default settings.

**Step 3: "Fork" the Repository (Make your own cloud copy)**
*Why? You cannot edit the SE Club's master project directly. Forking creates a 100% identical copy under your own GitHub profile where you have full control.*
1. Go to the GitHub link provided by Rami or the SE Club.
2. Look at the top-right corner of the page and click the button that says **"Fork"**.
3. Leave the settings as they are and click **"Create fork"**.
4. **⚠️ CRITICAL CHECK:** Look at your web browser's address bar. Make sure you are now on `github.com/YOUR_USERNAME/Git_Github_Beginner_Workshop`. If you still see the SE Club's name, you are in the wrong place!

**Step 4: Open Your Terminal**
*We need to talk to your computer using text commands.*
* **Windows Users:** Click your Start menu, search for **"Git Bash"**, and open it.
* **Mac Users:** Press `Cmd + Space`, search for **"Terminal"**, and open it.

**Step 5: Configure Your "Signature"**
*Why? Git needs to know who is making changes. This is like a name tag. It is NOT logging into your account.*
1. In your terminal, type the following commands. 
2. **Important:** Replace `"Your Name"` and `"your.email@example.com"` with your *actual* information. **Keep the quotation marks!**
   ```bash
   git config --global user.name "John Doe"
   git config --global user.email "john.doe@lau.edu"
   ```

**Step 6: "Clone" YOUR Fork (Download to your laptop)**
*Why? Now that you have a copy on the GitHub website, we need to download it to your laptop so you can actually edit the files.*
1. On your personal GitHub fork page, click the green **"<> Code"** button.
2. Make sure the "HTTPS" tab is selected, and click the small copy icon to copy the web address.
3. Go back to your terminal and type `git clone` followed by a space, then paste that link. It will look like this:
   ```bash
   git clone https://github.com/YOUR_USERNAME/Git_Github_Beginner_Workshop.git
   ```
4. Press Enter. You will see text scrolling as it downloads the files. *(Note: Because it is public, it will download instantly without asking for a password).*

**Step 7: Enter the Lab Folder**
*Why? Your terminal is currently looking at your computer's main folder. You need to tell it to "open" the new folder you just downloaded. We do this using `cd` (Change Directory).*
1. Type the following command and press Enter:
   ```bash
   cd Git_Github_Beginner_Workshop
   ```
2. You are now inside the lab! You are ready to start coding.

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
