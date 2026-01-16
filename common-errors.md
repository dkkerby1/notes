# Common Git Errors

## src refspec main does not match any
Cause:
- No commits yet
- Branch does not exist

Fix:
git add .
git commit -m "Initial commit"
git branch -M main
git push -u origin main

---

## fatal: not a git repository
Cause:
- Not inside a repo

Fix:
cd into the correct folder
or
git init

## Stuck in Git editor (Vim)

Problem:
After running git commit or git revert, a strange screen opens and you can’t exit.

Cause:
Git opened Vim (default terminal editor).

Fix (save and exit):
Press Esc
Type :wq
Press Enter

Fix (exit without saving):
Press Esc
Type :q!
Press Enter

Prevention (use a normal editor):
git config --global core.editor "notepad"
OR
git config --global core.editor "code --wait"

---

## Editing the Wrong File or Directory

Problem:
A file was edited or created, but it showed up in the wrong project.

Cause:
You were in the wrong directory when running the command.

How to check before editing:
pwd     # shows current directory
ls      # shows files in current directory

Fix:
1. cd to the correct directory
2. Re-run the edit command

Lesson:
The terminal always acts on the CURRENT directory.


