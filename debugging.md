# Debugging Checklist (Git)

Run these in order when something is wrong:

git status     # current state
git branch     # current branch
git log        # commits exist?
git remote -v  # remote configured?
git config -l  # user name/email

## Questions to ask
- Am I in the right folder?
- Do I have a commit?
- Does the branch exist?
- Am I pushing to the right remote?

## Undoing a Bad Commit (Safe Way)

Scenario:
You made a commit that was wrong, but you want to undo it safely.

Steps:
1. View commit history
   git log --oneline

2. Revert the most recent commit
   git revert HEAD

What this does:
- Creates a NEW commit that undoes the bad one
- Does NOT delete history
- Safe even if changes were already pushed

Notes:
- Git may open an editor for the revert message
- Save and exit to continue