# El Zatoona
### outline
[I] Editing  
1. Amend    
2. Interactive rebase  
    2.1 Reword  
    2.2 Reorder  
    2.3 Squash   
    
[II] Deleting  
1. Stash    
2. Revert    
3. Reset  

[III] Tags    
[IV] Releases   
[V] WorkTrees  
[VI] Workflows & GitHub Actions

---

# [I] Editing

## 1. Amend
> Goal: edit the last commit (don't create a new one) 🛠️
```bash
# first make your edits, then stage them

# Then: to edit the last commit
# without changing its message
git commit --amend --no-edit

# to edit the message use
git commit --amend -m "your updated msg"
```
## 2. Interactive rebase
> Goal: rewrite history ✍🏼 🚧  (not just the last commit)
```bash
# to enter this mode:
git rebase -i HEAD~3

# to edit the last 3 commits (3 is just an example)
```
Then you will be prompted with an interface where you can reorder, delete, edit, squash, and more
### 2.1 Reword 
> Goal: Edit the commit message   ✍🏼

- Use the keyword `reword` before the SHA
- save and continue, then you will be prompted again to change the message of desired commit

### 2.2 Reorder
> Goal: change order of past commits 📝

- Use the keyword `pick` before the SHA 
- **NOTE: The shown commits are ordered top to bottom from oldest to newest**, just change the order of the given lines as you wish

### 2.3 Squash
> Goal: Combine multiple commits into one 📚
- Use the keyword `squash` or `fixup` before the SHA 
- `fixup` by default keeps the older commit's message, while `squash` re-prompts for a message.


# [II] Deleting 

## 1. Stash
> Goal: save my current changes away from the wokring tree (files) 

```bash
# make some shanges, then
git stash -m "quick draft"
# message is optional
```
**NOTE: Stashed changes are removed form the working tree**

- `git stash pop` to pull the changes back to the current working tree (files)
- `git stash drop` to delete one entry
- `git stash clear` to clear the whole stash history

## 2. Revert
> Goal: Undo the last commit.  ↩️

`git revert HEAD`

**NOTE: automatically creates another commit.**

## 3. Reset
> Goal: Delete commits, restore previous version ⏪
- `git reset --hard HEAD~1` deletes the last commit and and its changes from the current working tree
- `git reset --soft HEAD~1` deletes the last commit, but leaves the working tree as it is.

- The Working Tree in Git is a directory (and its files and subdirectories) on your file system that is associated with a repository.

# [III] Tags
> Goal: Mark a point in history 🚩 

Tags are ref's that point to specific points in Git history. Tagging is generally used to capture a point in history that is used for a marked version release (i.e. v1. 0.1). A tag is like a branch that doesn't change. Unlike branches, tags, after being created, have no further history of commits.

- To list all tags `git tag`
- To add a tag `git tag -a v1.2`

# [IV] Releases
> Goal: share a downloadable version of my work

A Release is created from an existing tag and exposes release notes and links to download the software or source code from GitHub.

**NOTE: GitHub Releases must be created from existing tags**  
**GitHub Releases are based on tags**

# [V] Worktrees
> Goal: Being able to checkout multiple branches at the same time. each in a different folder.

Instead of using multiple clones, or unintended commits / stashes before checking out to another branch.

# [VI] Workflows and GitHub Actions
> Goal: Automate building, testing, deployment  

configure automatic actions that are executed when something happens to your repo   
something like a new commit / push or a new pull request