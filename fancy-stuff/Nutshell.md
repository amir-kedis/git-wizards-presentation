### Outline  
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

[III] Tags & Releases

[IV] WorkTrees

[V] Workflows & GitHub Actions

---
# Editing
## Amend
> Goal: edit the last commit (don't create a new one)
```bash
# first make your edits, then stage them

# Then: to edit the last commit
# without changing its message
git commit --amend --no-edit

# to edit the message use
git commit --amend -m "your updated msg"
```
## Interactive rebase
> Goal: edit history (not just the last commit)
```bash
# to enter this mode:
git rebase -i HEAD~3

# to edit the last 3 commits (3 is just an example)
```
Then you will be prompted with an interface where you can reorder, delete, edit, squash, and more
### Reword
> Goal: Edit the commit message  

- Use the keyword `reword` before the SHA
- save and continue, then you will be prompted again to change the message of desired commit

### Reorder
> Goal: change order of past commits

- Use the keyword `pick` before the SHA 
- **NOTE: The shown commits are ordered top to bottom from oldest to newest**, just change the order of the given lines as you wish

### Squash
> Goal: Combine multiple commits into one
- Use the keyword `squash` or `fixup` before the SHA 
- `fixup` by default keeps the older commit's message, while `squash` re-prompts for a message.


# Deleting 

## Stash
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

## Revert & Reset

### Revert
> Goal: Undo the last commit.
```bash
git revert HEAD
```
**NOTE: automatically creates another commit.**