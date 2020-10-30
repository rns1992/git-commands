# What is git?

- Git is hight level file system built on top of native file system. It was written by Linus Torvalds. It is versioned file system, a content tracker. It is a persistent map at its core and layered on top of it, a content tracker that looks a lot like versioned file system.

# How it works?

- With every change in file git calculates SHA-1 (hash) of file and stores its content in file as a blob in folder `\.git\objects`. Hash(SHA-1) value is same for all OS. For example, I commit a file. Git calculates a hash of that file for example - f825dcc465e7e1f54a09a27951c82b548795ed. It creates folder with first two letters of hash in `object` folder `(f8)` and creates a sub folder inside it with remaining value of hash `25dcc465e7e1f54a09a27951c82b548795ed`. To view the content of file and use plumbing connands. Also version of folders are tracked and stored in same way as above but the content is different. It contains 2 more attribues along with commit detaiks, `tree` and `parent`. 

# What this repository contains?
- This repository contains handfull of commands that are used in day to day development. 
