# Git

Git command reference.

## Upload all files in a local directory to a new Git repository

If you have a project on your computer and you just created an empty Git repository in GitHub, use these commands to upload everything to Git.

```bash
cd your-directory
git init
git remote add origin git@github.com:your-username/your-repo.git
git add .
git commit -am "Message"
git push -u origin master
```

## Download all files from Git repository to a local directory

The opposite of the above option - for example, if your repository exists in GitHub, and you're working on it in a different local computer. Run this command outside of where you want the new directory to appear (not within the directory you want it to appear).

```bash
git clone git@github.com:your-username/your-repo.git     # using SSH
git clone https://github.com/your-username/your-repo.git # using HTTPS
```

## Remove one file from Git cache

Remove one cached file.

```bash
git rm -r —-cached file.txt
```

## Override entire local directory

If you have some merge conflicts, or accidentally started to make a change to your local directory before pulling the changes from the master, here's how you can revert your local directory to what's on GitHub.

```bash
git fetch --all
git reset --hard origin/master
```

## Ignore a directory

If you've been tracking a directory and later decide to ignore the whole directory, simply adding it to `.gitignore` isn't enough. First you must add the directory to .gitignore, then run this command:

```bash
git rm -r --cached your-directory
```

Then push the changes.

## Add .gitignore to an existing repository

Similar to above, but if you've added a `.gitignore` with a lot of changes.

```bash
git rm -r --cached .
git add .
git commit -m "Message"
```

## Force a push or pull

When you really want your local repository to override the remote.

```bash
git push -f origin master
git pull -f origin master
```

## Merging changes from remote pull request with conflicts

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

## Rename branch

If you have a local clone, you can update it by running the following commands.

```bash
git branch -m master main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a
```

## Remove branch

Put a `:` in front to remove instead of update remotely.

```bash
git push origin :branch-name
```

Use `--delete` or `-D` for local.

```
git branch --delete branch-name
````

## Replace master with contents of another branch

```bash
git checkout branch-name
git merge -s ours master
git checkout master
git merge branch-name
```

## Remove all local branches except master

```bash
git branch | grep -v "master" | xargs git branch -D
```

More than one branch may be added to the grep. To remove all local branches except "master" and "develop":

```bash
git branch | grep -v "master\|develop" | xargs git branch -D
```

 ## Allow empty commit
 
 Fix the problem of git hooks claiming everything is "Up-to-date".
 
 ```bash
 git push production master
 git commit --allow-empty -m 'push to execute post-receive'
 git push production master
 ```
 
 ## Merge new-feature branch into master
 
 Merge branches.

```bash
git checkout master
git pull origin master
git merge new-feature
git push origin master
```

## Switch to branch that exists on origin

```bash
git fetch --prune --all
git checkout other-branch
```

## Fetch branch from origin

```bash
git fetch origin
git checkout --track origin/<remote_branch_name>
```

## Accept all incoming changes

```bash
git pull -Xtheirs
```

## Delete local and remote tag

```bash
git push --delete origin tagName
git tag -d tagName
```

## Rebase from develop

```bash
git fetch --prune --all
git rebase origin/develop
git pull
git push
```

## Stashing

Put your changes away and switch to another branch

```bash
git stash
git checkout -b new-branch
git stash pop
```

## Accidentally committed to develop and want to move that commit to a branch

```bash
git branch new-branch
git reset HEAD~1
git checkout <files>
```

## GitHub pages to non-docs folder

"dist" or whatever you want.

```bash
git subtree push --prefix dist origin gh-pages
```

## Subtree within repo

```bash
git subtree add --prefix <local-dir> https://github.com/taniarascia/<repo> master --squash
git subtree pull --prefix <local-dir> https://github.com/taniarascia/<repo> master --squash
git subtree push --prefix <local-dir> https://github.com/taniarascia/<repo> master --squash
```

## Exiting VIM

For those new to command line, ending up at the commit message screen (often when you forget to the add `-m` flag to a commit) is confusing because pressing escape (or `CTRL` + `C`) does not exit the screen, as the default editor for Git is VIM. Instead, press escape (if you've started attempting to type something) and type the following command:

```bash
:q
```

And press enter, and you'll return to where you were.

# GitHub

## Adding an existing project to GitHub using the command line

### 1. Initialize the local directory as a Git repository.

```
$ git init -b main
```
### 2. Add the files in your new local repository. This stages them for the first commit.

```
$ git add .
```

The code above adds the files in the local repository and stages them for commit. To unstage a file, use **git reset HEAD YOUR-FILE**.

### 3. Commit the files that you've staged in your local repository.

```
$ git commit -m "First commit"
```

The code above commits the tracked changes and prepares them to be pushed to a remote repository. To remove this commit and modify the file, use **git reset --soft HEAD~1** and commit and add the file again.

### 4. At the top of your GitHub repository's Quick Setup page, click to copy the remote repository URL. 

<img src="https://github.com/mnestorov/git-commands/blob/main/RemoteRepositoryUrl.png">

### 5. In the Command prompt, add the URL for the remote repository where your local repository will be pushed.

```
$ git remote add origin  <REMOTE_URL> 
# Sets the new remote
$ git remote -v
# Verifies the new remote URL
```

### 6. Push the changes in your local repository to GitHub.

```
$ git push origin main
```

The code above pushes the changes in your local repository up to the remote repository you specified as the origin.

## Change GitHub branch on local machine when the branch name is changed

```
git branch -m main objects
git fetch origin
git branch -u origin/objects objects
git remote set-head origin -a
```
