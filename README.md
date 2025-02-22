# These are the steps to follow to push any locally created repo (say "LocalRepo") to GitHub using CLI

## Steps Involved (VS Code  Terminal's Git Bash Shell/Profile was used)

### 1. Create a new folder in VS Code using Explorer e.g. name it "LocalRepo". Check that this new repo is not yet a git repo by executing the command below

```bash
ls -a # shows all files present in directory, even hidden ones
```

Output of above command should NOT show ".git"

### 2. Create new files in the local repo (optional; using CLI)

Github does recommend every repository include a README, LICENSE, and .gitignore. This can be done later as well, whether locally or on GitHub. In the local file creation case, remember to follow all steps to push your changes, while in the remote GitHub file creation case remember to follow all step to clone or pull the repo from remote to local machine. Below is the command to create a new README file

```bash
echo "# Hi! I am the heading line of readme file in markdown" > README.md
```

Be cautious of above command if you have already created a README.md file (or any file of same name) before in this repo.

To append text to an already existing file say README.md, use the command below:

```bash
# note the use of ">>" instead of ">"

echo "Hey! I am the appended line (not a heading) in readme file" >> README.md
```

### 3. Initialize the Git Repository

```bash
git init
```

The git init command creates a new .git subdirectory in your project folder, setting up the necessary files and directories Git uses to track your project's history. Next, check again with:

```bash
ls -a
```

The output of above command should show ".git" now.

### 4. Checking Your Current Branch Name (optional if name is already "*main*")

Before renaming, it's prudent to verify the current branch name to avoid potential conflicts. You can do this by executing:

```bash
git branch
```

This command lists all local branches and highlights the current one with an asterisk (*). If the current branch is already named "*main*", there's no need to rename it (i.e., step 4.1 below can be skipped).

#### 4.1 Rename the Current Branch to main (this is the optional step)

The command below renames the default branch from "*master*" to "*main*". Executing this command immediately after initialization ensures that all subsequent commits are made on the "*main*" branch.

```bash
git branch -M main
```

**Note**: If your repository already contains commits on a branch named "*master*", and you wish to rename it to "*main*", you can do so with:

```bash
git branch -m master main
```

After renaming, ensure you update the default branch settings on your remote repository and inform collaborators to update their local repositories accordingly.

### 5. Stage Changes

The git add command adds changes in the working directory to the staging area.

```bash
#The dot (.) indicates all files in the current directory.
git add .

#to add only README.md file of current directory to staging area, execute:
git add README.md
```

### 6. Commit Changes

After staging, commit the changes by executing:

```bash
git commit -m "first commit"
```

The git commit command captures a snapshot of the project's currently staged changes. The -m flag allows you to add a commit message inline.

### 7. Connecting to GitHub

To share your local repository on GitHub, you'll need to create a remote repository and link it to your local repo:

#### 7.1 Create a New Repository on GitHub

- Log in to your GitHub account.
- Click on the "+" icon in the top-right corner and select "New repository."
- Enter a repository name and description.
- Choose between public or private visibility.
- Click "Create repository."
- Add the Remote Repository

### 8. Add the Remote Repository

In VS Code's terminal, add the remote repository with the git remote add command.

The git remote add command creates a new connection to a remote repository. The default name given to this remote is "origin", but it can be changed if needed.

```bash
# Replace "amaan-123" and "LocalRepo" with your GitHub username and repository name, respectively.
git remote add origin https://github.com/amaan-123/LocalRepo.git
```

### 9. View Remote URLs

```bash
git remote -v # Displays the URLs of remote repositories.
```

### 10. Push Changes to GitHub

The git push command uploads your local commits to the remote repository:

```bash
# The -u flag sets the upstream tracking reference, so future pushes can be done with just git push:

git push -u origin main
```

If your default branch is named "*master*" instead of "*main*", adjust the command accordingly:

```bash
git push -u origin master 
```

So, a future push to the associated remote repo (with this repo set as current directory in your terminal's shell) would be done by just executing:

```bash
git push
```

### 11. Adios Amigo! 😎
