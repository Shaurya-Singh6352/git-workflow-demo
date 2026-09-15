# Git Workflow Demo — Write-up

## 1. Feature Branches & Pull Requests
Created branches off main, made small changes, and opened PRs for each.

- `feature/add-intro` — added an intro line to README
  ![PR add-intro](screenshots/pr-add-intro.png)

- `feature/update-title` — updated the README title
  (this branch caused the conflict below)

- `feature/add-notes` — added notes, later rebased onto main
  ![PR add-notes](screenshots/pr-add-notes.png)

## 2. Merge Conflict
Changed the same line (README title) on both `main` and `feature/update-title`.
Merging the branch into main triggered a conflict.

**Before resolving:**
![Conflict markers](screenshots/conflict-before.png)

**After resolving:**
![Resolved file](screenshots/conflict-after.png)

I resolved it by choosing the version I wanted to keep and removing the
`<<<<<<<`, `=======`, `>>>>>>>` markers, then committed the merge.

## 3. Rebase
Created `feature/add-notes` off an older main, then moved main forward
with a new commit. Ran `git rebase main` on the feature branch to replay
my commit on top of the latest main, instead of creating a merge commit.

![Rebase output](screenshots/rebase-success.png)

**What changed:** rebase rewrote my branch's commit so it sits on top of
main's latest commit, keeping history linear instead of adding an extra
merge commit like a regular merge would.