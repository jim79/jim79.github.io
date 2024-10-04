---
title: "Working with Git branches"
categories : [Robotics Lab,Tutorials]
---

## Git Branches
Git branches are a core feature of the Git version control system. They allow multiple lines of development to exist within a single repository, enabling different features, bug fixes, and experiments to be worked on simultaneously without interfering with the main codebase.

## Working with Git branches
- View branches in a project \
```git branch -a```

- Create a new branch and move to it \
```git checkout -b branch name```

- Move to a branch \
```git checkout branch name```

- Merging changes made in a branch with main \
```git checkout main``` \
```git merge branch name``` \
```git add .``` \
```git commit -m "commit message"``` \
```git push``` 

- Delete a branch on remote repo \
```git push origin --delete branch name```

- Delete a branch with unmerged commits \
```git branch -D branch name```

- Delete a branch locally \
    - checkout to another branch \
```git branch --delete branch name```

- Display the commit history of a Git repository \
```git log --graph --oneline --decorate --all```

<!-- # This command is long, so shorten it using aliases
git config --global alias.lg 'log --graph --oneline --decorate --all' -->
