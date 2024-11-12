- git init - makes git work (needed at 1st time)

- git status
- git add . - puts all files in staging area
- git commit - makes commit of staging area
- git push - push all new commits to github

- git checkout main
- git merge feat/filter-btn      puts changes of feat/filter-btn to HEAD

## To make repository using git for the first time
No problem! Here are the steps to upload (push) your repository to GitHub for the first time using Git.

### Step-by-Step Guide

#### 1. **Create a New Repository on GitHub**

1. Go to [GitHub](https://github.com).
2. Click on the `+` icon at the top right corner and select `New repository`.
3. Fill in the repository name, description (optional), and choose the visibility (public or private).
4. Click `Create repository`.

#### 2. **Initialize Your Local Repository**

If you haven't already initialized your local repository, navigate to your project directory and run:
```sh
git init
```

#### 3. **Add Your Files to the Repository**

Add all your project files to the staging area:
```sh
git add .
```

#### 4. **Commit Your Files**

Commit your changes with a descriptive commit message:
```sh
git commit -m "Initial commit"
```

#### 5. **Add the Remote Repository**

Add the URL of the remote repository you created on GitHub. Replace `<username>` with your GitHub username and `<repository>` with your repository name.
```sh
git remote add origin https://github.com/<username>/<repository>.git
```

#### 6. **Push Your Changes to GitHub**

Push your local commits to the remote repository on GitHub:
```sh
git push -u origin main
```

### Example Command Sequence

Here's a complete example of the commands:

1. **Initialize the Local Repository** (if not already done):
   ```sh
   cd "C:\Users\chels\OneDrive\Documents\Practice Coding\Naruto Game\Naruto Game Project  Pt 2 Final"
   git init
   ```

2. **Add Your Files**:
   ```sh
   git add .
   ```

3. **Commit Your Changes**:
   ```sh
   git commit -m "Initial commit"
   ```

4. **Add the Remote Repository**:
   ```sh
   git remote add origin https://github.com/chelsyyolanori07/shinobi-battle.git
   ```

5. **Push Your Changes**:
   ```sh
   git push -u origin main
   ```

### Verify Your Changes on GitHub

After running these commands, go to your GitHub repository page. You should see all your files uploaded there.

## To push edit file or anything new to the available repository

1. `git init` (to turn on git every the first time you open your project folder)
2. edit file you want to edit
3. `git add .` (for tracking all files)
4. `git status` (make sure this correct and make sure you check it everytime just to make sure)
5. after you check that git status is correct then you can do `git commit`
6. `git push` you did git push in the end after you did all of that

## Special occasion when you add something outside of the internal thing like readme or smth and you make change in it make sure you do this (push the local commits to the remote repository)
experince case:
local branch is ahead of the remote branch by 2 commits, you have commits locally that have not yet been pushed to the remote repository. You can proceed with pushing your local commits to the remote repository.

1. `git pull origin main`(This command will upload your local commits to the remote repository, updating the `main` branch on GitHub.)
2. `git status`
3. `git push origin main` (your local changes will be pushed to the remote repository, and your local and remote branches will be in sync)
4. `git status`

case:
C:\Users\chels\OneDrive\Documents\Practice Coding\Naruto Game\Naruto Game Project  Pt 2 Final>git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

C:\Users\chels\OneDrive\Documents\Practice Coding\Naruto Game\Naruto Game Project  Pt 2 Final>git push origin main
Enumerating objects: 9, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 552 bytes | 552.00 KiB/s, done.
Total 5 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), completed with 2 local objects.
To https://github.com/chelsyyolanori07/shinobi-battle
   cba29a3..3f41c88  main -> main

C:\Users\chels\OneDrive\Documents\Practice Coding\Naruto Game\Naruto Game Project  Pt 2 Final>git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

is it already good?

Yes, everything looks good! The output indicates that your local branch and the remote branch on GitHub are now in sync. Your recent changes have been successfully pushed to the remote repository. Here's a summary of the status:

- **Local and Remote Branches are in Sync**: The message `Your branch is up to date with 'origin/main'` confirms that there are no differences between your local branch and the remote branch.
- **Working Tree Clean**: The message `nothing to commit, working tree clean` means there are no uncommitted changes in your working directory.

### Summary

1. **Pushed Successfully**:
   ```sh
   git push origin main
   ```

2. **Checked Status**:
   ```sh
   git status
   ```

Both commands confirmed that your local changes are now reflected in the remote repository, and everything is in a clean state :)

#git