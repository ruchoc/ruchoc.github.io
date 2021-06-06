---
title: git常用命令
date: 2021-06-04 16:08:48
tags:
---
# BASIC

git init \<directroy\> 初始化

git clone \<repo\> 克隆指定的repo到本地，repo可以是SSH或HTTP

git add \<directory\> 将目录下的所有修改加入到下一次commit中，把\<directory>换成\<file\>将添加指定文件的修改

git commit -m"\<message\>" 提交暂存区的修改，使用指定的\<message\>作为提交信息，而不是打开文本编辑器输入提交信息

git status 显示哪些文件已被staged、未被staged以及为跟踪(untracked)

git log 以缺省格式显示全部commit历史

# DIFF

git diff 比较工作区和暂存区的修改

git diff HEAD 比较工作区与上一次commit后的修改

git diff --cached 比较暂存区和上一次commit后的修改，与--staged参数作用一样

git diff HEAD~X或git diff HEAD\^\^\^...(共有X个\^符号，X为正整数)可以比较最近一次提交的版本与前X次提交的版本

git diff \<commit1\> \<commit2\> 可以比较两个commit

# UNDOING CHANGES

git restore --worktree \<file\> 撤销工作区的\<file\>的修改，--worktree为默认参数

git restore --staged \<file\> 将\<file\>从暂存区移除，但保持工作区不变，此操作不会修改工作区的任何文件

git reset --hard 移除所有暂存区的修改，并强制删除所有工作区的修改，去掉--hard即不会改变工作区，以下同理

git reset --hard \<commit\> 将当前分支回滚到指定\<commit\>，清除暂存区的修改

git reset --hard HEAD~X或git reset --hard HEAD\^\^\^...(共有X个\^符号，X为正整数)回退到前X个提交的版本

# BRANCHS

git branch -a 显示所有分支，去掉-a显示本地分支，换成-r参数显示远程分支

git branch -m \<oldbranch\> \<newbranch\> 本地分支重命名

git switch -c \<branch\> 创建并切换到一个新的名为\<branch\>的分支，去掉-c参数将切换到一个已有分支

git merge \<branch\> 将指定\<branch\>分支合并到当前分支

git branch --set-upstream-to=\<remote\>/\<remote_branch\> \<local_branch\> 本地分支关联远程分支

# REMOTE

git remote -v 显示本地添加了哪些远程连接，-v参数代表详细

git remote remove \<remote\> 删除本地指定远程连接

git remote add \<name\> \<url\> 添加一个新的远程连接，添加后可使用\<name\>作为指定\<url\>远程连接的名称

# LOG

git log -\<limit\> 限制log的显示数量，eg：git log -5 仅显示最新的5条commit

git log --oneline 每行显示一条commit

git log --author="\<pattern\>" 按提交者名字搜索并显示commit

git log -- \<file\> 仅显示包含指定文件修改的commit

git log --graph 使用--graph参数显示图形化的branch信息

git reflog 查看命令历史，回退后需要反悔的话，需要通过此命令查找到所有操作的提交点

# PUSH&PULL

git push \<远程主机名\> \<本地分支名\>:\<远程分支名\> 将本地的分支版本上传到远程并合并，如果本地分支名与远程分支名相同，则可以省略冒号

git push --force \<远程主机名\> \<远程分支名\> 若本地与远程有差异，但又要强制推送可以使用--force参数进行覆盖

git push \<远程主机名\> --delete \<远程分支名\> 删除远程分支

git pull \<远程主机名\> \<远程分支名\>:\<本地分支名\> 从远程获取代码并合并本地的版本，同上，名字相同时冒号可以省略