# Git Internals

## Section 1: How Git Is Stateless

Git is stateless it doesn't know where it it.Everytime you run a git command it. It goes and search for .git folder in the 
folder and it parents

-- animation of a cat chasing .git -- 

## Section 2: 

So what is inside a .git folder? 
This actually is a silly question because trivially it contains all the state but the question now is how the state is stored. Is it just stroing diffs between the current and previous commit? If so, how is the diff encoded? Or is it an entire snapshot of the repo stored each time

let's rewind a moment and investigate

-- Detective Animation --

## Section 3

Let's use git log to show our commits
you see each commit comes with a sha (just a hash)
actually git can infer the sha from just the first seven character
let's dig in the .git folder and find how the commits are stored

Spoiler:
Commits exist in the .git/objects directory with the first 2 letters as a directory, and the remaining 38 as a file.

let's then cat the file and see what is in it

Spoiler:
Bunch of crap / that is becuase it is compressed 
you can lookup the src code and try to reverse the algorithm or you can just use ```git cat-file -p```

let's try to use it with the hash we have

so the commit file contains what

-meta data 
other hashes (which are stored in the .git folder by the way)

let's try to use it with the other stuff

- parent -> just the parent commit (useless)
- tree -> this is the entire repo (wowww)

git stores complete version of the entire source at the point of each commit


## Section 4

let's talk about the contents

blobs (binary large objects)
why not just simply files there is a difference actually
files = blobs + metadata

trees are simply the equivelant of directories

so now we know that commit is a snapshot of the working tree.

## Section 5

so let's use these knowledge to try to understand advanced concepts

a branch for example -> you might think that a branch have to store all the commits that are in the branch.
you might need to rethink this idea you know that a commit keeps a pointer to the parent so you only need the branch to track one commit
the newest commit in this branch (ta-da)

so a branch is just a fancy terminology and it is just a named refrence

## Section 6

HEAD what is Head
git uses head to know which branch we are on 
so you guessed what a head is?
it points to a branch which itself points to a commit so it is the same


 


