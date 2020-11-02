### What is git?

- Git is hight level file system built on top of native file system. It was written by Linus Torvalds. It is versioned file system, a content tracker. It is a persistent map at its core and layered on top of it, a content tracker that looks a lot like versioned file system.

### How it works?

- With every change in file git calculates SHA-1 (hash) of file and stores its content in file as a blob in folder `\.git\objects`. Hash(SHA-1) value is same for all OS. For example, I commit a file. Git calculates a hash of that file for example - f825dcc465e7e1f54a09a27951c82b548795ed. It creates folder with first two letters of hash in `object` folder `(f8)` and creates a sub folder inside it with remaining value of hash `25dcc465e7e1f54a09a27951c82b548795ed`. To view the content of file and use plumbing commands. Also version of folders are tracked and stored in same way as above but the content is different. It contains 2 more attribues along with commit detaiks, `tree` and `parent`. 

https://github.com/rns1992/git-commands/blob/master/images/object_model.jpg?raw=true

### What is branch?

- A pointer to reference of a commit. Information for reference which branch is pointing is stored in `ref/head/{branchname}`. It contains just one line, a SHA-1 of commit.

### How git knows which is current branch?

- Inside .git folder there is a file name `HEAD` which contains location of file with branch name. eg: `ref: refs/heads/master`. HEAD is a reference to a branch.

### What does checkout mean?

- Move Head to branch commit reference and update ref in HEAD.

### How merging works?

- When a beanch is merged the a new commit is created that has 2 parent commit reference in its content file. One for current branch and second for the branch which needs to be merged.

### How git manages working directory?

- The object in the database are commits, trees and blobs. All the objects are arranged in a graph as a reference channel. There are references from commits -> trees, trees -> blobs. When we checkout git is just concerned about commits, trees and blobs related to that reference. 

### What is FAST-FORWARD commit?

- I have merged feature branch to master branch and a new commit is created. So, master branch is one commit ahead of feature branch. Now if I merge master branch to feature branch the it will not create a new commit, it will simply move the pointer of feature branch to master branch as its head. So ultimately master and feature branch will point to a same commit hash.

### What is Detached HEAD state?

- When I checkout a specific commit instead of branch then in `ref/HEAD` localtion there would not be any reference to location of branch file, instead it would having a commit reference in HEAD file which is not pointing to any branch. Later, I perform some 2 commits in DETACHED HEAD. Now if I switch to master from deached HEAD then the  2 commits would be lost. I would be same a object left with no reference in OOP languages. Ultimately it will be garbage collected by git at some point of time and those commit files would be removed. If I dont want to get those commits lost then I need to create branch from that commit, so it would not be lost.

### What is Rebase in Git?

Rebasing is the process of moving or combining a sequence of commits to a new base commit. It integrates all new changes from current branch and adds on top of another branch. From a content perspective, rebasing is changing the base of your branch from one commit to another making it appear as if you'd created your branch from a different commit. Internally, Git accomplishes this by creating new commits and applying them to the specified base. It's very important to understand that even though the branch looks the same, it's composed of entirely new commits. `Git detaches the current branch from its base and moves it to the top of target branch`.

### How rebase works?

When you do rebase git makes copies of the commits of current branch, it creates new commits with mostly the same data. Actually exactly the same data except for their parents. So the new commit exactly looks like the original commits, but they are new objects with new SHA1's. So they are new files with new file name in database director. Finally, then git moves pointer of the rebase branch to new commit leaving the old commit behind. The older commits are later garbage collected.

### What is difference between merging and rebasing?

Merges preserves history of commits, merge and conflicts where as in rebase history looks cleaner and in single line but we have to compromise the history. `When in doubt, just merge`

### What this repository contains?
- This repository contains handfull of commands and git information that are used in day to day development.
