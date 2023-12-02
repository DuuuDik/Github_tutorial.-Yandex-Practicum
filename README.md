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

## Working with log history   
- *Get full log history*  
`git log` 

- *Get short log history*   
`git log --oneline` 

## Connect Git to Github
- *If ~/.ssh/ does not exist, generate SSH-keys first*   
`ssh-keygen -t ed25519 -C "your@email.here"`  
OR  
`ssh-keygen -t rsa -b 4096 -C "your@email.here"`
As a result of commands, it will ask where to save generated keys and also new passwords for them.  
I recommend leaving those empty.  

- *Copy ssh key and paste it later in Github settings*
*clip < ~/.ssh/id_rsa.pub*   
OR  
*clip < ~/.ssh/id_ed25519.pub *   

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


Cheatlist for Markdown  
([https://github.com/sandino/Markdown-Cheatsheet](https://github.com/sandino/Markdown-Cheatsheet))
([original](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet))
[additional usefull link](https://www.markdownguide.org/cheat-sheet/)