VIDEO LINK (https://www.youtube.com/watch?v=Ala6PHlYjmw) -Great explannation of everything git does

GIT DOCUMENTATION (https://git-scm.com/docs) -Has all info

Git — Condensed cheat-sheet (explanations + commands) - Written by ChatGPT-5 Mini using a transcript from video listed above

Below is a tight summary of each concept from the transcript followed immediately by the practical commands you’ll use.

1) Commit — snapshot of the whole project

A commit is a complete snapshot of every file at one moment. It contains: a snapshot pointer, metadata (author/date/message), and a pointer to its parent commit(s). Commits form a history chain.

Commands:

git add <file>               # stage changes
git commit -m "message"      # create a commit from staging area
git commit --amend -m "..."  # change the most recent commit (rewrite)
git log --oneline            # view commit history

2) DAG (Directed Acyclic Graph) — the project history graph

Commits are nodes in a DAG: each commit points to parents (never cycles). Branches, merges, and parallel work are reflected in this graph.

Commands:

git log --graph --oneline --all    # visualize the DAG
git show <commit>                  # inspect a commit snapshot

3) Branches — lightweight pointers (sticky notes)

A branch is just a pointer (a tiny file) that names a commit hash. Creating a branch is instant because you’re only making a pointer, not copying files.

Commands:

git branch                      # list local branches
git branch <name>               # create a branch (pointer)
git checkout -b <name>          # create + switch to a branch
git branch -d <name>            # delete branch (safe)
git push origin <name>          # push branch to remote

4) HEAD — where you are pointing now

HEAD is a pointer that usually points to a branch which points to a commit. If you checkout a raw commit hash, HEAD points directly to that commit — a detached HEAD.

Commands:

git status                      # shows current branch (HEAD)
git checkout <branch>           # move HEAD to a branch
git checkout <commit-hash>      # detached HEAD (read-only view)

5) Staging area (index) — Git’s waiting room

Three areas: working directory (files on disk), staging area (what will be committed), repository (commits). git add moves changes to staging; git commit writes staged state into a commit.

Commands:

git status                      # see working vs staged changes
git add <file>                  # stage a file
git restore --staged <file>     # unstage a file
git diff                        # unstaged diffs (working vs index)
git diff --staged               # staged diffs (index vs HEAD)

6) Checkout vs Reset vs Revert — different ways to “undo”

checkout: moves your view (HEAD). Non-destructive; used to switch branches or inspect commits.

reset: moves a branch pointer (can rewrite local history) and has three modes:

--soft: move branch only (staging + working stay).

--mixed (default): move branch + reset staging (working unchanged).

--hard: move branch + reset staging + working (dangerous — discards uncommitted changes).

revert: does not rewrite history — it creates a new commit that undoes an earlier commit. Safe for shared history.

Commands:

# Checkout (safe)
git checkout <branch>
git checkout <commit-hash>

# Reset (rewrites branch pointer — use with care)
git reset --soft <commit>
git reset --mixed <commit>    # same as: git reset <commit>
git reset --hard <commit>

# Revert (create new commit that undoes an old one)
git revert <commit>

7) Rebase — “replay” commits (rewrites history)

Rebase takes commits from your branch, computes their changes, and creates new commits with different parents (new hashes). This rewrites history — don’t rebase commits that others have based work on. Use rebase locally to keep history linear.

Commands:

# Move feature branch on top of latest main
git checkout feature
git fetch origin
git rebase origin/main

# Interactive rebase to edit/squash commits
git rebase -i <base-commit>

# After rebasing a branch you pushed, update remote safely:
git push --force-with-lease origin feature

8) Merge — join histories (creates commit with two parents)

Merging records the true parallel history by creating a merge commit that has two (or more) parents.

Commands:

git checkout main
git merge feature
# or for fast-forward merges when possible:
git merge --no-ff feature

9) Reflog — your safety net (recent HEAD movements)

git reflog shows where HEAD has pointed recently (checkouts, commits, resets). Lost/orphaned commits are often recoverable by finding the hash in the reflog and creating a branch pointing to it.

Commands:

git reflog                       # show recent HEAD movements
git checkout -b recover <hash>   # create a branch at the lost commit
git branch restore <name> <hash> # alternative: create branch at hash

10) Quick practical reminders / cheat lines
git status
git add -A
git commit -m "short message"
git pull --rebase origin main    # update local branch cleanly
git push origin HEAD             # push current branch
git log --graph --decorate --all

One-line philosophy (so you actually understand it)

Commits = full snapshots; the history is a graph of pointers.

Branches & HEAD = pointers/labels — cheap and fast.

Use checkout to look around, reset to change local pointers (dangerous), revert to undo publicly, rebase to rewrite local history for cleanliness, and reflog to recover lost pointers.
