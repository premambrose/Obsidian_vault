Here's a bash script that automatically pulls changes from a Git repository, commits changes with a commit message containing the computer name and time, and pushes the changes back to the repository:

```
#!/bin/bash

# Set the commit message to the computer name and time
commit_message="$(hostname) $(date)"

# Change to the Git repository directory
cd /path/to/git/repository

# Pull changes from the remote repository
git pull origin main

# Add all changes to the staging area
git add .

# Commit changes with the commit message
git commit -m "${commit_message}"

# Push changes to the remote repository
git push origin main
```

This script assumes that you have already set up a Git repository and cloned it to your local machine. You'll need to modify the `/path/to/git/repository` to the actual path of your Git repository.

The script uses the `hostname` command to get the name of the computer and the `date` command to get the current date and time. It concatenates these values to create the commit message.

The script then changes to the Git repository directory using the `cd` command. It pulls changes from the remote repository using the `git pull` command.

The script adds all changes to the staging area using the `git add .` command. It then commits the changes with the commit message using the `git commit -m "${commit_message}"` command.

Finally, the script pushes the changes to the remote repository using the `git push` command.

You can set up a cron job to run this script at regular intervals to automatically pull and push changes to the Git repository.