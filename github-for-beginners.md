# GitHub for Absolute Beginners

This guide walks you through everything you need to start using GitHub from your terminal — from logging in for the first time to pushing your first change.

📚 **Keep learning at your own pace:**
- 🟢 [Beginner](https://docs.github.com/en/get-started) — GitHub's official "Get Started" docs
- 🟡 [Intermediate](https://skills.github.com/) — GitHub Skills, free hands-on exercises
- 🔴 [Advanced](https://resources.github.com/learn/pathways/) — GitHub Learning Pathways, in-depth expert-guided content

---

## 0. What You Need Before Starting

- A [GitHub account](https://github.com/join) (free)
- [Git installed](https://git-scm.com/downloads) on your computer
- A terminal app (Terminal on Mac/Linux, Command Prompt or Git Bash on Windows)

To check if Git is already installed, open your terminal and type:

```bash
git --version
```

If you see a version number, you're good to go.

---

## 1. How to Log In to GitHub From Your Terminal

GitHub no longer lets you log in with just a username and password from the terminal. Instead, you use a **Personal Access Token (PAT)** — think of it as a special password just for your terminal.

### How to Create a Token

1. Log in to GitHub in your browser.
2. Click your profile picture (top right) → **Settings**.
3. Scroll down and click **Developer settings** (bottom of the left sidebar).
4. Click **Personal access tokens** → **Tokens (classic)**.
5. Click **Generate new token** → **Generate new token (classic)**.
6. Give it a name (e.g., "My Laptop"), set an expiration date, and check the box for **repo** (this gives it permission to work with your repositories).
7. Click **Generate token**.
8. **Copy the token immediately** — GitHub only shows it once. Save it somewhere safe (like a password manager).

### Using the Token to Log In

The first time you try to push or pull from a private action (like cloning a private repo or pushing code), Git will ask for your username and password:

```
Username: your-github-username
Password: paste-your-token-here
```

Note: You paste the **token**, not your actual GitHub password.

💡 *Tip: Most systems will remember your token after the first successful login, so you won't have to paste it every time.*

---

## 2. How to Create a Repository on GitHub

A **repository** (or "repo") is basically a project folder that lives on GitHub.

1. Go to [github.com](https://github.com) and log in.
2. Click the **+** icon in the top right → **New repository**.
3. Give your repository a name (e.g., `my-first-project`).
4. Choose **Public** (anyone can see it) or **Private** (only you and people you invite).
5. Check **Add a README file** (this creates a starting file so your repo isn't empty).
6. Click **Create repository**.

You now have a repository living on GitHub's servers.

---

## 3. Clone the Repo to Your Local Machine

"Cloning" means downloading a copy of the GitHub repo onto your own computer (laptop or desktop) so you can work on it.

1. On your repository's GitHub page, click the green **Code** button.
2. Copy the URL shown (it will look like `https://github.com/your-username/my-first-project.git`).
3. In your terminal, navigate to the folder where you want to store the project, then run:

```bash
git clone https://github.com/your-username/my-first-project.git
```

4. Move into the new folder that was created:

```bash
cd my-first-project
```

You now have a local copy of the repo on your machine.

---

## 4. Modify Your Code Locally

Open the project folder in your favorite code editor (like VS Code) and make changes — edit a file, add a new one, whatever your project needs.

Once you've made a change, go back to your terminal and check what's changed:

```bash
git status
```

This shows you which files have been modified.

---

## 5. Add, Commit, and Push Your Code

Getting your changes from your computer back onto GitHub is a three-step process:

### Step 1: Add
This tells Git which changes you want to include in your next "save point."

```bash
git add .
```

*(The `.` means "add everything I changed." You can also add specific files, like `git add filename.txt`.)*

### Step 2: Commit
This creates a snapshot of your changes with a short description.

```bash
git commit -m "Describe what you changed here"
```

Example:
```bash
git commit -m "Add welcome message to homepage"
```

### Step 3: Push
This uploads your commit to GitHub.

```bash
git push
```

Refresh your repository page on GitHub — your changes should now appear.

---

## 6. Branches and Merging

As you get more comfortable, you'll want to avoid making changes directly to your main code. That's where branches come in.

### What Is a Branch?

A **branch** is a copy of your repository where you can safely make changes without affecting the main version (usually called `main`). Think of it like working on a draft, while the original stays untouched.

To create and switch to a new branch:

```bash
git checkout -b my-new-feature
```

Now any changes, adds, commits, and pushes you make happen on `my-new-feature`, not on `main`.

To push a new branch to GitHub for the first time:

```bash
git push -u origin my-new-feature
```

### What Is Merging?

Once your changes on the branch look good, you **merge** them back into `main` — usually through a **Pull Request (PR)**:

1. Go to your repository on GitHub.
2. You'll see a prompt to **Compare & pull request** for your recently pushed branch. Click it.
3. Add a title and description explaining your changes.
4. Click **Create pull request**.
5. Once it's reviewed (by you or a teammate), click **Merge pull request**.

Your changes are now part of the main codebase. 🎉

---

## Quick Reference Cheat Sheet

| Action | Command |
|---|---|
| Check Git version | `git --version` |
| Clone a repo | `git clone <url>` |
| Check status | `git status` |
| Stage changes | `git add .` |
| Commit changes | `git commit -m "message"` |
| Push changes | `git push` |
| Create a branch | `git checkout -b branch-name` |
| Push a new branch | `git push -u origin branch-name` |
