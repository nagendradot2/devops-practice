# Git Rebase Feature Branch

## Objective
Rebase feature branch with master without creating merge commits

## Steps

1. Checkout feature branch
git checkout feature

2. Fetch latest changes
git fetch origin

3. Rebase with master
git rebase origin/master

4. Resolve conflicts (if any)
git add .
git rebase --continue

5. Push changes
git push origin feature --force

## Key Learnings
- Rebase keeps history clean
- No merge commits created
- Force push required after rebase
