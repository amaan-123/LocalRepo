# These are the steps to follow to push a locally created repo called "LocalRepo" to GitHub from VSCode Bash Terminal

## Steps Involved

### 1. Create a new folder in VS Code e.g. it is named "LocalRepo". Check that this new repo is not a git repo by executing command

ls -a /*should **NOT** show .git*/

### 2. Init command

git init
/*This command creates a new .git subdirectory in your project folder, setting up the necessary files and directories Git uses to track your project's history.

ls -a /*should show .git now*/

/*Create a new repo in GitHub, without README & other additional things for now (because if we do create other items, then we'd also need to pull as those files wouldn't be present locally)*/

git remote add origin <https://github.com/yourusername/your-repo-name.git>
/*The git remote add command creates a new connection to a remote repository. origin is the default name given to this remote, but it can be changed if needed.*/

git remote -v /*Displays the URLs of remote repositories.*/

git branch /*Shows all local branches, highlighting the current one.*/

git branch -M main
/*to rename branch, may not need to rename if LocalRepo on machine is already main*/

git push -u origin main
/*-u to add upstream reference so that you only need to write git push*/
git push
