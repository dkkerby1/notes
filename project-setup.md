# Creating a New Project (Git + Bash)

## 1. Create project folder
mkdir project-name
cd project-name

## 2. Initialize git
git init

## 3. Create initial files
touch README.md
touch .gitignore

## 4. Check git status
git status

## 5. Stage files
git add .

## 6. First commit
git commit -m "Initial commit"

## 7. Rename branch to main
git branch -M main

## 8. Create GitHub repo
- Create empty repo on GitHub
- Do NOT add README or license

## 9. Add remote (SSH)
git remote add origin git@github.com:USERNAME/project-name.git

## 10. Push
git push -u origin main