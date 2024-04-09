## Part 5. HEAD & Reflog

In git terminology, HEAD is a reference variable. It points to the tip of the current branch, i.e. the last commit on the current branch. It's stored inside .git/HEAD.

Git stores a full record of HEAD's movements through different commits and branches, which you can view by running _git reflog_.

This record does not get affected if a branch gets deleted. This means you can use it to recover commits that were on a deleted branch. Find the SHA of the commit you want to recover, and run _git merge <SHA>_.

But, as you may know, each commit stores the entire content of the repo, and when merging a particular commit, you may not want its entire history, as there may be changes you want to discard(that were part of previous commits).

You can avoid this using _git cherry-pick_. This command allows you to merge only the changes that were new and did not exist in previous commits, thereby ignoring its previous history.
