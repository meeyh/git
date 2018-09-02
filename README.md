## Git Skills Learn

#### Git Install

**`sudo apt-get install git`**  Git install on Linux

`git config -l` or `git config --list`  List all config

`git config --global <option>` Configure global options

 - `git config --global user.name "YourName"`
 - `git config --global user.email "YourE-Mail"`


#### Create Repository

`git init`  Initialize a Git repository

`git add <file>`  Stage file

 - `git add README.md` or `git add .` 

`git commit`  Commit stage fiels to the local repository

 - `git commit -m "add README.md file"`

#### Version Rollback

`git status` Check working directory status

`git diff` View modify content

 - `git diff README.md`
 
`git log` Show commit log

`git log --pretty=oneline` One line show commit log

`HEAD` Represents the current version， `HEAD^` Up one version， `HEAD^^` Up two version， `HEAD~100` Up one hundred version

`git reset --hard HEAD^` Rollback to previous version

`git reset --hard 5ec5b8e` Specifies to return to some a version

`git reflog` View command history
