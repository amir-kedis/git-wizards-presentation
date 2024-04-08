>  This is still an unfinished draft 

7. Bullets of fancy git commands: `George`
    - interactive (reword - squash - reorder) commits 
    - stash
    - revert vs reset - where is the fun
    - tags and releases
8. tools, more to look for, refs `George`
    - lazygit
    - GitHub actions
    - (git worktrees, git workflows, git actions)
    - thank you


> Part {A} Fancy Git commands
1. [done] commit --amend
2. [done] interactive rebase (reword - squash - reorder) commits
3. [done] stash
4. [done] revert vs reset - where is the fun
5. [done] tags and releases
> Part {B} Extras and final notes
6. lazygit
7. GitHub actions
8. (git worktrees, git workflows, git actions)


[YouTube Playlist - Great source](https://youtube.com/playlist?list=PLfU9XN7w4tFzW200TaCP1W9RTE8jRSHU5&si=l7Rlfs2JWvgHhnb-)

### Types of actions
- Saving changes: commit, diff, stash, .gitignore
- Undoing changes: revert, reset
- Rewriting History: rebase, reflog

# {A} Fancy Git Commands

## {1} `git commit --amend `
_something like editing the last message in whatsapp_ <br>
sometimes you make a minor mistake in the last commit, (last commit only) <br>
something like forgetting to add a file or an immediate mistake<br>
so instead of making another commit with message _"minor edit"_ or _"fix typo"_ <br>
USE git commit --amend <br>
amend means adjust / modify

```bash
git commit --amend -m "updated commit message"
# this simply takes the currently staged changes (if any) and put it in the last commmit,
# and updates its message
```
OR
```bash
git commit --amend --no-edit
# this simply takes the currently staged changes and put it in the last commmit
# leaving the message as it is
```
<a href="https://www.atlassian.com/git/tutorials/rewriting-history#:~:text=Changing%20the%20Last%20Commit%3A%20git,creating%20an%20entirely%20new%20commit.">Good Resource</a>


## {2} `git rebase -i `
### What if I want a commit that is further back ?
### {2.1} Reword
example: 
` git rebase -i HEAD~2 ` <br>
means I want to work on the last 2 commits <br>
this will open vim or nano. allowing you to do a lot of stuff, of which is "reword" <br>
type "reword" instead of pick in front of the commit that you want to change its message. <br>
` Esc  :  W  Q` in vim or `^S ^X` in nano<br> 
when you hit enter, you get directed to another window to edit the commit message that you intended

<img src="rebase_show.png">


### {2.2} Reorder
_refer to the image_ <br>
Just change the order in which they appear (top is the current oldest) 

### {2.3} Squash (combine commits)
_refer to the image_ <br>
Simply combining multiple commits into one
#### Squash vs Fixup
The difference is in the commit message, anyways the commit bodies are combined

