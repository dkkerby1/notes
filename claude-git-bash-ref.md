Git & Bash Reference
BASH - NAVIGATION & FILES
pwd - shows current directory path
ls - lists files/folders in current directory
-a all files including hidden
-l detailed list with permissions/size
-lh human-readable file sizes
cd <path> - change directory
cd .. up one level
cd ~ home directory
cd - previous directory
mkdir <name> - create directory
-p create nested directories
touch <file> - create empty file or update timestamp
cp <source> <dest> - copy file
-r copy directory recursively
mv <source> <dest> - move or rename file/folder
rm <file> - delete file
-r delete directory recursively
-f force delete without confirmation
-rf force delete directory (dangerous)
cat <file> - display file contents
less <file> - view file with scrolling (q to quit)
head <file> - first 10 lines
-n 5 first 5 lines
tail <file> - last 10 lines
-n 5 last 5 lines
find <path> -name "<pattern>" - search for files
grep "<pattern>" <file> - search inside files
-r recursive search in directories
-i case-insensitive
BASH - SYSTEM & PROCESS
clear - clear terminal screen
history - show command history
man <command> - manual/help for command
which <command> - shows path to command
echo $PATH - shows directories in PATH
chmod <permissions> <file> - change file permissions
chmod +x <file> make executable
chmod 755 <file> rwx for owner, rx for others
ps - show running processes
ps aux detailed process list
kill <pid> - terminate process by ID
df -h - disk space usage
du -sh <dir> - directory size
top - live process monitor (q to quit)
GIT - LOCAL WORKFLOW
git init - create new git repo in current directory
git status - shows changed files, staging area, branch
git add <file> - stage file for commit
git add . stage all changes
git add -A stage all including deletions
git commit -m "message" - commit staged changes
-am "message" stage and commit tracked files in one step
git branch - list branches (* shows current)
git branch <name> create new branch
git branch -d <name> delete branch (safe)
git branch -D <name> force delete branch
git checkout <branch> - switch to branch
git checkout -b <name> create and switch to new branch
git switch <branch> - newer way to switch branches
git switch -c <name> create and switch
git merge <branch> - merge branch into current branch
git stash - temporarily save uncommitted changes
git stash pop apply and remove most recent stash
git stash list show all stashes
git stash apply apply stash but keep it
GIT - REMOTE WORKFLOW
git clone <url> - copy remote repo to local machine
git remote -v - show remote repositories
git remote add origin <url> - link local repo to remote
git push origin <branch> - upload commits to remote
git push -u origin <branch> set upstream and push
-f force push (dangerous, overwrites remote)
git pull origin <branch> - download and merge remote changes
git fetch - download remote changes without merging
GIT - INFORMATION & INSPECTION
git log - show commit history
--oneline condensed one-line format
--graph visual branch graph
-n 5 last 5 commits
git diff - show unstaged changes
git diff --staged show staged changes
git diff <branch> compare current branch to another
git show <commit> - show commit details
git blame <file> - show who changed each line
GIT - UNDOING MISTAKES
git restore <file> - discard changes in working directory
git restore --staged <file> unstage file (keep changes)
git reset <file> - unstage file (older command)
git reset --soft HEAD~1 - undo last commit, keep changes staged
git reset --hard HEAD~1 - undo last commit, delete changes (dangerous)
git revert <commit> - create new commit that undoes a previous commit
git clean -fd - delete untracked files and directories
COMMON ERRORS & FIXES
"fatal: not a git repository"

You're not in a git repo. Run git init or cd into one.

"error: failed to push some refs"

Remote has changes you don't have locally. Run git pull first, then push.

"Your branch is behind"

Remote is ahead. Run git pull to sync.

Merge conflict

Open conflicted files, look for <<<<<<<, =======, >>>>>>> markers.
Edit to resolve, remove markers, then git add <file> and git commit.

Accidentally committed to wrong branch

git log to find commit hash
git checkout <correct-branch>
git cherry-pick <hash>
git checkout <wrong-branch>
git reset --hard HEAD~1

Pushed sensitive data

Delete locally, commit, push. But history still has it.
Use git filter-branch or BFG Repo-Cleaner (advanced).
Consider repo compromised if credentials were exposed.

Detached HEAD state

You checked out a commit directly instead of a branch.
Create branch: git checkout -b <new-branch-name>
Or return: git checkout <branch-name>

PROJECT SETUP PATTERNS
New project from scratch:
bashmkdir project-name
cd project-name
git init
touch README.md .gitignore
git add .
git commit -m "Initial commit"
# Create repo on GitHub, then:
git remote add origin <url>
git push -u origin main
Clone existing project:
bashgit clone <url>
cd project-name
# Make changes
git add .
git commit -m "description"
git push
Feature branch workflow:
bashgit checkout -b feature-name
# Make changes
git add .
git commit -m "description"
git push -u origin feature-name
# On GitHub: create pull request
# After merge:
git checkout main
git pull
git branch -d feature-name
.GITIGNORE ESSENTIALS
Common patterns to ignore:
# OS files
.DS_Store
Thumbs.db

# Python
__pycache__/
*.pyc
venv/
.env

# Node
node_modules/
.npm

# Logs
*.log

# IDE
.vscode/
.idea/