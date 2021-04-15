# Master Notes

Last Update: 15 Apr 2021

## Git & Github

* [git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)

### Basic Commands

* initize repo: `git init`
* clone repo: `git clone [url]`
* add to stage: `git add [file_name]`
* commit: `git commit -m "[message]"`
* push: `git push`
* pull: `git pull`

### Advanced Commands

* create a new repository on the command line

```
echo "# gal_sdi" >> README.md
git init
git add README.md
git commit -m "first commit"
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