## Sources
-[YT tutorial - GitHub for beginners](https://www.youtube.com/watch?v=0fKg7e37bQE&t=684s)

# Git commands
- When typing these commands in the terminal, the current folder in your terminal must correspond to the project you want to commit 
- Initialize the local directory as a Git repository
  ```cmd
  git init
  ```
- Add files and changes to your new local repository. Use file name for a specific file or . for all files in the folder (for initial commit).
  ```cmd
  git add .
  ```
- Shows the difference between files on the local machine and the remote repository
  ```cmd
  git status
  ```
- Commit changes to the repository with a message (-m) "First commit". Important: this still is not uploaded to the repo.
```cmd
git commit -m "First commit"
```
- Upload commited changes to the repository
```cmd
git push
```
- Pull changes down from the remote repo to your local machine
```cmd
git pull
```
- Pull a repository from a remote repository (GitHub) to your local machine using the provided url
```cmd
git clone [url]
```
