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
you find HEAD right on top. If you switch to another branch and do the same, you find HEAD there too. But if you run 
```bash
git log --oneline --graph <branch-name> 
``` 
where branch-name is the name of any branch other than the one you're currently in, you do not find HEAD in the result.

You get it now. Head is basically a pointer that points to wherever you're at. When you switch branches, it follows you. When you go through commit after commit, it follows you.

Okay, that seems like a pretty basic concept. Why is it useful?

What makes it actually useful is that all its movements through commits are recorded, each with their respective SHAs. 

``` bash
git reflog
```

This is what enables us to recover certain commits even if their branches were deleted. As you know, the SHA enables us to access all of the commit's content, just by retracing it.