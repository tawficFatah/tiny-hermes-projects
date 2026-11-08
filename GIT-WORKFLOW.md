# Keeping WSL and the VPS in sync

This project can be checked out in WSL and on the VPS where Hermes runs. GitHub is the shared remote. Run these commands from the repository root in each checkout. If you cloned to the suggested location, enter it with `cd ~/projects/tiny-hermes-projects`.

## Check what each checkout has

Run on both machines:

```bash
git status --short --branch
git remote get-url origin
git rev-parse HEAD
```

Check that both use the intended branch and GitHub repository. Matching commit hashes mean both checkouts are at the same committed revision. Read the status output separately to spot modified or untracked files. Those files can differ even when the hashes match.

To compare your current commit with what GitHub has on `main`, run:

```bash
git ls-remote origin refs/heads/main
```

Compare the returned hash with `git rev-parse HEAD`. The `origin/main` shown by `git status` is a locally stored reference. Fetching refreshes it, while `git ls-remote` asks GitHub directly.

## Publish on one machine, then pull on the other

On the machine where you edited the exercise, stage the specific files you want to publish. For example:

```bash
git add exercises/beginner/H02-the-file-clerk.md solutions/beginner/H02-the-file-clerk-solution.md
git diff --cached
git commit -m "Revise H02 instructions and solution"
git push
```

On the other machine, run `git status --short --branch` first. If the working tree is clean, pull the committed changes:

```bash
git pull --ff-only
git rev-parse HEAD
```

`--ff-only` updates the branch when it can move directly to the newer commit. If both checkouts have separate commits, it stops so you can review the divergence.

## If the checkouts disagree

- **A pull says “Already up to date,” but the hashes differ.** Confirm both branch names and remote URLs, then compare `git ls-remote origin refs/heads/main` on each machine. If GitHub shows the newer commit and your branch is `main`, explicitly refresh that branch with `git fetch origin refs/heads/main:refs/remotes/origin/main`, then run `git merge --ff-only origin/main`.
- **You have edits to tracked files.** Commit them if ready, or stash them with `git stash push -m "Exercise edits" -- path/to/file.md`. Pull, then run `git stash pop` once the pull succeeds. If Git reports a conflict, review the affected files before retrying.
- **An untracked practice file blocks a pull.** Move the file to a backup folder outside the repo, then pull. Compare your backup with the incoming version afterward. A stash of tracked edits leaves untracked files in place.

To check exactly which practice files are already in the current commit, run:

```bash
git ls-tree -r --name-only HEAD -- practice/
```

Review what you stage so practice output, personal observations, and setup credentials stay out of exercise commits unless you explicitly intend to share the relevant material.
