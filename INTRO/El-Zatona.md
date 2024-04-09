# EL-Zatona

## What is Git ?
Git is a open-source distributed version control system for software development.

## What is version control?
A system that is like a database of references that stores all the change that occurred to the code.

## What is Local Version Control?
Stores all changes to files on your computer, making it difficult or impossible to recover them if any errors occur or files get lost.

## What is Centralized Version Control?
- There is a single central server that contains all the versioned files, and it only keeps track them.
- To make changes to the code, they first need to obtain a copy of the latest version from the central repository. They make their changes on their local machine and then submit them back to the central repository.
- It doesn't keep track on the versions on your devices or on the others making it very hard to merge and maintain.
- If the central repository is lost or damaged, it can be difficult or impossible to recover the code.

## What is Distributed Version Vontrol ?
A hyprid system between the previous systems. It allows you to have a copy of all the changes that have occurred throughout the project's lifetime and the codes on your computer. If anything happens to the original code, you can send your code and the history of changes that have occurred since the project started, as if nothing had happened.

### Repository:
It's the place or folder where Git stores the code and any changes that occur in it.

### Working Tree:
It's the current state of the directories and files on your local machine. You can make changes to any file in it.


### What are the states of a file in git?
- **Modified(untracked):** You have changed the file but have not committed it to your database yet.
- **Staged:** You have marked a modified file in its current version to go into your next commit snapshot.
- **Committed(Tracked):** Here, you've told Git to take these edits and make them in the repository. Git will record that at a specific time, someone edited the file, with a message explaining why they made this commit.
