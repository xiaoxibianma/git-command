# git常用命令
创建版本库
```
初始化版本库
git init
添加文件到暂存区
git add file.text
提交文件到版本库
git commit -m "add a file"
```
版本回退
```
查看历史记录
git log
简化
git log --pretty=oneline
回到上一个版本
git reset --hard HEAD^
回到指定版本
git reset --hard 版本号
查看命令历史记录
git reflog
```
管理修改
```
查看状态
git status
丢弃工作区的修改
git checkout -- readme.txt
git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。
删除文件
git rm test.txt
查看工作区和版本库里面最新版本的区别
git diff HEAD -- <filename>
```
添加远程仓库
```
连接远程仓库
git remote add origin git@dabeizi.com:root/learngit.git
推送远程库
git push -u origin master
加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
git push origin master
克隆
git clone git@dabiezi.com:root/gitskills.git
```
分支管理
```
创建并切换分支
git checkout -b dev
查看当前分支
git branch
创建分支
git checkout dev
切换分支
git checkout master
合并分支
git merge dev
删除分支
git branch -d dev
查看分支合并情况
git log --graph --pretty=oneline --abbrev-commit
合并分支，不删除分支记录
git merge --no-ff -m "merge with no-ff" dev
保存工作现场
git stash
查找工作现场
git stash list
恢复工作现场
git stash apply
删除工作现场
git stash drop
恢复并删除
git stash pop
git stash apply stash@{0}
强行删除分支
git branch -D dev
查看远程库信息
git remote
详细信息
git remote -v
推送分支
git push origin master
分支开发
git checkout -b dev origin/dev
git push origin dev
建立本地分支与远程的连接
git branch --set-upstream-to=origin/dev dev
拉取最新分支
git pull
```
标签管理
```
为当前分支打标签
git tag v1.0
查看所有标签
git tag
为历史提交打标签
git log --pretty=oneline --abbrev-commit
git tag v0.9 f52c633
查看标签信息
git show v0.9
待说明文字的标签
git tag -a v01 -m "dada" 1094abd
删除标签
git tag -d v0.1
推送标签到远程
git push origin v1.0
推送全部标签
git push origin --tags
删除远程标签
git tag -d v0.9
git push origin :refs/tags/v0.9
```
自定义git
```
忽略特殊文件
https://github.com/github/gitignore
配置别名
git config --global alias.st status
git config --global alias.unstage 'reset HEAD'
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

