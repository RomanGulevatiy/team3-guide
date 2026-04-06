<div align="center">

# Team 3 - Start Guide

[Українська](README.md) • English • [Русский](README-ru.md)

</div>

> [!NOTE]
> This is a quick reference guide. If you forget something - find the right section and read it again.
>
> **Questions or ideas?** -> Discord: `Java pro` -> `#team-3`

---

## Navigation

1. [Setup](#1-setup)
   - [IntelliJ IDEA Ultimate](#11-intellij-idea-ultimate)
   - [File Header](#12-file-header)
2. [Git Basics](#2-git-basics)
   - [What is Git and GitHub?](#21-what-is-git-and-github)
   - [Connect GitHub Account](#22-connect-github-account)
   - [Clone the Repository](#23-clone-the-repository)
3. [Daily Work](#3-daily-work)
   - [Branches](#31-branches)
   - [Commit](#32-commit)
   - [Push](#33-push)
4. [Pull Request (PR)](#4-pull-request-pr)
   - [How to Open a PR](#41-how-to-open-a-pr)
   - [If You Got a Comment](#42-if-you-got-a-comment)

---

## 1. Setup

### 1.1. IntelliJ IDEA Ultimate

Use **IntelliJ IDEA Ultimate** for this project (not Community).

> [!TIP]
> It is free for students. Step-by-step guide from the university: [link](https://duikt.edu.ua/uploads/n_11828_56886710.pdf)

1. Go to [jetbrains.com/academy](https://www.jetbrains.com/academy/student-pack/) -> click **"Request now"**
2. Sign up with your university email (`@duikt.edu.ua`)
3. Confirm your email by clicking the link in the letter
4. Download and install IntelliJ IDEA Ultimate using the link from the letter

![Intellij IDEA Ultimate](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/intellij-ultimate.png)

---

### 1.2. File Header

File Header is an automatic author signature added to every new file. You set it up only once.

1. Press `Shift` twice -> type `File and Code Templates` -> select it from the list
2. Go to the **Includes** tab -> click **File Header**
3. Paste the template below (replace with your own data):

> [!TIP]
> Write your name in English. `${DATE}` sets the current date automatically.

```java
/**
 * Created by FirstName LastName on ${DATE}.
 * github: github.com/your-username
 */
```

---

## 2. Git Basics

### 2.1. What is Git and GitHub?

**Git** is a system that saves the full history of changes in your code. Every `commit` is a save point you can go back to. **GitHub** is a cloud service where the team's shared repository is stored.

---

### 2.2. Connect GitHub Account

Do this once after you install IntelliJ IDEA.

1. Go to `File -> Settings` (or press `Ctrl + Alt + S`) -> `Version Control -> GitHub`
2. Click `+` -> `Log In with Token`
3. Click **Generate** - a browser window will open
4. Check all boxes -> generate the token -> copy it
5. Paste the token into the **Token** field -> click **Add account**

---

### 2.3. Clone the Repository

Cloning means downloading the project from GitHub to your computer. You do this only once.

1. Go to the [repository page](https://github.com/Java-Spring-Sprint-Class/teamwork-management-system-team-3) -> click the **`<> Code`** button -> copy the HTTPS link
2. In IntelliJ IDEA: `File -> New -> Project from Version Control`
3. Paste the link -> click **Clone**

![GitHub clone](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/github-clone.gif)

---

## 3. Daily Work

### 3.1. Branches

A **branch** is a separate line of changes, isolated from the main team code.

> [!CAUTION]
> Never write code directly in the `main` branch!

```
main ──●────────────────────────●── (stable code)
        \                      /
         ●────● feature/my-task (your branch)
```

**Before starting each new task:**

```bash
# Make sure you are on main
git status

# Switch to main (if you were on another branch)
git checkout main

# Download the latest changes
git pull

# Create a new branch and switch to it
git checkout -b type/task-name
```

**Branch naming rules.** Format: `type/short-name`. Name must be in **English**, words separated by `-`.

| Task type             | Prefix      | Example                             |
|-----------------------|-------------|-------------------------------------|
| New feature           | `feature/`  | `feature/user-login`       |
| Bug fix               | `fix/`      | `fix/login-null-pointer`   |
| Refactoring           | `refactor/` | `refactor/user-service`    |

![Branch switching](https://github.com/RomanGulevatiy/team3-guide/blob/main/images/branch-switching.gif)

---

### 3.2. Commit

A commit saves your changes **locally** (on your device).

> [!IMPORTANT]
> The commit message must clearly say **what** was done. Not "changes", not "edits", not "fix2".

```bash
# Check which files were changed
git status

# Add files to the commit
git add .

# Save the changes
git commit -m "type: short description of what was done"
```

**Commit types:**

| Type       | When to use                  | Example                                  |
|------------|------------------------------|------------------------------------------|
| `feat`     | New feature                  | `feat: add email validation`             |
| `fix`      | Bug fix                      | `fix: null pointer in UserService`       |
| `refactor` | Refactoring, no logic change | `refactor: extract validation to method` |

**Rules:**
- English only
- Lowercase after the colon
- Up to 72 characters
- Use present tense: `add`, `fix`, `update` (not `added`, `fixed`, `updated`)

---

### 3.3. Push

Push sends your local commits to GitHub.

```bash
git push origin type/your-branch-name
```

---

## 4. Pull Request (PR)

A **Pull Request** is a request to merge your branch into `main`. Before merging, another team member (reviewer) checks your code.

### 4.1. How to Open a PR

After `git push`, GitHub will show a banner **"Compare & pull request"** - click it.
Or: go to the **Pull requests** tab -> click **New pull request**.

Fill in the form:
- **Title:** short description of what was done - in commit format (`feat: add user login`)
- **Description:** what was done, what to check, any important notes
- **Reviewers:** choose a team member

Click **Create pull request**.

> [!WARNING]
> Do not merge the PR yourself - only after the reviewer approves it.

---

### 4.2. If You Got a Comment

1. Read the reviewer's comment
2. Make changes on the same branch (locally, in the IDE)
3. Save the changes: `git add .` -> new `commit` and `push` - it will be added to the already open PR automatically
4. Reply to the comment or click **"Resolve conversation"**

---

[^ Back to top](#team-3---start-guide)

---

> Last updated: April 2026 • Maintainer: [@RomanGulevatiy](https://github.com/RomanGulevatiy)
