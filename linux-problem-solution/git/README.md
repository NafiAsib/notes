# Git

## Basics

* **git setup**

```bash
git config --global user.name "NafiAsib"
git config --global user.email "nafi.asib@gmail.com"
git config --global color.ui true # enable colored output in terminal
git config --global core.editor nvim

# ↓ OLD
# git config --global credential.helper cache --timeout=3600 # cache password for 3600 second
# git config --global credential.helper cache
# git config --global --unset credential.helper
# git config --global core.editor code      # only in windows
# git config --global core.autocrlf true    # only in windows
```

* **SSH key**

```bash
cd ~/.ssh
ssh-keygen -t rsa -C "nafi.asib@gmail.com" -f "id_rsa_github"
# -t rsa ⇒ Specifies the type of key to create. In this case, it's rsa
# -C ⇒ comment
# -f ⇒ filename
```

Now copy the content of `id_rsa_github.pub` and set as SSH key in GitHub.

You can confirm that SSH is okay by typing `ssh -T git@github.com`

If you see following message, you're done!

```bash
Hi NafiAsib! You've successfully authenticated, but Github does
not provide shell access.
```

* **git directory initialization**

```bash
git init
git add .
git commit -m "commit message"
git branch -M main # change default branch to main from master
git remote add origin repo-link # https link of remote directory
git push -u origin main
```

* **remove a file**

```bash
git rm file-name # from both git and locally
git rm --cached file-name # from only git
git rm -r directory-name # directory
# commit and push
```

#### &#x20;reset last commit

```bash
$ git reset --soft HEAD~1
```

#### git merge conflicts

To solve merge conflict between two branch, first pull the other branch in your working branch. Then merge all conflict and push. It's better to squash your commits to make the commit tree clean.

```bash
$ git pull dev # dev is the already pushed branch
$ git checkout feature_branch # working branch
$ git pull origin dev
# fix all merge conflict
$ git add .
$ git commit -m 'merged message'
$ git push
```

#### git squash last X commits

```bash
$ git reset --soft HEAD~X     # last X commits
$ git commit -m "new commit message"
```

_**Reset rebase**_

* [How to reset, revert, and return to previous states in Git](https://opensource.com/article/18/6/git-reset-revert-rebase-commands)

```bash
$ git reflog
$ git reset --hard HEAD@{5}
```

#### git ammend

* [git commit --amend and other methods of rewriting history](https://www.atlassian.com/git/tutorials/rewriting-history)

```bash
$ git commit --amend # prompt editor to change most recent Git commit message
$ git commit --amend -m "an updated commit message" # doesn't prompt editor
```

_**using interactive rebase**_

```bash
$ git rebase -i HEAD~5
# replace pick to squash to commits you want to squash
```

## Errors & fix

*

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



### [Switching remote URLs from HTTPS to SSH](https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-to-ssh)

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

### Links

* [Force git pull to overwrite local files](https://stackoverflow.com/questions/1125968/how-do-i-force-git-pull-to-overwrite-local-files)
* [Create empty branch](https://stackoverflow.com/questions/34100048/create-empty-branch-on-github/55943394)
* [ssh-keygen man page](https://man7.org/linux/man-pages/man1/ssh-keygen.1.html)
*   [merge unrelated histories](https://www.educative.io/edpresso/the-fatal-refusing-to-merge-unrelated-histories-git-error)

    ```bash
    $ git pull origin master --allow-unrelated-histories
    ```
*   **Misc**

    ```bash
    git pull == git fetch && git merge
    git pull --rebase == git fetch && git rebase
    ```



#### Resources

* Read through chapter 1 \~ 3 of [Pro Git book](https://git-scm.com/book/en/v2)
* [Learn Git Branching](https://learngitbranching.js.org/) - Interactive website to learn git branching in depth
* [Make atomic git commits](https://www.aleksandrhovhannisyan.com/blog/atomic-git-commits/) -&#x20;
* [How to Write a Git Commit Message](https://cbea.ms/git-commit/#imperative) - Try to use imperative git messages
* [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) - Too many perks to ignore
* [A Visual Guide to Git Internals — Objects, Branches, and How to Create a Repo From Scratch](https://www.freecodecamp.org/news/git-internals-objects-branches-create-repo/)
