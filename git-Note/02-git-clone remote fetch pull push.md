##### learning Git cmd

- git clone

- git remote

- git fetch

- git pull

- git push

#####  管理版本和合并
- 从本地分支中新建一个分支：
```shell
git checkout -b branchWrite
```

- 在branchWrite分支上add、commit:
```shell
git add .
git commit -m 'Note'
```

- 从本地合并到远程：
```shell
# 查看远程所有主机名
git remote
# 查看所有远程主机名对应的网址
git remote -v
# 查看远程分支
git branch -r
# 查看远程所有分支
git branch -a
# 本地当前分支向远程分支合并
git merge <远程分支>
-----------------------------
# 用git pull 方法从本地分支向远程分支合并，本地更新了
# 合并到当前分支时，:<本地分支名>可省略 
git pull <远程主机名> <远程分支名>:<本地分支名>

# 推送更新后的本地分支，远程更新了
git push <远程主机名> <本地分支名>:<远程分支名>

# 删除远程分支名，2种方法
git push <远程主机名> :<远程分支名>
git push --delete <远程分支名>

# 将本地的所有分支都推送到远程主机
git push --all <远程主机名>

# 将本地的所有分支都强制推送到远程主机
git push --force <远程主机名>

```






