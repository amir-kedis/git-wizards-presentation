# Code for Part 5: HEAD

``` bash
# start on main branch
git log --oneline --graph 
git checkout <other-branch-name>
git log --oneline --graph

# inside .git/ directory
ls
cat .git/HEAD
cat .git/refs/HEADS/<main branch>

# view reflog and check out content
git reflog
git cat-file -p <SHA-of-last-commit>

# create new branch and commit
git checkout -b new-feature
echo "really important feature" > new-feature.md
git add .
git status
git commit -m "Add important feature!"

# delete branch
git checkout <main-branch> 
git branch -D new-feature 

# view content of lost commit
git reflog 
git cat-file -p <SHA-of-lost-commit>
git cat-file -p <SHA-of-tree>
git cat-file -p <SHA-of-blob>

# recover lost commit
git merge <SHA-of-lost-commit>

# or cherry-pick a particular commit
git cherry-pick <SHA-of-lost-commit>
```