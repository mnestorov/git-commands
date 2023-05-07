# Git Commands

These advanced Git commands and techniques will help you take your Git skills to the next level, allowing you to more effectively manage and collaborate on complex code projects.

## Setting up Git

- [Configure your name and email](#configure-your-name-and-email)

## Basic Git Commands

- [Initialize a new Git repository](#initialize-a-new-git-repository)
- [Clone a remote repository](#clone-a-remote-repository)
- [Check the status of your repository](#check-the-status-of-your-repository)
- [Stage files for commit](#stage-files-for-commit)
- [Stage all files in the repository for commit](#stage-all-files-in-the-repository-for-commit)
- [Commit staged files with a message](#commit-staged-files-with-a-message)
- [Show the commit history](#show-the-commit-history)
- [Show the commit history in a graph format](#show-the-commit-history-in-a-graph-format)
- [Show the differences between the working directory and the last commit](#show-the-differences-between-the-working-directory-and-the-last-commit)

## Branching and Merging

- [List all branches](#list-all-branches)
- [Create a new branch](#create-a-new-branch)
- [Switch to a different branch](#switch-to-a-different-branch)
- [Create and switch to a new branch in one command](#create-and-switch-to-a-new-branch-in-one-command)
- [Merge a branch into the current branch](#merge-a-branch-into-the-current-branch)
- [Delete a branch](#delete-a-branch)

## Remote Repositories

- [Show a list of remote repositories](#show-a-list-of-remote-repositories)
- [Add a remote repository](#add-a-remote-repository)
- [Fetch changes from a remote repository](#fetch-changes-from-a-remote-repository)
- [Pull changes from a remote repository and merge them into the current branch](#pull-changes-from-a-remote-repository-and-merge-them-into-the-current-branch)
- [Push changes to a remote repository](#push-changes-to-a-remote-repository)
- [Remove a remote repository](#remove-a-remote-repository)

## Stashing

- [Stash changes in the working directory](#stash-changes-in-the-working-directory)
- [Apply the latest stashed changes](#apply-the-latest-stashed-changes)
- [Apply a specific stash](#apply-a-specific-stash)
- [Drop a specific stash](#drop-a-specific-stash)
- [List all stashes](#list-all-stashes)

## Tagging

- [List all tags](#list-all-tags)
- [Create a new tag](#create-a-new-tag)
- [Push tags to a remote repository](#push-tags-to-a-remote-repository)

## Undoing and Reverting

- [Unstage a file](#unstage-a-file)
- [Revert changes in a file to the last commit](#revert-changes-in-a-file-to-the-last-commit)
- [Revert a commit (creates a new commit that undoes the changes)](#revert-a-commit-creates-a-new-commit-that-undoes-the-changes)
- [Reset the working directory to a specific commit](#reset-the-working-directory-to-a-specific-commit)

## Other Commands for BitBucket / GitHub / GitLab

- [Upload all files in a local directory to a new Git repository](#upload-all-files-in-a-local-directory-to-a-new-git-repository)
- [Download all files from Git repository to a local directory](#download-all-files-from-git-repository-to-a-local-directory)
- [Remove one file from Git cache](#remove-one-file-from-git-cache)
- [Override entire local directory](#override-entire-local-directory)
- [Ignore a directory](#ignore-a-directory)
- [Add gitignore to an existing repository](#add-gitignore-to-an-existing-repository)
- [Force a push or pull](#force-a-push-or-pull)
- [Merging changes from remote pull request with conflicts](#merging-changes-from-remote-pull-request-with-conflicts)
- [Rename branch](#rename-branch)
- [Remove branch](#remove-branch)
- [Replace master with contents of another branch](#replace-master-with-contents-of-another-branch)
- [Remove all local branches except master](#remove-all-local-branches-except-master)
- [Allow empty commit](#allow-empty-commit)
- [Merge new-feature branch into master](#merge-new-feature-branch-into-master)
- [Switch to branch that exists on origin](#switch-to-branch-that-exists-on-origin)
- [Fetch branch from origin](#fetch-branch-from-origin)
- [Accept all incoming changes](#accept-all-incoming-changes)
- [Delete local and remote tag](#delete-local-and-remote-tag)
- [Rebase from develop](#rebase-from-develop)
- [Stashing](#stashing)
- [Accidentally committed to develop and want to move that commit to a branch](#acidentally-committed-to-develop-and-want-to-move-that-commit-to-a-branch)
- [Subtree within repo](#subtree-within-repo)
- [Exiting VIM](#exiting-vim)

## GitHub Specific Commands

- [GitHub pages to non-docs folder](#github-pages-to-non-docs-folder)

---

## Setting up Git

### Configure your name and email

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Basic Git Commands

### Initialize a new Git repository

```
git init
```

### Clone a remote repository

```
git clone https://github.com/user/repo.git
```

### Check the status of your repository

```
git status
```

### Stage files for commit

```
git add file_name
```

### Stage all files in the repository for commit

```
git add .
```

### Commit staged files with a message

```
git commit -m "Commit message"
```

### Show the commit history

```
git log
```

### Show the commit history in a graph format

```
git log --graph --oneline --decorate
```

### Show the differences between the working directory and the last commit

```
git diff
```

## Branching and Merging

### List all branches

```
git branch
```

### Create a new branch

```
git branch new_branch
```

### Switch to a different branch

```
git checkout branch_name
```

### Create and switch to a new branch in one command

```
git checkout -b new_branch
```

### Merge a branch into the current branch

```
git merge branch_name
```

### Delete a branch

```
git branch -d branch_name
```

## Remote Repositories

### Show a list of remote repositories

```
git remote -v
```

### Add a remote repository

```
git remote add remote_name https://github.com/user/repo.git
```

### Fetch changes from a remote repository

```
git fetch remote_name
```

### Pull changes from a remote repository and merge them into the current branch

```
git pull remote_name branch_name
```

### Push changes to a remote repository

```
git push remote_name branch_name
```

### Remove a remote repository

```
git remote rm remote_name
```

## Stashing

### Stash changes in the working directory

```
git stash
```

### Apply the latest stashed changes

```
git stash apply
```

### Apply a specific stash

```
git stash apply stash@{stash_number}
```

### Drop a specific stash

```
git stash drop stash@{stash_number}
```

### List all stashes

```
git stash list
```

## Tagging

### List all tags

```
git tag
```

### Create a new tag

```
git tag -a tag_name -m "Tag message"
```

### Push tags to a remote repository

```
git push remote_name --tags
```

## Undoing and Reverting

### Unstage a file

```
git reset HEAD file_name
```

### Revert changes in a file to the last commit

```
git checkout -- file_name
```

### Revert a commit (creates a new commit that undoes the changes)

```
git revert commit_hash
```

### Reset the working directory to a specific commit

**WARNING:** This will discard all uncommitted changes

```
git reset --hard commit_hash
```
## Other Commands for BitBucket / GitHub / GitLab

### Upload all files in a local directory to a new Git repository

If you have a project on your computer and you just created an empty Git repository in GitHub, use these commands to upload everything to Git.

```bash
cd your-directory
git init
git remote add origin git@github.com:your-username/your-repo.git
git add .
git commit -am "Message"
git push -u origin master
```

### Download all files from Git repository to a local directory

The opposite of the above option - for example, if your repository exists in GitHub, and you're working on it in a different local computer. Run this command outside of where you want the new directory to appear (not within the directory you want it to appear).

```bash
git clone git@github.com:your-username/your-repo.git     # using SSH
git clone https://github.com/your-username/your-repo.git # using HTTPS
```

### Remove one file from Git cache

Remove one cached file.

```bash
git rm -r —-cached file.txt
```

### Override entire local directory

If you have some merge conflicts, or accidentally started to make a change to your local directory before pulling the changes from the master, here's how you can revert your local directory to what's on GitHub.

```bash
git fetch --all
git reset --hard origin/master
```

### Ignore a directory

If you've been tracking a directory and later decide to ignore the whole directory, simply adding it to `.gitignore` isn't enough. First you must add the directory to .gitignore, then run this command:

```bash
git rm -r --cached your-directory
```

Then push the changes.

### Add gitignore to an existing repository

Similar to above, but if you've added a `.gitignore` with a lot of changes.

```bash
git rm -r --cached .
git add .
git commit -m "Message"
```

### Force a push or pull

When you really want your local repository to override the remote.

```bash
git push -f origin master
git pull -f origin master
```

### Merging changes from remote pull request with conflicts

Make a new branch with their changes.

```bash
git checkout -b their-branch master
git pull their.git master
```

Play with the files and commit them.    

```bash
git add files
git commit -m “Message"
git push origin master
```

Merge back into your branch.  

```bash
git checkout master
git merge --no-ff <their-branch) (:wq!)
git push origin master
```

### Rename branch

If you have a local clone, you can update it by running the following commands.

```bash
git branch -m master main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a
```

### Remove branch

Put a `:` in front to remove instead of update remotely.

```bash
git push origin :branch-name
```

Use `--delete` or `-D` for local.

```
git branch --delete branch-name
````

### Replace master with contents of another branch

```bash
git checkout branch-name
git merge -s ours master
git checkout master
git merge branch-name
```

### Remove all local branches except master

```bash
git branch | grep -v "master" | xargs git branch -D
```

More than one branch may be added to the grep. To remove all local branches except "master" and "develop":

```bash
git branch | grep -v "master\|develop" | xargs git branch -D
```

 ### Allow empty commit
 
 Fix the problem of git hooks claiming everything is "Up-to-date".
 
 ```bash
 git push production master
 git commit --allow-empty -m 'push to execute post-receive'
 git push production master
 ```
 
 ### Merge new-feature branch into master
 
 Merge branches.

```bash
git checkout master
git pull origin master
git merge new-feature
git push origin master
```

### Switch to branch that exists on origin

```bash
git fetch --prune --all
git checkout other-branch
```

### Fetch branch from origin

```bash
git fetch origin
git checkout --track origin/<remote_branch_name>
```

### Accept all incoming changes

```bash
git pull -Xtheirs
```

### Delete local and remote tag

```bash
git push --delete origin tagName
git tag -d tagName
```

### Rebase from develop

```bash
git fetch --prune --all
git rebase origin/develop
git pull
git push
```

### Stashing

Put your changes away and switch to another branch

```bash
git stash
git checkout -b new-branch
git stash pop
```

### Accidentally committed to develop and want to move that commit to a branch

```bash
git branch new-branch
git reset HEAD~1
git checkout <files>
```

### Subtree within repo

```bash
git subtree add --prefix <local-dir> https://github.com/taniarascia/<repo> master --squash
git subtree pull --prefix <local-dir> https://github.com/taniarascia/<repo> master --squash
git subtree push --prefix <local-dir> https://github.com/taniarascia/<repo> master --squash
```

### Exiting VIM

For those new to command line, ending up at the commit message screen (often when you forget to the add `-m` flag to a commit) is confusing because pressing escape (or `CTRL` + `C`) does not exit the screen, as the default editor for Git is VIM. Instead, press escape (if you've started attempting to type something) and type the following command:

```bash
:q
```

And press enter, and you'll return to where you were.

## GitHub Specific Commands

### Adding an existing project to GitHub using the command line

1. Initialize the local directory as a Git repository.

```
$ git init -b main
```

2. Add the files in your new local repository. This stages them for the first commit.

```
$ git add .
```

The code above adds the files in the local repository and stages them for commit. To unstage a file, use **git reset HEAD YOUR-FILE**.

3. Commit the files that you've staged in your local repository.

```
$ git commit -m "First commit"
```

The code above commits the tracked changes and prepares them to be pushed to a remote repository. To remove this commit and modify the file, use **git reset --soft HEAD~1** and commit and add the file again.

4. At the top of your GitHub repository's Quick Setup page, click to copy the remote repository URL. 

<img src="https://github.com/mnestorov/git-commands/blob/main/RemoteRepositoryUrl.png">

5. In the Command prompt, add the URL for the remote repository where your local repository will be pushed.

```
$ git remote add origin  <REMOTE_URL> 
# Sets the new remote
$ git remote -v
# Verifies the new remote URL
```

6. Push the changes in your local repository to GitHub.

```
$ git push origin main
```

The code above pushes the changes in your local repository up to the remote repository you specified as the origin.

### Change GitHub branch on local machine when the branch name is changed

```
git branch -m main objects
git fetch origin
git branch -u origin/objects objects
git remote set-head origin -a
```

### GitHub pages to non-docs folder

"dist" or whatever you want.

```bash
git subtree push --prefix dist origin gh-pages
```

### Git Workflow

```
git checkout main
git pull origin main
git checkout -b <new branch name here>
git status
git add themes/.../header.php # add only this file for commit
git add . # add all changed files
git commit -m "Commit message"
git push origin <branch name>
```

---

## License

This project is released under the MIT License.
