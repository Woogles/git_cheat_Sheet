# Git Branching Strategies

## Solo Developer

Simple:

```text
main
 └─ feature
```

---

## Small Team

```text
main
 ├─ feature-login
 ├─ feature-api
 └─ bugfix-auth
```

---

## AI-Assisted Development

```text
main
 ├─ ai-login
 ├─ ai-dashboard
 └─ ai-reporting
```

Each AI task gets its own branch.

This avoids timeline crimes.
