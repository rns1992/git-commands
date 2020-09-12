## Global Commands

There are some parameters that needs to be setup initially before dealing with repositories in Git. They effect globally.

- To set **username** and **email** globally:
  ```
  git config --global user.name "Raj Soni"
  git config --global user.email "raj.soni@git.com"
  ```
- To list all parameters that are set globally: 
  ```
  git config --list
  ```
- To view all our settings and from where they are been set:
  ```
  git config --list --show-origin
  ```
- To set editor:
  ```
  git config --global core.editor "'C:\Program Files (x86)\PSPad editor\PSPad.exe'"
  ```
