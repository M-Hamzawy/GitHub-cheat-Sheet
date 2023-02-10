# GitHub Cheat Sheet


_A list of my commonly used Git commands_

*If you are interested in my Git aliases, have a look at my `.bash_profile`, found here: https://github.com/joshnh/bash_profile/blob/master/.bash_profile*

--

### Getting & Creating Projects

| Command | Description |
| ------- | ----------- |
| `git init` | Initialize a local Git repository |
| `git clone ssh://git@github.com/[username]/[repository-name].git` | Create a local copy of a remote repository |

### Basic Snapshotting

| Command | Description | exra info |
| -- | --- | ----------------- |
| `git status` | Check status of the staging area|
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area | 
| `git commit -m "[commit message]"` | Commit changes `(-a -m "message)` <br> to add all unstaged files and commit directly <br> `git commit --help` to sea all other flags| To set your account's default identity:<br>`git config --global user.email "you@you.com"` <br> `git config --global user.name "Your Name"`<br>But Omit --global to set identity only in this repo. <br> Also to get the email and user name that you set <br> configration with just type the previous commands without specifying email or name|
| `git rm -r [file-name.txt]` |Remove a file(or folder)`(--cashed -f)`| 

### Branching & Merging

| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git checkout [branch name]` | Switch to a branch |
| `git checkout -b [branch name]` | Create a new branch and switch to it |
| `git checkout -b [branch name] origin/[branch name]` | Clone a remote branch and switch to it |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git checkout -` | Switch to the branch last checked out |
| `git checkout -- [file-name.txt]` | Discard changes to a file |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git stash` | Stash changes in a dirty working directory |
| `git stash clear` | Remove all stashed entries |

### Sharing & Updating Projects

| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git pull` | Update local repository to the newest commit |
| `git pull origin [branch name]` | Pull changes from remote repository |
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` | Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |

### Inspection & Comparison

| Command | Description |
| ------- | ----------- |
| `git log` | View changes or all commits |
| `git checkout [commit_ID]` | Go back in time to specific commit but notice that you can only look around <br> and make experiamental changes and when you move to another commit <br> or go back to the main commit, means changes you made will no longer exist <br> but if you want at some point to keep them you can create a branch <br> to save these commits in.  |
| `git checkout main [or master]` | Go to the latest commit(the main branch)<br> when you finish your work on a past snapshot you can return back to the main|
| `git log --summary` | View changes (detailed) |
| `git log --oneline` | View changes (briefly) |
| `git diff [source branch] [target branch]` | Preview changes before merging |

### Extra Commands

| Command | Description |
| ------- | ----------- |
| `git revert [commit_ID]` | Creates new commit after deleting all changes in the specified commit <br> but all changes from all commits before and after this commit still exist <br> and if you want to revert this revert you can do the same command to <br> this latest commit created then changes will return back in a new commit |
| `git reset --soft [commit_ID]` | Go back in time to specific commit and all changes comes after <br> become staged(go to staging area waiting to be commit again)<br> This isn't used too much but can be used to spelling checks before commet|
| `git reset --mixed [commit_ID]` | this is the default for `git reset` command and it goes back to specific commit <br> and all changes after this time will return back to the woking directory <br> and this is useful when you commit file by mistake or want to edit file then <br> recommit it  Notice that --soft and --mixed reset don't delete your change <br> they will stay exist in one of stages |
| `git reset --hard [commit_ID]` | Go back in time to specific commit and noway to return from that, it looks like <br> all commits comes after that commit never happen, it will be deleted |
