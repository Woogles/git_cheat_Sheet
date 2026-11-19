# Git Cheat Sheet
### NetworkChuck Version (Time Machine, Sacred Timeline & Alternate Reality Edition)

---

# The 30-Second Mental Model

Think of Git as:

| Git Thing | What It Really Means |
|------------|---------------------|
| Git | Time Machine / Game Save System |
| Repository (Repo) | Project being tracked |
| Commit | Save Point |
| Branch | Alternate Timeline |
| Main Branch | Sacred Timeline |
| Staging Area | Letter in Envelope |
| HEAD | You Are Here marker |
| GitHub | Cloud Backup / Remote Repo |
| Merge | Fuse Timelines |
| Pull Request (PR) | Request to Merge Timelines |
| Restore | Reload Save |
| Checkout | Time Travel |

---

# The Git Workflow You'll Use Most

```text
Edit Files
     ↓
git status
     ↓
git add .
     ↓
git commit -m "what changed"
     ↓
git push
```

Mental shortcut:

```text
Modify → Stage → Save → Upload
```

---

# Core Concepts

## Working Directory

Your actual files.

```text
zombiestory.md
index.html
```

Nothing is saved to Git yet.

---

## Staging Area

Git's "waiting room."

Like writing a letter:

```text
Write Letter
    ↓
Put in Envelope
    ↓
Add Stamp
```

But haven't mailed it yet.

Command:

```bash
git add .
```

---

## Commit

A save point in your project.

Like:

```text
Envelope
    ↓
Mailbox
```

Command:

```bash
git commit -m "Added zombie story"
```

Think:

> Save Game

---

## Repository (Repo)

A folder Git is tracking.

Create one:

```bash
git init
```

Think:

```text
Regular Folder
      ↓
git init
      ↓
Time Machine Folder
```

---

# Essential Commands

---

## Check Git Version

```bash
git --version
```

Verify Git is installed.

---

## Configure Git

Tell Git who you are.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@email.com"
git config --global init.defaultBranch main
```

Think:

> Sign your work.

---

## Initialize Repository

```bash
git init
```

Creates:

```text
.git
```

Hidden folder containing the time machine.

---

## Check Status

```bash
git status
```

Shows:

- Current branch
- Modified files
- Staged files
- Untracked files

Think:

> What's going on right now?

---

## Add Files to Staging

Single file:

```bash
git add filename
```

Everything:

```bash
git add .
```

Think:

> Put the letter in the envelope.

---

## Commit Changes

```bash
git commit -m "Added new story beat"
```

Think:

> Create a save point.

---

## View History

Full log:

```bash
git log
```

Compact log:

```bash
git log --oneline
```

Think:

> Show me my save files.

---

## See Differences

Changes not staged:

```bash
git diff
```

Changes already staged:

```bash
git diff --staged
```

Think:

> Show me exactly what changed.

---

## Restore File

```bash
git restore zombiestory.md
```

Think:

> Reload last save.

Useful when you accidentally break something.

---

# Understanding HEAD

Example:

```text
HEAD -> main
```

HEAD is:

```text
★ You Are Here
```

Like a mall map.

It marks the commit you're currently viewing.

---

# Time Travel

---

## Travel to Previous Save Point

```bash
git checkout COMMIT_HASH
```

Example:

```bash
git checkout abc123
```

Think:

> Get in the DeLorean.

You are now viewing history.

---

## Return to Present

```bash
git switch main
```

Think:

> Return to the sacred timeline.

---

# Branches

---

## Why Branches Exist

Without branches:

```text
Main Timeline
     ↓
Risky Changes
     ↓
Everything Breaks
```

With branches:

```text
Main Timeline
      │
      └── Experiment Timeline
```

Safe place to test ideas.

---

## List Branches

```bash
git branch
```

Example:

```text
* main
  zombie-attack
```

The `*` means:

```text
You Are Here
```

---

## Create Branch

```bash
git branch zombie-attack
```

Think:

> Create alternate reality.

---

## Switch Branches

```bash
git switch zombie-attack
```

Think:

> Jump dimensions.

---

## Create and Switch

Common shortcut:

```bash
git switch -c zombie-attack
```

Think:

> Create dimension and immediately enter it.

---

# Merging

When your experiment worked.

Switch back:

```bash
git switch main
```

Merge:

```bash
git merge zombie-attack
```

Think:

```text
Timeline A
      +
Timeline B
      =
One Timeline
```

---

## Delete Branch

After merge:

```bash
git branch -d zombie-attack
```

Think:

> Close alternate reality.

---

# GitHub

## Git vs GitHub

### Git

Local time machine.

```text
Your Computer
```

### GitHub

Remote time machine.

```text
Cloud Backup
```

Think:

```text
Git = Save System

GitHub = Cloud Save
```

---

# .gitignore

Keep secrets out of GitHub.

Example:

```text
.env
node_modules
```

File:

```text
.gitignore
```

Think:

> Don't pack these items in the suitcase.

---

# Remote Repositories

---

## Add Remote

```bash
git remote add origin URL
```

Example:

```bash
git remote add origin https://github.com/user/repo.git
```

Think:

```text
origin = vacation house in Cabo
```

---

## View Remotes

```bash
git remote -v
```

Shows where GitHub lives.

---

# Uploading Changes

---

## First Push

```bash
git push -u origin main
```

Meaning:

```text
push   = upload
origin = remote GitHub repo
main   = branch
-u     = remember this connection
```

---

## Future Pushes

After first push:

```bash
git push
```

Think:

> Upload latest save file.

---

# Downloading Changes

---

## Clone Repository

```bash
git clone URL
```

Think:

> Download entire time machine.

---

## Pull Changes

```bash
git pull
```

Think:

> Sync with GitHub.

Downloads and merges latest changes.

---

## Fetch Changes

```bash
git fetch
```

Think:

> Dog fetches stick.

Git downloads information but does NOT merge it.

---

# GitHub Features

These are GitHub features, not Git features.

---

# Issues

Think:

```text
To-Do List
```

Examples:

- Add feature
- Fix bug
- Improve documentation

CLI Example:

```bash
gh issue create
gh issue list
```

---

# Pull Requests (PRs)

Think:

> Can we make this timeline official?

Process:

```text
Issue
  ↓
Branch
  ↓
Work
  ↓
Commit
  ↓
Push
  ↓
PR
  ↓
Review
  ↓
Merge
```

---

## Create PR

Example:

```bash
gh pr create
```

---

## View PR

```bash
gh pr view 3
```

---

## Checkout PR

```bash
gh pr checkout 3
```

Think:

> Let me inspect this alternate timeline.

---

## Merge PR

```bash
gh pr merge 3 --merge
```

Think:

> Make the alternate reality canon.

---

# Merge Conflicts

Happen when:

```text
You change Line 10

AND

Someone else changes Line 10
```

Git doesn't know which version wins.

You'll choose:

```text
Accept Current Change
Accept Incoming Change
Accept Both Changes
```

Think:

> Timeline Crime

Two realities collide.

Human intervention required.

---

# Revert

Undo bad merge.

GitHub provides:

```text
Revert
```

Button.

Think:

```text
Bad Merge
    ↓
Revert
    ↓
Timeline Fixed
```

---

# Agent Workflow (AI Coding)

Modern AI coding typically follows:

```text
Issue
  ↓
Create Branch
  ↓
AI Makes Changes
  ↓
Push Branch
  ↓
Create PR
  ↓
Review
  ↓
Merge
```

This is what tools like:

- Claude Code
- OpenCode
- Aider
- Cursor
- Windsurf
- Codex

are doing behind the scenes.

---

# Daily Git Commands

## Commands You'll Use Constantly

```bash
git status
git add .
git commit -m "message"
git push
git pull
git diff
git log --oneline
```

---

# Feature Development Flow

```bash
git switch -c feature-name

# work

git add .
git commit -m "feature complete"

git push
```

Then:

```text
Create PR
Review PR
Merge PR
Delete Branch
```

---

# Emergency Recovery Commands

Undo file changes:

```bash
git restore filename
```

View history:

```bash
git log --oneline
```

Travel to history:

```bash
git checkout COMMIT_HASH
```

Return to present:

```bash
git switch main
```

---

# The 4 Commands To Memorize First

If you learn nothing else:

```bash
git status

git add .

git commit -m "message"

git push
```

These cover roughly 80–90% of day-to-day Git usage.

---

# Final Mental Picture

```text
Git = Time Machine

Commit = Save Point

Main = Sacred Timeline

Branch = Alternate Reality

Checkout = Time Travel

Restore = Reload Save

Merge = Fuse Timelines

GitHub = Cloud Backup

PR = Request To Make
     A Timeline Canon
```

And the entire Git workflow:

```text
Edit Files
    ↓
git add .
    ↓
Stage Changes
    ↓
git commit
    ↓
Create Save Point
    ↓
git push
    ↓
Cloud Backup
```

That's Git.
# Other Git Topics

The main cheat sheet focuses on the Git fundamentals.

For practical workflows and modern development environments, see:

- [Git Desktop Reference](./git-desktop-reference.md)
- [Git with AI Agents](./git-with-ai-agents.md)
- [Git in VSCode](./git-in-vscode.md)
- [Git Collaboration](./git-collaboration.md)
- [Git Automation & CI/CD](./git-automation-ci-cd.md)
- [Git Branching Strategies](./git-branching-strategies.md)
- [Git Troubleshooting](./git-troubleshooting.md)
- [Git for Solo Developers](./git-for-solo-developers.md)
