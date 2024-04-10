# Git remote summary

## What’s a remote?

remote is a **COPY OF THE MAIN REPO SOMEWHERE ELSE.**

That means that you can have a remote repo on your local machine.

## git vs github

**github is used with git for online backup.**

**To link your local repo with a remote one:**

```bash
**git init
git remote add <remote-name> <url>**
```

**or simply**

![Screenshot from 2024-04-08 14-14-31.png](Git%20remote%20summary%2011436a4cd66844f1b30760529f80812e/Screenshot_from_2024-04-08_14-14-31.png)

```bash
**git clone <uri> <folder-name>**
```

this will create a folder with git initialized in it

## git fetch

```bash
git fetch
```

**Here's what happens when you run** **`git fetch`**:

1. Git contacts the remote repository.
2. It retrieves any new commits, branches, or tags that exist on the remote repository but are not present in your local repository.
3. It updates your local repository's remote-tracking branches (e.g., **`origin/main`**) to reflect the state of the remote repository.

**However, the command does not:**

- Change the state of your current working branches.
- Merge any changes into your local branches.
- Modify any of your local files or commit history.

> **In summary:** fetch is used to update all of the remote tracking branches as they are not updated automatically
> 

<aside>
💡 you can then merge these changes using git merge

</aside>

## git pull

**To merge the remote changes into your local branches:**

```bash
**git pull <remote> <branch>**
```

<aside>
💡 git pull is a combination of git fetch and git merge

</aside>

## git push

It’s now the case that you want to upload your changes to the remote repo

```bash
**git push <remote> <branch>**
```

## merge conflicts

**merge conficts happen when making different changes to the same line of the same file, or when one person edits a file and another person deletes the same file (git cann’t automatically merge)**.

**This is how files with conflicts look like:**

```bash
<<<<<<< HEAD
Hello from local
=======
Hello from remote.
>>>>>>> 3481fb2d429347f009646b1456375e6685c1a36e
```

<<<<<<< HEAD
Hello from local
======= 

**Your version has these changes**

=======
Hello from remote.
>>>>>>> 3481fb2d429347f009646b1456375e6685c1a36e

**and the remote has these changes**

To resolve a merge conflict you either:

- accept your changes
- accept the remote changes
- combine both
- add completely new line