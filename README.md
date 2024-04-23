# Mosh Hamedani Git Tutorial

[Yout tube video](https://www.youtube.com/watch?v=8JJ101D3knE)

user defaults
```sh
haraldbeker@MacBookHarry GitTutorial % git config --global user.email "<qualcunodue@gmail.com>"
haraldbeker@MacBookHarry GitTutorial % git config --global user.name "Helmut Qualtinger"
haraldbeker@MacBookHarry GitTutorial % git config --global core.editor "code --wait"

```

configuation file:

```conf
[user]
 name = Helmut Qualtinger
 email = qualcunodue@gmail.com
[filter "lfs"]
 clean = git-lfs clean -- %f
 smudge = git-lfs smudge -- %f
 process = git-lfs filter-process
 required = true
[core]
 autocrlf = input
 editor = code --wait
```

## Creating snapshots:

```sh
git init
```

## Git Workflow

Git uses a stages area

## Staging files
use add command

````sh
(base) haraldbeker@MacBookHarry GitTutorial % echo Hello >file1.txt
(base) haraldbeker@MacBookHarry GitTutorial % echo Hello >file2.txt
(base) haraldbeker@MacBookHarry GitTutorial % git statis
git: 'statis' is not a git command. See 'git --help'.

The most similar command is
        status
(base) haraldbeker@MacBookHarry GitTutorial % git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        file1.txt
        file2.txt

nothing added to commit but untracked files present (use "git add" to track)
(base) haraldbeker@MacBookHarry GitTutorial % git add *.txt
(base) haraldbeker@MacBookHarry GitTutorial % git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   file1.txt
        new file:   file2.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

(base) haraldbeker@MacBookHarry GitTutorial % echo Hello World>file1.txt
(base) haraldbeker@MacBookHarry GitTutorial % git status                
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   file1.txt
        new file:   file2.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file1.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

(base) haraldbeker@MacBookHarry GitTutorial % git add file1.txt 
(base) haraldbeker@MacBookHarry GitTutorial % git status       
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   file1.txt
        new file:   file2.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

(base) haraldbeker@MacBookHarry GitTutorial % git commit -m "Initial commit"
[main (root-commit) 2a8a407] Initial commit
 2 files changed, 2 insertions(+)
 create mode 100644 file1.txt
 create mode 100644 file2.txt
 ````

## Committing best practices

Commit each logical set of changes

## skipping the staging area
```sh
echo test >> file1.txt
git commit -am fixed a bug
```
