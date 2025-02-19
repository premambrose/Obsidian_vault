

# From ChatGPT
**Basic commands:**

- `git init`: Initializes a new Git repository in the current directory.
- `git clone <url>`: Creates a copy of a remote repository on your local machine.
- `git add <file>`: Adds a file to the staging area.
- `git commit -m "<message>"`: Commits changes to the local repository with a message describing the changes.
- `git status`: Shows the status of the current repository, including files that have been modified or added.

**Branching and merging:**

- `git branch`: Lists all local branches in the repository.
- `git branch <branch-name>`: Creates a new branch with the specified name.
- `git checkout <branch-name>`: Switches to the specified branch.
- `git merge <branch-name>`: Merges the specified branch into the current branch.

**Remote repositories:**

- `git remote`: Lists all remote repositories.
- `git remote add <name> <url>`: Adds a new remote repository with the specified name and URL.
- `git push <remote> <branch>`: Pushes changes to the specified branch in the remote repository.
- `git pull <remote> <branch>`: Pulls changes from the specified branch in the remote repository.

**Undoing changes:**

- `git reset <file>`: Removes a file from the staging area.
- `git reset --hard`: Discards all changes since the last commit.
- `git revert <commit>`: Reverts a commit and creates a new commit with the reverted changes.
- `git checkout <file>`: Discards changes to a file and reverts it to the last committed version.

This is just a basic cheatsheet, but it should give you a good starting point for using Git. There are many more commands and options available, so be sure to consult the Git documentation for more information.

# Others 
## General
- Log the git commits
	***git log --oneline***
- See the differences from last commit
	***git diff***
- Make git track all the newly added files
	***git add .***
	
## Delete commits
- Deletes the last commit
	***git reset --hard HEAD~1***
- Undo the last commit and move changes to stage area
	***git reset --soft HEAD~1***
- Delete nth commit *(only do it on local changes)*
	***git rebase -i HEAD ~n***
	***Press 'i' to enter insert mode
	Replace "pick" with "drop" before the nth commit***
- To  abort rebase if conflict happens
	***git rebase --abort***

## Rewrite commit messages
- Change message of last commit
	***git commit --amend -m "new message"*
- Change message of nth commit *(only do it on local changes)*
	***git rebase -i Head~n*
	 Press i for insert mode
	 Replace "pick" with "reword" before the nth commit
	 Press ESC , : , w, q
	 Press i for insert mode
	 Change the commit message
	 Press ESC , : , w, q

## Git Amend
- Add files forgot to add in commit *(only in local changes)*
	***git status
	git add file1 file2
	git commit --amend --no-edit***	

## Git Rebase
- Rebase instead of merge to rebase a branch to master with a straight line of commits
	1. ***git checkout <new_branch>***
	2. ***git commit -m "changes"***
	3. ***git rebase master***
	4. ***git checkout master***
	5. ***git rebase <new_branch> ***

## Git Stash
- Add changed files to staged area
	***git add .***
- Stash the files for later work and work on other files
	***git stash***
- Show the changes in last stash
	***git stash show***
- Pop the latest stash files to master and work on it
	***git stash pop***
- Stash with a message (Multiple stash can be made in time)
	***git stash -m "message for stash"***
- list the multiple stashes made with index
	***git stash list***
- Pop nth stash to master branch for work. latest stash will have index 0(stashes are stacked)
	***git stash pop --index n***
- Convert a stash into a branch
	***git stash branch BRANCH_NAME INDEX_OF_STASH*
- Clear all the stashes
	***git stash clear*

