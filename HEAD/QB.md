# Question Bank

## Part 5. HEAD (by Khalid)

1. In git terminology, ..... is a reference variable that points to the tip of your current branch.

- A) refs
- B) HEAD
- C) checkout
- D) config

>Answer: B
---

2. The command ..... allows you to view the history of HEAD's movements through different branches and commits.

- A) git config --get-regexp branches
- B) git revert
- C) git pull --rebase
- D) git reflog
  
> Answer: D
---

3. Git reflog allows you to view HEAD's past movements through commits, and you are able to identify each commit because git reflog lists its .....

- A) Timestamp
- B) Parent
- C) SHA
- D) None

> Answer: C
---

4. Knowing a particular commit's SHA allows you to merge it onto a branch, revert it or reset it.

- A) True
- B) False

> Answer: A
---

5. Git cherry-pick allows you to merge a commit onto a branch, including all of that commit's history.

- A) True
- B) False

> Answer: B
---

6. You can merge a particular commit onto your branch by running this command.

- A) git merge \<commit-SHA>
- B) git merge \<branch-name>
- C) git merge origin/\<branch-name>
- D) git merge \<branch-SHA>

> Answer: A
---

7. If you have been working on a feature branch for a long time, and had trouble merging it onto your project's main branch, you can use ..... to select a particular set of changes and additions to merge and ignore the rest (that are causing merge conflicts).

- A) git merge \<SHA-of-desired-commit>
- B) git cherry-pick \<SHA-of-desired-commit>
- C) git revert \<SHA-of-desired-commit>
- D) git commit -m "yes"

> Answer: B
