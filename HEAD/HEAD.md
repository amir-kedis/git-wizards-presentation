# What is HEAD?

## Outline 
- What exactly is HEAD
- Using _git reflog_
- Recovering deleted branches
- Cherry-picking commits to merge

## Summary
### What is HEAD ? 

In your main branch, run
```bash
git log --oneline --graph 
```
You find HEAD pointing to your branch right on top. 
If you switch to another branch and do the same, you find HEAD there too. 

But if you run, 
```bash
git log --oneline --graph <branch-name> 
``` 
With branch-name being any branch other than the one you're currently in, you do not find HEAD in the result.

You get it now. Head is basically a pointer that points to wherever you're at. When you switch branches, it follows you. When you go through commit after commit, it follows you. 

Like everything, it's stored inside .git. 

```bash
cat .git/HEAD
```
This shows you what HEAD points to, as recorded inside .git.

### Git Reflog

**_FAQ:_**  Okay, that seems like a pretty basic concept. Why is it useful?

What makes it actually useful is that all of HEAD's movements throughout the lifetime of the repository are recorded. 

``` bash
git reflog
```

This command shows you the full record of HEAD's movements, every single one since _git init_. 

And the key lies in the SHAs that are written next to each movement, they indicate which commit HEAD pointed to. And as you know, the SHA enables us to access all of the commit's content by retracing it using the command you now know very well:

``` bash
git cat-file -p <SHA>
```

### Retracing and recovering

Imagine a scenario where you worked on a feature branch for some time, and you planned to merge it onto main, but some problem happened and your branch got deleted, all of it. 

Don't despair just yet, git has you covered!

By using _git reflog_ you can find the SHAs to all your commits, even the ones that were in the deleted branch. Now you can use the SHA to merge your commits onto main as you wish, or recover certain parts of the commits' content (through multiple rounds of _git cat-file -p_ ). 

To recover your lost commit, on your target branch, run

```bash
git merge <SHA of desired commit>
```
But as you may know, merging a commit onto a branch basically adds the entire commit's life history. What if you were working on a long lived branch, with many unmerged commits? A  merge could potentially cause a ton of merge conflicts. 

What if those conflicts got so complicated, that the only way out was to hand-pick certain edits to merge and discard the rest? Luckily, git provides this very handy command: 

```bash
git cherry-pick <SHA>
```

This trusty command allows you to merge that singular commit's changes, and ignore everything that came before it (even though previous changes are included in the commit and accessed through its SHA). 