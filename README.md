# Git usefull commands    
In this repositary, I will try to collect most usefull Git Bash commands. 

## Starting commands   
- *Create local .git folder*  
`git init`  

- *Delete .git folder (in case if needed)*  
`rm -rf .git` 


## Git local commands
- *Check Git status*  
`git status`  

- *Add files, start to track them*  
`git add <file.name>`   
`git add .` OR  `git add --all` to track all files in the folder  

- *Commit changes and save to the log*  
`git commit -m "DONT FORGET TO WRITE COMMENTS`"`  

### A bit of information about Git statuses  
1. **untracked** - Git does not have history with file nor saves it with commits.  
2. **tracked** - an opposite of **untracked** status. Git added file to its logs and will track its changes and, in general, existance(whether it was deleted or moved).
3. **staged** - after running `git add` file becomes staged as well as **tracked**. Staged status says that this file and it current version is ready for commit.
4. **modified** - a **tracked** file that has been modified. You can run `git add` to prepare file for commit and change its status to **staged**


![alt-text](https://github.com/DuuuDik/Github_tutorial.-Yandex-Practicum/blob/master/pictures/gits_statuses.png)

## Working with log history   
- *Get full log history*  
`git log` 

- *Get short log history*   
`git log --oneline` 

### Additional information about logs
- Git transforms information about your commits using algolithm SHA-1 and produces **hash**  
- **Hash** allows to get information about commit, its author and info about commited files  
- **HEAD** is file within .git repositary, which holds the name of the latest commit. It can be used as an argument, if you need to address latest commit.  

### Change made commits
- *Change latest commit*  
`git commit --amend --no-edit`  
**--no-edit** flag saves previous message given to the edited commit  

- *Change latest commit massage*  
`git commit --amend -m "New massage"`

### Change before commits
- *Unstage file(s)/reverce latest `git add`*  
`git restore --staged <file>`  

- *Reset commit to older version*  
`git reset --hard <commit hash>`

- *Restore file to latest `git commit` or `git add`(staged) version*  
`git restore <file>`  

**IMPORTANT TIP:** `reset` works with commits, while `restore` works with files. Might be usefull to memorise that.

## Connect Git to Github
- *If ~/.ssh/ does not exist, generate SSH-keys first*   
`ssh-keygen -t ed25519 -C "your@email.here"`  
OR  
`ssh-keygen -t rsa -b 4096 -C "your@email.here"`  
As a result of commands, it will ask where to save generated keys and also new passwords for them.  
I recommend leaving those empty.  

- *Copy ssh key and paste it later in Github settings*  
`clip < ~/.ssh/id_rsa.pub`
OR  
`clip < ~/.ssh/id_ed25519.pub`

- *Check if connection works. If done correcty, you will see first-timer warning, enter "yes" to continue*   
`ssh -T git@github.com`  

- *Link local .git to Github*  
`git remote add origin main link@github.com:to_your_project/here.git`  
*if error, try changing MAIN to MASTER*

- *Check if link established correctly*  
`git remote -v`  

## Working with Github
- *Push local to remote (Git to Github)*  
`git push -u origin main` for the first time, later you can use simplified version  
`git push`  

- *Pull remote to local*  
`git pull origin main` for the first time, later you can use simplified version  
`git pull` 

## How to Commit correctly. Conventional Commits
([Conventional Commits standarts](https://www.conventionalcommits.org/ru/v1.0.0-beta.4))


Cheatlist for Markdown  
([https://github.com/sandino/Markdown-Cheatsheet](https://github.com/sandino/Markdown-Cheatsheet))  
([original](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet))  
[additional usefull link](https://www.markdownguide.org/cheat-sheet/)