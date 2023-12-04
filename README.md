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
`git status --ignored` - adds **Ignored files** section    

- *Add files, start to track them*  
`git add <file.name>`   
`git add .` OR  `git add --all` to track all files in the folder  

- *Commit changes and save to the log*  
`git commit -m "DONT FORGET TO WRITE COMMENTS`"`  

### A bit of information about Git statuses  
1. **untracked** - Git does not have history with file nor saves it with commits.  
2. **tracked** - an opposite of **untracked** status. Git added file to its logs and will track its changes and, in general, existance(whether it was deleted or moved).
3. **staged** - after running `git add` file becomes staged as well as **tracked**. Staged status says that this file current version is ready for commit.
4. **modified** - a **tracked** file that has been modified. You can run `git add` to prepare file for commit and change its status to **staged**


![alt-text](https://github.com/DuuuDik/Github_tutorial.-Yandex-Practicum/blob/master/pictures/gits_statuses.png)

## Working with log history   
- *Get full log history*  
`git log` 

- *Get short log history*   
`git log --oneline` 

- *Get changes of one commit*  
`git diff <hash>`

- *Get changes between commits*  
`git diff <first hash> <second_hash>`

- *Reset files to older version*  
`git reset --hard <commit hash>`

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

### Check changes
- *See what changes have been made in **modified***   
`git diff`  

- *See what changes have been made in **staged***  
`git diff --staged`  


### Change before commits
- *Unstage file(s)/reverce latest `git add`*  
`git restore --staged <file>`  

- *Restore file to latest `git commit` or `git add`(staged) version*  
`git restore <file>`  

![alt-text](https://github.com/DuuuDik/Github_tutorial.-Yandex-Practicum/blob/master/pictures/git_reset.png)

**IMPORTANT TIP:** `reset` works with commits, while `restore` works with files. Might be usefull to memorise that.

## Working with branches
#### General interaction with branches
- *View branches*  
`git branch`

- *Create new branch*  
`git branch <branch_name>` 

- *Jump to another branch*  
`git checkout <branch_name>`  
`git checkout -b <branch_name` - create new branch and jump on it

- *Get differencies between branches*  
`git diff <branch_1> <branch_2>`  
**PRO-TIP** - it is possible to compare branches to commit hashes.   
**PRO-TIP** - `~` sign is used to simplify comparison. By default, it gets commit before current one  
but it can get any number after it, for instace `master~3`, will show 3rd from end commit  
from `master` branch 

#### Merge and delete branches
- *Merge branches*  
`git merge <merged_branch>`  use from another branch.

- *Delete branch*  
`git branch -D <branch_name>`  
Use flag `-d` if you don't want to delete branch, if it wasn't merged before  

In case **CONFLICT** emergies, manually solve it  
![alt-text](https://github.com/DuuuDik/Github_tutorial.-Yandex-Practicum/blob/master/pictures/merge_conflict.png)
[Official Git recomendations about solving conflicts](https://git-scm.com/book/ru/v2/%D0%98%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D1%8B-Git-%D0%9F%D1%80%D0%BE%D0%B4%D0%B2%D0%B8%D0%BD%D1%83%D1%82%D0%BE%D0%B5-%D1%81%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5)

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
#### Clone
- *Cloning existing Github to local*  
`git clone <ssh-link>`

- *Update local repositary by Github version*
`git remote -v`

#### Pull and Push
- *Push local to remote (Git to Github)*  
`git push -u origin main` for the first time, later you can use simplified version  
`git push`  

- *Pull remote to local*  
`git pull origin main` for the first time, later you can use simplified version  
`git pull` 

## .gitignore usage samples
1. `file_name`  ignores all files with this name in all folders
2. `*.jpeg` ignores all files with `jpeg` extention   
- `docs/*/tmp` ignores all **tmp** files in all **docs** subfolders. (example docs/first/tmp)   
- `docs/**/tmp` ignores any **tmp** within **docs** on any level. (example docs/a/b/c/b/tmp)   
3. `?` - means any character, but only one.  
For instance `file?.txt` will ignore **file1.txt**
4. `[...]` - means a range of characters, but only one.  
For instanse `file[0-2].txt` will ignore `file2.txt`, but won't ignore **file3.txt**  
Same goes for letters `[a-z]`  
5. `/todo.txt` - ignores **todo.txt** in root folder  
`build/` - ignores folder **build**  
6. `!` inverts any given rule.  Usefull for exceptions.  
`*.jpeg` but we want to save Doge meme  
`!doge.jpeg`  



#### Less usefull comands  
- *Read a text file*  
`cat <file>`

- *Write into a text file new line*  
`echo "new line" >> <file>`

- *Write into a text file line, fully overwriting file contents*  
`echo "new line" > <file>`

*If you accidently activated Vim, when you forgot to add message to commit, write `!qa!` to exit

## How to Commit correctly. Conventional Commits
([Conventional Commits standarts](https://www.conventionalcommits.org/ru/v1.0.0-beta.4))

## Cheatlist for Markdown  
([https://github.com/sandino/Markdown-Cheatsheet](https://github.com/sandino/Markdown-Cheatsheet))  
([checklist](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet))  
([additional usefull link](https://www.markdownguide.org/cheat-sheet/))