# Git with AI Agents

Modern coding agents use Git constantly.

Examples:

- Claude Code
- OpenCode
- Aider
- Cursor
- Windsurf
- Codex

## What Agents Should Do

```text
Issue
 ↓
Branch
 ↓
Code
 ↓
Commit
 ↓
Push
 ↓
Create PR
```

NOT:

```text
Code Directly On Main
```

---

# Golden Rule

Never let AI work directly on:

```text
main
master
production
```

Always use a branch.

---

# AI Safe Workflow

git switch -c feature-name

Let agent work.

Review changes:

git diff

Review commits:

git log --oneline

Push:

git push

Create PR

Merge

---

# Trust But Verify

AI writes code.

You approve code.

Never blindly merge.
