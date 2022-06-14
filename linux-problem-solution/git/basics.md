# basics

```bash
git commit -am 'commit-message' # == git add . && git commit -m 'commit-message'
```

#### Edit last commit message

```bash
git commit --ammend -m 'edited commit message'
```

#### Update last commit with new file and commit

```
git add .
git commit --ammend --no-edit
```

#### git revert allows to go back one commit&#x20;

git log --graph --oneline --decorate

#### hard reset to remote git repo

```bash
git fetch origin
git reset --hard origin/master
git clean df
```



#### Resources

* [13 Advanced (but useful) Git Techniques and Shortcuts](https://www.youtube.com/watch?v=ecK3EnyGD8o) - Fireship
