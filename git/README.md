# Git

## git rebase

_**rebase strategy of Pavel vaia**_

```bash
git checkout dev
git pull
git checkout bugfix/re-add-modal-fix
#remember to rebase your feature branch into protected branch(in our case; dev)
git rebase dev

#if there are conflicts in some files
#read instructions from the terminal and act accordingly

#terimal will give you hints to do the following 
git add .
git rebase --continue

#if there are conflicts in some files
#fix the conflicts and

git add .
git rebase --continue

#go on like this 
#till you have resolved conflicts throughout all the commits of 
#bugfix/re-add-modal-fix and dev

#now that you have resolved conflicts of all the commits
#you are free to commit your changes

git commit -m "rebased dev"
git pull
git push

#you are not done yet
#go to git remote repository to create a pull request
#while creating a pull request, make sure to check 
#1. squash commits
#2. close source branch

#now you are done 
#happy coding!
```

_**My rebase strategy \(ToDo: detail explanation\)**_

```bash
#checkout to your feature branch
$ git checkout my_working_branch

#do your changes, then
$ git add .
$ git commit -m 'my meaningful commit message'

#checkout to master branch and pull 
#the changes your fellow colleagues did
$ git checkout dev
$ git pull

#now checkout to your branch to rebase
$ git checkout my_working_branch
$ git pull --rebase
$ git rebase dev
#now push & make a PR
#make sure to tick on close branch in PR
$ git push
```

_**Reset rebase**_

* [https://opensource.com/article/18/6/git-reset-revert-rebase-commands](https://opensource.com/article/18/6/git-reset-revert-rebase-commands)

```bash
$ git reflog
$ git reset --hard HEAD@{5}
```

## Basics

### git setup

```bash
$ git config --global user.name "NafiAsib"
$ git config --global user.email "nafi.asib@gmail.com"
$ git config --global color.ui true         # enable colored output in terminal
$ git config --global core.editor nvim

# Now setup ssh key
$ cd ~/.ssh
$ ssh-keygen -t rsa -C "nafi.asib@gmail.com" -f "id_rsa_github"

# To confirm
$ ssh -T git@github.com
> Hi NafiAsib! You've successfully authenticated, but Github does
> not provide shell access.

# Deprecated
git config --global credential.helper cache --timeout=3600 # cache password for 3600 second
git config --global credential.helper cache
git config --global --unset credential.helper
git config --global core.editor code      # only in windows
git config --global core.autocrlf true    # only in windows
```

### git dir initialization

```bash
$ git init
$ git add .
$ git commit -m "commit message"
$ git branch -M main
$ git remote add origin repo-link
$ git push -u origin main
```

### remove a file

```bash
$ git rm
```

_**If you want to remove the file from the Git repository and the filesystem**_

```bash
$ git rm file1.txt
$ git commit -m "remove file1.txt"
```

_**But if you want to remove the file only from the Git repository and not remove it from the filesystem**_

```bash
$ git rm --cached file1.txt
$ git commit -m "remove file1.txt"
```

**for directory**

```bash
$ git rm -r dir-name
```

_**And to push changes to remote repo**_

```bash
$ git push origin branch_name
$ git checkout master
$ git fetch upstream
$ git reset --hard upstream/master
$ git push --force
```

[https://stackoverflow.com/questions/1125968/how-do-i-force-git-pull-to-overwrite-local-files](https://stackoverflow.com/questions/1125968/how-do-i-force-git-pull-to-overwrite-local-files)

```bash
Error
fatal: unable to access 'https://github.com/sitndeal/sitndeal.git/': Could
not resolve host: github.com
```

_**Solve**_

```bash
$ git config --global --unset http.proxy
$ git config --global --unset https.proxy
```

_**restart terminal**_

#### git ammend

```bash
$ git commit --amend
```

```bash
$ git pull -> git fetch && git merge
$ git pull --rebase -> git fetch && git rebase
```

#### git squash last X commits

```bash
$ git reset --soft HEAD~X     # last X commits
$ git commit -m "new commit message"
```

_**using interactive rebase**_

```bash
$ git rebase -i HEAD~5
# replace pick to squash to commits you want to squash
```

**very much risky** ⇒ learn more

#### git merge conflicts

```bash
$ git pull dev
$ git checkout feature_branch
$ git pull origin dev
$ git add .
$ git commit -m 'merged message'
$ git push
```

#### fatal: refusing to merge unrelated histories

* reference

  [The “fatal: refusing to merge unrelated histories” Git error](https://www.educative.io/edpresso/the-fatal-refusing-to-merge-unrelated-histories-git-error)

```bash
$ git pull origin master --allow-unrelated-histories
```

#### reset last commit

```bash
$ git reset --soft HEAD~1
```

#### [Switching remote URLs from HTTPS to SSH](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-to-ssh)

```bash
$ git remote -v
> origin  https://github.com/USERNAME/REPOSITORY.git (fetch)
> origin  https://github.com/USERNAME/REPOSITORY.git (push)

$ git remote set-url origin git@github.com:USERNAME/REPOSITORY.git

$ git remote -v
# Verify new remote URL
> origin  git@github.com:USERNAME/REPOSITORY.git (fetch)
> origin  git@github.com:USERNAME/REPOSITORY.git (push)
```



#### Create empty branch

* [StackOverflow answer](https://stackoverflow.com/questions/34100048/create-empty-branch-on-github/55943394)

