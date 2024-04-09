# Branches, merge & rebase

---

## branches

> [!cite] What is a branch and why ?
> Branching means you diverge from the main line of development and continue to do work without messing with that main line.

#### create a branch :

```bash
git branch <branch-name>
```

> [!attention] Attention :
> After you make a new branch, git doesn't checkout(move to) the new branch automatically.

#### switch to a branch :

```shell
git checkout <targetbranch>
```

- [I] You can use the `-b` option with checkout to create a branch and switch to it.

```shell
git checkout -b <branch-name>
```

> [!info] Info :
> Branches are virtually **`free`** just a SHA to a commit/tree.

---

### merge

> [!quote] what is a merge ?
> A merge is attempting to `combine` two histories together that have diverged at some point in the past. There is a common commit point between the two, this is referred to as the `best common ancestor`

#### merge have 2 different outcomes :

##### _1. Fast Forward_:

- [P] just update the pointer/reference `(no merge commits)`
  ![[fastforward-merge.excalidraw|600]]

##### 2. Divergence merge:

- [P] create a merge commit to combine 2 commits/histories have 2 parents
  ![[diverge-merge.excalidraw|600]]

#### how to merge :

```shell
git merge <source-branch>
```

- [i] target-branch is the currently checked-out branch
- [>] conflicts are discussed on the `going remote` section.

---

### rebase

> [!quote] what is a rebase ?
> git-rebase - `Reapply` commits on top of another base tip - _"the docs"_

![[rebase.excalidraw|600]]

#### how to rebase :

```shell
git rebase <target-branch>
```

> [!question] NOTE :
> Note the different perspective of merge's one.
> rebase alters your branch to be at the tip of `<targetbranch>`

#### How rebase actually works :

1. checkout the latest commit at `<target-branch>`
   - [I] think of `<target-branch>` as `main`
2. replay one commit at a time of the `<source-branch>`
   - [I] `<srouce-branch>` is often the feature branch.
3. update source branch ref to the latest commit made.

> [!danger] Be careful :
> Rebase alters history (notice: replay), so **don't ever rebase main or any other public shared branch**

---

### merge vs. rebase

- [I] **Merge**:
  - [u] doesn't alter history
  - [u] doesn't require `push force`
  - [u] works with private and public branches without problems
  - [d] makes annoying merge commits
- [I] **Rebase**:
  - [d] alters history
  - [d] requires `push force`
  - [i] works best with private branches only
  - [u] no annoying merge commits
  - [u] linear history which is easier to search

---

### workflows war

#### Merge flow :

- [P] just merge always
  - [M] merge back into main
  - [!] merge commits happen but we live with it

#### Rebase flow :

- [P] (rebase in private branches - FF merge in public branches)
  - [D] rebase main into your feature branch first
  - [M] then fast-forward merge into main

> [!important] Important :
> In simple cases the difference between the 2 options in
> practice is what option you use in the following list.
> but people seem to be really opinionated about this matter.
> anyway `rebase flow` is the best.

![[Pasted image 20240409144440.png|300]]

---
