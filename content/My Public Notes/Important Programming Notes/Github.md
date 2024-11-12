## What is github?

- It's a platform for hosting and collaborating on code repositories.
- It provides version control using Git, making it easier for developers to work together on projects

## Basic commands
### Creating a repository

- Initialize a new git repository locally
	`git init`
- Add files to the repository
	`git add .`
- commit the changes 
	`git commit -m "Initial Commit"`
	or
	`git commit`
- link the local repository to remote repository on github
	`git remote origin <repository_url>`
- push the changes to github
	`git push`
- clone a repository from github to your local machine
	`git clone <repository url>`

### Branching and merging

- Create a new branch
	`git branch <branch name>`
- switch to the new branch
	`git checkout <branch name>`
- to merging brenches
	- switch to the branch you want to merge into
		`git checkout <target branch>`
	- merge changes from another branch into current branch
		`git merge <source branch>`

### Collaborating

- forking a repository
	`Forking a Repository`
- create a pull request to suggest changes to the original repository
	`Pull Requests`
- review and provide feedback on pull requests submitted by others
	`Reviewing Pull Requests`

### Miscellaneous

- checking status of the files in the repository
	`git status`
- view commit hostory
	`got log`
- undo changes in the working directory to the last commit
	`git checkout -- <file name>`
- undo the last commit
	`git reset HEAD-1`


[[Git Important Notes]]
#git
#github