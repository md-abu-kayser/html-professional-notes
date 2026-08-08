# Version Control Basics

## Overview

Git tracks every change to your HTML, CSS, and assets over time, and is how this entire repository — and virtually every real project — is built and shared. This lesson covers the core loop you'll use constantly.

## Why It Matters

Without version control, "undo" only goes back one step, and there's no safe way to try a redesign without risking the working version. Git also underpins the deployment workflow used in [14-real-world-projects](../14-real-world-projects/README.md) (push to GitHub → auto-deploy).

## Core Concepts

### The daily loop

```bash
git init                        # start tracking a new project
git status                       # see what's changed
git add index.html                 # stage a specific file
git add .                            # stage everything changed
git commit -m "Add hero section"       # save a snapshot with a message
```

### Working with a remote (GitHub)

```bash
git remote add origin https://github.com/md-abu-kayser/html-professional-notes.git
git push -u origin main
git pull                       # fetch and merge remote changes
git clone https://github.com/md-abu-kayser/html-professional-notes.git   # copy an existing repo
```

### `.gitignore` for a front-end project

```text
node_modules/
dist/
.DS_Store
```

### Commit conventions

This repo uses [Conventional Commits](https://www.conventionalcommits.org/):

```text
feat: add responsive navbar snippet
fix: correct heading order in blog template
docs: expand accessibility lesson with ARIA examples
```

## Common Pitfalls

- Committing `node_modules/` because `.gitignore` wasn't set up first — bloats the repo enormously.
- Vague commit messages ("update stuff") that make history useless later.
- Working directly on `main` for every change instead of using feature branches for anything non-trivial.

## Key Takeaways

- The daily loop is `status` → `add` → `commit`; `push`/`pull` sync with a remote like GitHub.
- Set up `.gitignore` before the first commit, especially for `node_modules/`.
- Clear, conventional commit messages are documentation for future-you.
- GitHub is also how static sites typically get deployed — see the deployment step in [14-real-world-projects/01-personal-portfolio](../14-real-world-projects/01-personal-portfolio/README.md).
