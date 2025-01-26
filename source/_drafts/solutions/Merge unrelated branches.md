(Stackoverflow)[https://stackoverflow.com/questions/37937984/git-refusing-to-merge-unrelated-histories-on-rebase]

### Backgrounds
本地和远程仓库的主分支不同（master main）,导致新建远程仓库后拉取合并到本地会报错。
```sh
git merge master
# fatal: refusing to merge unrelated histories
```

### Solution
```sh
git merge master --allow-unrelated-histories
```

