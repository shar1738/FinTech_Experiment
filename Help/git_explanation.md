VIDEO LINK — [Great explanation of everything Git does](https://www.youtube.com/watch?v=Ala6PHlYjmw)

DOCUMENTATION — [Git official docs](https://git-scm.com/docs)

---

# Git — Condensed Cheat Sheet

---

## 1. Commit — Snapshot of the Project

A commit is a complete snapshot of every file at one moment.
Contains: snapshot pointer, metadata (author/date/message), pointer to parent commit(s). Commits form a history chain.

| Command | Description |
|---------|-------------|
| `git add <file>` | Stage changes |
| `git commit -m "message"` | Create a commit from staging area |
| `git commit --amend -m "..."` | Change the most recent commit (rewrite) |
| `git log --oneline` | View commit history |

---

## 2. DAG — Project History Graph

Commits are nodes in a Directed Acyclic Graph: each commit points to parents (never cycles). Branches, merges, and parallel work are reflected in this graph.

| Command | Description |
|---------|-------------|
| `git log --graph --oneline --all` | Visualize the DAG |
| `git show <commit>` | Inspect a commit snapshot |

---

## 3. Branches — Lightweight Pointers

A branch is a pointer to a commit hash. Creating a branch is instant because you're only making a pointer, not copying files.

| Command | Description |
|---------|-------------|
| `git branch` | List local branches |
| `git branch <name>` | Create a branch (pointer) |
| `git checkout -b <name>` | Create + switch to a branch |
| `git branch -d <name>` | Delete branch (safe) |
| `git push origin <name>` | Push branch to remote |

---

## 4. HEAD — Where You Are Now

HEAD points to a branch which points to a commit. Checkout a raw commit hash → detached HEAD.

| Command | Description |
|---------|-------------|
| `git status` | Shows current branch (HEAD) |
| `git checkout <branch>` | Move HEAD to a branch |
| `git checkout <commit-hash>` | Detached HEAD (read-only view) |

---

## 5. Staging Area — Git's Waiting Room

Three areas:
1. Working directory (files on disk)
2. Staging area (what will be committed)
3. Repository (commits)

| Command | Description |
|---------|-------------|
| `git status` | See working vs staged changes |
| `git add <file>` | Stage a file |
| `git restore --staged <file>` | Unstage a file |
| `git diff` | Unstaged diffs (working vs index) |
| `git diff --staged` | Staged diffs (index vs HEAD) |

---

## 6. Checkout vs Reset vs Revert

- **checkout**: moves your view (HEAD). Non-destructive.
- **reset**: moves a branch pointer (can rewrite local history)
  - `--soft`: branch moves, staging + working stay
  - `--mixed`: branch moves, staging resets, working unchanged (default)
  - `--hard`: branch + staging + working reset (dangerous)
- **revert**: creates a new commit that undoes an earlier commit (safe for shared history)

| Command | Description |
|---------|-------------|
| `git checkout <branch>` | Checkout (safe) |
| `git checkout <commit-hash>` | Checkout (safe) |
| `git reset --soft <commit>` | Reset (branch moves, staging + working stay) |
| `git reset --mixed <commit>` | Reset (branch moves, staging resets) |
| `git reset --hard <commit>` | Reset (branch + staging + working reset - dangerous) |
| `git revert <commit>` | Revert (create new commit that undoes an old one) |

---

## 7. Rebase — Replay Commits

Takes commits from your branch, calculates changes, and creates new commits with different parents → new hashes. Use locally to keep history linear.

| Command | Description |
|---------|-------------|
| `git checkout feature` | Switch to feature branch |
| `git fetch origin` | Fetch latest from remote |
| `git rebase origin/main` | Move feature branch on top of latest main |
| `git rebase -i <base-commit>` | Interactive rebase to edit/squash commits |
| `git push --force-with-lease origin feature` | After rebasing, update remote safely |

---

## 8. Merge — Join Histories

Merging records true parallel history by creating a merge commit.

| Command | Description |
|---------|-------------|
| `git checkout main` | Switch to main branch |
| `git merge feature` | Merge feature into main |
| `git merge --no-ff feature` | Force a merge commit even if fast-forward |

---

## 9. Reflog — Your Safety Net

Shows where HEAD has pointed recently. Lost/orphaned commits are recoverable by creating a branch pointing to the hash.

| Command | Description |
|---------|-------------|
| `git reflog` | Show recent HEAD movements |
| `git checkout -b recover <hash>` | Create a branch at the lost commit |
| `git branch restore <name> <hash>` | Alternative: create branch at hash |

---

## 10. Quick Practical Reminders

| Command | Description |
|---------|-------------|
| `git status` | Check status |
| `git add -A` | Stage all changes |
| `git commit -m "short message"` | Commit all staged changes |
| `git pull --rebase origin main` | Update local branch cleanly |
| `git push origin HEAD` | Push current branch |
| `git log --graph --decorate --all` | Full history visualization |

---

## One-Line Philosophy

- **Commits** = full snapshots; history = a graph of pointers
- **Branches & HEAD** = pointers/labels — cheap and fast
- **checkout** = look around
- **reset** = change local pointers (dangerous)
- **revert** = undo publicly
- **rebase** = rewrite local history cleanly
- **reflog** = recover lost pointers
