# merging strategy

## git rebase

{% hint style="info" %}
Recommended by Alif Arfab
{% endhint %}

```bash
$ git checkout dev
$ git pull
$ git checkout bugfix/re-add-modal-fix
#remember to rebase your feature branch into protected branch(in our case; dev)
$ git rebase dev

#if there are conflicts in some files
#read instructions from the terminal and act accordingly

#terimal will give you hints to do the following 
$ git add .
$ git rebase --continue

#if there are conflicts in some files
#fix the conflicts and

$ git add .
$ git rebase --continue

#go on like this 
#till you have resolved conflicts throughout all the commits of 
#bugfix/re-add-modal-fix and dev

#now that you have resolved conflicts of all the commits
#you are free to commit your changes

$ git commit -m "rebased dev"
$ git pull
$ git push

#you are not done yet
#go to git remote repository to create a pull request
#while creating a pull request, make sure to check 
#1. squash commits
#2. close source branch

#now you are done 
#happy coding!
```

_**My rebase strategy (TODO: detail explanation with branch tree)**_

```bash
#checkout to feature branch
$ git checkout feature-branch

#do changes, then
$ git add .
$ git commit -m 'meaningful commit message'

#checkout to master branch and pull 
#the changes
$ git checkout dev
$ git pull

#now checkout to feature branch to rebase
$ git checkout feature-branch
$ git pull --rebase
$ git rebase dev

#now push & make a PR
#make sure to tick on close branch in PR
$ git push
```
