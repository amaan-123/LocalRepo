# These are the steps to follow to push any locally created repo (say "LocalRepo") to GitHub from VSCode Bash Terminal

## Steps Involved

### 1. Create a new folder in VS Code e.g. it is named "LocalRepo". Check that this new repo is not yet a git repo by executing command

```bash
ls -a
```

// *output of above command should NOT show .git*

### 2. Init command

```bash
git init
```

// *This command creates a new .git subdirectory in your project folder, setting up the necessary files and directories Git uses to track your project's history.*

```bash
ls -a
```

// *output of above command should show .git now*

### 3. Create a new repo in GitHub, without any additional files like README.md, .gitignore, etc for now

 // *because if we do create other items, then we'd also need to pull as those files wouldn't be present locally.*

```bash
git remote add origin https://github.com/yourusername/your-repo-name.git
```

// *The git remote add command creates a new connection to a remote repository. origin is the default name given to this remote, but it can be changed if needed.*

```bash
git remote -v
```

// *Displays the URLs of remote repositories.*

```bash
git branch
```

// *Shows all local branches, highlighting the current one.*

```bash
git branch -M main
```

// *to rename branch, may not need to rename if LocalRepo on machine is already main.*

```bash
git push -u origin main
```

// *-u to add upstream reference so that you only need to write git push as below.*

```bash
git push
```
