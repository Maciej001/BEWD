# Git and Github

## General 

**Three stages:**

- committed - data safely stored in your local system
- modified - changed but not committed into your db
- staged - marked as changed to go to commit in next stage


**Basic workflow:**

1. modify file in working directory
2. stage the files
3. commit - permanent snapshot in git directory

**First time setup**

- `/etc/gitconfig` - values for every user on the system
- `/.gitconfig` - specific to the user. you can make git read and write to the file by passing --global variable.
- `.git/config` - file within your repository.

[Github setup](https://help.github.com/articles/set-up-git)

```
git config --global user.name “Maciej Nowakowski”
git config --global user.email “m.nowakowskipl@gmail.com”
git config --global core.editor subl
```

to check:
`git config --list`

Repository

`git init` - in project directory to start tracking your peroject
`git add .`   - add all the project files to repository
`git commit -m ‘initial commmit’` 

`git clone url` - clones the whole repository

`git log` - shows all the commits
`git help log` - to get help screen for log command
`git log -n number` - shows last number of commits
`git log --since=2013-28-12` - commits od podanej daty
`git log --grep=”Init”` - szuka commits z “init w opisie”



##Git architecture

**Three-tree architacture**

- repository
- staging index
- working (where you write and save file on hd)

**Undoing changes**

in working directory:
you deleted something from the file and saved it, closed the file. but you want to undo that

`git status` - will show that the file is red, meaning it has been changed

`git diff` - wyswietli jakich zmian ostatnio dokonales.

**I want the respository version back now!**

git take the last repository version and bring it back to my working directory.

`git checkout index.html` - in most cases it will work. it goes to repository and makes your working directory to look like repository.

better:
`git checkout -- index.html` - meaning, stay on the current branch

**retrieving the old version:**

git checkout 2954ef (pierwsze pare cyfr commit) -- index.html (file, ktory chcemy przywrocic)
it moves the file from repository to staging area.
you can check it: git status, and the file will be in green, and ready for commit

**reverting commit:**

`git revert  737347ea4a`

#GitHub 

1. Create new repository on github.com. You can call it whatever you want. 
You can add README file, and gitignore file, and github will show you what you should do 

2. Push existing repository:
`git remote add origin https://github.com/Maciej001/my_repo.git`
`git push -u origin master`

`git remote` - wyswietli wszystkie remote repositories znane dla tego projektu

origin - to dowolna nazwa( moze byc np.primary) twojego remote repository.

`git remote -v`        gives a bit more information

`git remote rm origin`       usuwa remote repository o nazwie ‘origin’

`git push -u origin  maste`r      pushes repository (master branch)  to origin remote repository

`git branch`           checks on which branch you are on now


##Branching

1. make  a new branch

`git checkout -b nazwa-branch`

2. add and commit. if you did not create new files

`git commit -am “improved files”`

**with new files:**
```
git add .
git commit -m “improved files”
```

3. move to master branch and merge
```
git checkout master
git merge my_branch
```

`git branch -d my_branch` - to delete my_branch


to delete branch before merging:

`git checkout master` - to go back to master
`git branch -D my_branch - "D" deletes branch




















