# Master Notes

Last Update: 15 Apr 2021

## CLI

### Basic Commands

* make directory: `mkdir [folder name]`
* create file: `touch [file name]`
* move or rename: `mv [old] [new]`
* copy: `cp [old] [new]`
* recursive copy: `cp -r [old] [new]`
* remove: `rm [file name]`
* recursive remove: `rm -r [file name]`
* clear terminal: `cmd + k`

## Git & Github

* [git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)

### Basic Commands

* initize repo: `git init`
* clone repo: `git clone [url]`
* add to stage: `git add [filename]`
* commit: `git commit -m "[message]"`
* push: `git push`
* pull: `git pull`
* see all branches: `git branch -a`
* create branch: `git branch [new branch name]`
* switch branches: `git checkout [branch name]`
* create and switch brnaches: `git checkout -b [new branch name]`

### Advanced Commands

* create a new repository on the command line

```
echo "# gal_sdi" >> README.md
git init
git add .
git commit -m "init commit"
git branch -M main
git remote add origin https://github.com/josiah-d/gal_sdi.git
git push -u origin main
```

* push an existing repository from the command line

```
git remote add origin https://github.com/josiah-d/gal_sdi.git
git branch -M main
git push -u origin main
```