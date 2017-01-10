#### Git管理文本文件的改动
git add命令实际上就是把要提交的所有修改放到暂存区（Stage），然后，执git
commit就可以一次性把暂存区的所有修改提交到分支。

- `> git init`  把当前目前变成仓库
- `> git add readme.txt`  把文件readme.txt添加到仓库
- `> git commit -m "wrote a readme file"`   把文件提交到仓库
- - `> git commit -a"`   自动把跟踪文件提交到仓库
- `> git status `   查看当前修改情况
- `> git diff readme.txt`   查看readme.txt文件修改内容
- `> git log`   查看历史
- `HEAD` 表示当前版本
- `HEAD^` 表示上一个版本
- `HEAD^^` 表示上上一个版本
- `HEAD~100` 表示上100个版本
- `> git reset --hard HEAD^` 回退到上一个版本
- `> git reset --hard 468` 回退到468版本
- `> git reset HEAD readme.txt`
- git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区
- git reset HEAD file可以把暂存区的修改撤销掉（unstage），重
  新放回工作区：
- `> git reflog`    查看记录的每一次命令
- `> git checkout --readme.txt` 丢弃修改，回到最一次git commit或git add时的状态
- git checkout -- file命令中的“--”很重要，没有“--”，就变成了“创建一个新分支”的命
  令

- `> git rm test.txt`   从版本库中删除test.txt文件


##### 推送到远程仓库
```git
…or create a new repository on the command line

echo "# AsCall" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:oncechen/HeyOnce.git
git push -u origin master
```

```git
…or push an existing repository from the command line

git remote add origin git@github.com:oncechen/HeyOnce.git
git push -u origin master
```
- `> -u`   远程仓库是空里加-u,后续的推送或拉取可简化命令
- `> git push origin mastert`   后续提交

##### 从远程仓库克隆

```
git@github.com:oncechen/HeyOnce.git
```

##### 分支管理
- `> git checkout -b OtherMastert`   创建新分支OtherMastert，并切换
- `> git branch OtherMastert`
- `> git checkout OtherMastert`

- `> git branch`    查看当前分支，当前分支会加*标识
- `> git checkout mastert`    切换到mastert分支
- `> git merge OtherMastert` 合并分支（OtherMastert分支并到当前分支）
- `> git branch -d OtherMastert` 删除分支OtherMastert
- `> git branch -D OtherMastert` 强行删除分支OtherMastert

##### 推送分支
- `> git push origin master` 推送master分支
- `> git push origin dev` 推送dev分支

##### 标签管理
- `> git tag v1.0`  创建标签
- `> git tag `  查看标签
- `> git tag -d v1.0`  删除标签
- `> git push origin v1.0`  推送标签
- `> git push origin --tags`  一次性推送标签





id_rsa: 私密
id_pub：公密
