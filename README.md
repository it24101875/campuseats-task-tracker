# CampusEats Task Tracker

A small team repository for **SE3090 Lab 08** (Git, collaborative development, CI/CD, security and code quality).

CampusEats developers use this tracker to practise the professional delivery workflow:

**branch → commit → pull request → review → merge**, with GitHub Issues for planning and GitHub Actions checking every change.

## Run locally

```bash
git clone https://github.com/it24101875/campuseats-task-tracker.git
cd campuseats-task-tracker
node src/tasks.js
```

## Branching strategy (GitHub Flow)

`main` is always deployable. Work happens on short-lived branches, then merges through a pull request:

| Branch name | Purpose |
| --- | --- |
| `feature/add-task-list` | new functionality |
| `chore/add-ci` | tooling / CI |
| `fix/code-quality-security` | quality and security fixes |

Commit messages follow Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`).

## CI

GitHub Actions (`.github/workflows/ci.yml`) runs on push and on pull requests into `main`. A failing check is intended to block a merge so broken changes never reach `main`.

## Security

- Never commit secrets (API keys, passwords, tokens).
- Store secrets in environment variables (for example `process.env.API_KEY`).
- Dependency risks are checked with `npm audit` and Dependabot alerts.
