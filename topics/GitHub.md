Git Commands
============


### Note
- When typing these commands in the terminal, the current folder in your terminal must correspond to the project you want to commit 

### Steps for Pushing Changes
1. `git pull [remote] [your active local branch]`   

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |
| `touch .gitignore` | Add .gitignore file to your local Git repository (open in text editor and add a list of files which you don't want uploaded to the remote repository |

### Basic Snapshotting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status (Shows the difference between files on the local machine and the remote repository) |
| `git add [file-name.txt]` | Add a file to the local staging area |
| `git add -A` | Add all new and changed files to the local staging area. You can also use . instead of -A |
| `git commit -m "[commit message]"` | Commit changes with a message (-m). If you commit changes without '-m', exit the screen with ESC + :wq |
| `git rm -r [file-name.txt]` | Remove a file (or folder) from local staging area. You can also use git remove instead. |
| `git reset` | Removes all files from local staging area. |

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote). Branch with * is the branch you're currently working on.  |
| `git remote -v` | Check what remote branches have been set.  |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch (locally) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git branch --merged` | Shows a list of all branches merged into the active branch. Useful when merging with the master branch. |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git merge [source branch] [target branch] --allow-unrelated-histories` | Merge a branch into a target branch when github thinks two branches are unrelated (refusing to merge unrelated histories error) |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote origin repository (remote repository has to be created on your github account first). |
| `git push origin [branch name]` | Push a [branch] to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes |
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Initial Install

| Command | Description |
| ------- | ----------- |
| `git --version` | Checks the version of the installed locally git |
| `git config --global user.name [name]` | Sets up the name of the user  |
| `git config --global user.email [mail]` | Sets up the mail of the user  |
| `git config --list` | List all git configurations |


### Sources
- [YT tutorial: GitHub for beginners](https://www.youtube.com/watch?v=0fKg7e37bQE&t=684s)
- [YT tutorial: Corey Shafer's Git Tutorial for Beginners: Command-Line Fundamentals](https://www.youtube.com/watch?v=HVsySz-h9r4&t=131s)
- [Official GitHub documentation](https://docs.github.com/en/free-pro-team@latest/github)
