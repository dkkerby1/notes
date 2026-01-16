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