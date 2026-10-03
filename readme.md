# Git and GitHub

## Theory

### Git

**Git** is a version control software that helps us track changes made to files and projects.

It helps us:

- Track changes in files
- Save different versions of a project
- Go back to previous versions
- Work with branches
- Collaborate with other developers
- Merge changes from different branches

### GitHub

**GitHub** is a cloud-based service/platform where we can store Git repositories and collaborate with other developers.

In simple terms:

```text
Git     → Version Control Software
GitHub  → Platform/service for hosting Git repositories
```

### Repository (Repo)

A **repository** is a project that is tracked using Git.

A repository can contain:

- Source code
- Files
- Folders
- Git history
- Branches
- Commits

When a repository is hosted on GitHub, we can access and collaborate on it remotely.

---

# GitHub CLI Commands

## `gh auth login`

Logs in to your GitHub account using GitHub CLI.

```bash
gh auth login
```

---

## `gh auth logout`

Logs out of the GitHub account from GitHub CLI.

```bash
gh auth logout
```

---

## `gh auth status`

Shows the current GitHub authentication status.

```bash
gh auth status
```

---

## `gh repo create`

Creates a new repository on GitHub.

```bash
gh repo create repo_name --public
```

This creates a public repository on GitHub.

---

# Git Configuration

## `git config --global user.email`

Sets the email address that Git associates with your commits.

```bash
git config --global user.email "email@example.com"
```

The email is stored in the commit metadata.

---

## `git config --global user.name`

Sets the name that Git associates with your commits.

```bash
git config --global user.name "Your Name"
```

---

# Basic Terminal Commands

## `git --version`

Shows the installed Git version.

```bash
git --version
```

---

## `cd ..`

Moves from the current directory to its parent directory.

```bash
cd ..
```

Example:

```text
C:/Users/Sai/Projects/Git
                    ↑
                 cd ..
                    ↓
C:/Users/Sai/Projects
```

---

## `cd <folder>`

Moves into a folder.

```bash
cd foldername
```

### Tab Completion

After typing part of a folder name, pressing **Tab** can automatically complete the name.

Example:

```bash
cd git<Tab>
```

---

## `ls`

Lists the files and folders in the current directory.

```bash
ls
```

---

## `pwd`

Shows the current working directory.

```bash
pwd
```

It tells you the exact path of the directory you are currently inside.

---

## `mkdir`

Creates a new folder.

```bash
mkdir foldername
```

You can also create multiple folders:

```bash
mkdir folder1 folder2 folder3
```

---

## `rmdir`

Removes a directory.

```bash
rmdir foldername
```

---

# Starting a Git Repository

## `git status`

Shows the current state of the Git repository.

```bash
git status
```

It can tell you:

1. Whether the current directory is a Git repository
2. Which branch you are currently on
3. Which files are untracked
4. Which files have been modified
5. Which files are staged

---

## `git init`

Initializes Git in the current folder.

```bash
git init
```

This creates a hidden `.git` directory.

The `.git` directory contains the information Git needs to track the repository.

```text
Project
│
├── file1.txt
├── file2.txt
└── .git
```

---

# Creating and Removing Files

## `touch`

Creates a new file.

```bash
touch filename
```

Example:

```bash
touch README.md
```

---

## `rm`

Removes a file.

```bash
rm filename
```

Example:

```bash
rm test.txt
```

---

# Git Staging and Commits

## `git add`

Moves changes into the **staging area**.

```bash
git add filename
```

To stage all changed files:

```bash
git add .
```

The basic flow is:

```text
Working Directory
       ↓
   git add
       ↓
Staging Area
       ↓
  git commit
       ↓
Repository
```

---

## `git commit`

Creates a commit containing the staged changes.

```bash
git commit -m "Your commit message"
```

Example:

```bash
git commit -m "Added Git notes"
```

A commit is basically a **saved snapshot of your project at a particular point in time**.

---

# Branches

## `git branch`

Shows the branches in the repository.

```bash
git branch
```

The branch with `*` is the branch you are currently on.

---

## `git branch <branch-name>`

Creates a new branch.

```bash
git branch gitone
```

This creates the branch but does **not** switch to it.

---

## `git switch <branch-name>`

Switches from the current branch to another branch.

```bash
git switch gitone
```

---

## Create and Switch to a Branch

You can also create and switch to a new branch in one command:

```bash
git switch -c gitone
```

---

# Git History

## `git log`

Shows the commit history of the current branch.

```bash
git log
```

---

## `git log --oneline`

Shows the commit history in a shorter format.

```bash
git log --oneline
```

Example:

```text
4da6622 Added Git notes
9bc1234 Added README
7fa2345 Initial commit
```

The first value is the shortened commit ID.

---

# GitHub Remote Repository

## `git remote -v`

Shows the URLs of the remote repositories connected to your local repository.

```bash
git remote -v
```

Example:

```text
origin  https://github.com/username/project.git (fetch)
origin  https://github.com/username/project.git (push)
```

---

## `git remote add origin`

Connects the local Git repository to a remote GitHub repository.

```bash
git remote add origin https://github.com/username/project.git
```

Here:

```text
origin → short name for the remote repository
```

---

# Pushing Changes to GitHub

## `git push -u origin <branch-name>`

Pushes the local branch to the remote GitHub repository and sets the upstream relationship.

```bash
git push -u origin main
```

The `-u` means Git remembers that:

```text
Local main
    ↓
Remote origin/main
```

After the upstream relationship is established, you can usually use:

```bash
git push
```

instead of:

```bash
git push origin main
```

---

## `git push`

Pushes your local commits to the configured remote branch.

```bash
git push
```

---

# Merging Branches

## `git merge <branch-name>`

Merges the specified branch into the branch you are currently on.

For example, if you want to merge `gitone` into `main`:

```bash
git switch main
git merge gitone
```

The important point is:

> The branch you are currently on is the branch that receives the changes.

Example:

```text
             gitone
               │
               │
               ▼
main ──────────●
       merge
```

---

# Deleting a Branch

## `git branch -d`

Deletes a local branch.

```bash
git branch -d gitone
```

Usually, you delete a branch after its work has been merged.

---

# Checking Differences

## `git diff`

Shows differences between the current working directory and the last committed state.

```bash
git diff
```

It helps you see what has changed but has not yet been staged.

---

## `git diff --staged`

Shows the differences that are currently in the staging area.

```bash
git diff --staged
```

So:

```text
git diff
    ↓
Changes NOT staged

git diff --staged
    ↓
Changes already staged
```

---

# Checkout

## `git checkout`

`git checkout` has multiple uses.

### Switch to another branch

```bash
git checkout gitone
```

### Go to a previous commit

```bash
git checkout 4da6622
```

This can put you into a **detached HEAD** state.

In this state, you can inspect the project exactly as it existed at that commit.

For normal branch switching, `git switch` is generally easier to understand.

---

# Rebase

## `git rebase <branch-name>`

Rebase takes the commits from your current branch and reapplies them on top of another branch.

Example:

```bash
git switch gitone
git rebase main
```

Conceptually:

### Before

```text
A---B---C  main
     \
      D---E  gitone
```

### After

```text
A---B---C---D'---E'  gitone
```

Rebase creates new commit IDs because the commits are reapplied.

> Rebase does not simply "temporarily remove a branch." It changes the base of a branch's commits.

---

# Clone

## `git clone`

Downloads an existing Git repository from a remote location to your local computer.

```bash
git clone https://github.com/username/project.git
```

After cloning:

```text
GitHub Repository
       ↓
   git clone
       ↓
Local Repository
```

---

# Fetch

## `git fetch`

Downloads new commits and other changes from the remote repository **without automatically merging them into your current working branch**.

```bash
git fetch
```

For example:

```text
GitHub
  │
  │ git fetch
  ↓
Local remote-tracking information
```

Your working files are not automatically changed by the fetch itself.

You can then inspect the changes before deciding what to do.

---

# Pull

## `git pull`

`git pull` generally performs:

```text
git fetch
    +
git merge
```

So it downloads changes from the remote repository and integrates them into your current branch.

```bash
git pull
```

Conceptually:

```text
GitHub
   ↓
fetch
   ↓
Local repository
   ↓
merge
   ↓
Current branch
```

---

# Forking

A **fork** is a copy of another person's GitHub repository under your own GitHub account.

Example:

```text
Other person's GitHub
        │
        │ Fork
        ↓
Your GitHub account
        │
        ↓
Your copy of the repository
```

Forking is commonly used when you want to contribute to a project that you don't have direct write access to.

---

# Pull Request

A **Pull Request (PR)** is a request to merge your changes into another repository or branch.

A common open-source workflow is:

```text
Other person's repository
          ↓
        Fork
          ↓
Your GitHub repository
          ↓
       Clone
          ↓
Make changes locally
          ↓
        Commit
          ↓
         Push
          ↓
Create Pull Request
          ↓
Project maintainers review
          ↓
Changes may be merged
```

A Pull Request does **not automatically mean the changes will be accepted**. The project maintainers review the proposed changes before merging them.

---

# Removing Git Tracking

## `rm -rf .git`

Removes the `.git` directory from the current project.

```bash
rm -rf .git
```

This removes the Git repository metadata from that folder.

After doing this, the folder is no longer a Git repository.

### ⚠️ Be Careful

This command is destructive.

It removes the local Git history and configuration stored inside `.git`.

The actual project files remain, but Git will no longer track the folder.

---

# Basic Git Workflow

The most important workflow to remember is:

```text
Create / Modify files
        ↓
   git status
        ↓
     git add
        ↓
   git diff --staged
        ↓
    git commit
        ↓
     git push
        ↓
      GitHub
```

For collaboration:

```text
GitHub
   ↓
git clone
   ↓
Local repository
   ↓
Create branch
   ↓
Make changes
   ↓
git add
   ↓
git commit
   ↓
git push
   ↓
Pull Request
   ↓
Review
   ↓
Merge
```

---

# Git vs GitHub — Quick Difference

| Git | GitHub |
|---|---|
| Software | Online platform/service |
| Version control system | Hosts Git repositories |
| Works locally | Primarily remote/cloud-based |
| Tracks changes | Stores and shares repositories |
| Creates commits | Displays and manages commits |
| Creates branches | Hosts branches |
| Can work without GitHub | Uses Git repositories |

### Simple way to remember

```text
Git = Tool that tracks your project history

GitHub = Platform where you can store,
         share and collaborate on Git repositories
```
