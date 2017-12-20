## Git常用命令

### 基础命令
### git init
> 初始化一个空的仓库

### git status
> 查看git状态, 查看哪些文件没有提交。

### git config --global user.name "wujinqing"
> 设置提交的用户名

### git config --global user.email "wujinqing@aliyun.com"
> 设置提交的邮箱

> git config --system 系统级别的，优先级最低

> git config --global，当前用户空间的所有项目，优先级次之

> git config --local 针对于特定项目，优先级最高

### git config --global alias.br branch
> 创建别名 git br 等价于 git branch

> git config --global alias.br branch

> git config --global alias.st status

> git config --global alias.co checkout

### cat ~/.gitconfig
> 查看通过git config --global设置的配置信息



### git clone git@github.com:wujq4git/gitlecture.git
> 将代码克隆到默认的gitlecture目录下

### git clone git@github.com:wujq4git/gitlecture.git mydest
> 将代码克隆到指定的文件夹mydest里面



### 分支

### git branch
> 查看分支

### git branch new_branch
> 创建一个新的分支

### git checkout new_branch
> 切换分支

### git checkout –
> 切换到上一个分支

### git branch -d new_branch
> 删除一个分支前提是这个分支和主分支的内容一样，如果不一样，先合并分支，否则无法删除

### git branch -D new_branch
> 强制删除一个分支就算这个分支的内容没有合并，也会删除

### git checkout -b new_branch3
> 创建一个分支，并切换到该分支, 相当于执行了下面两个操作

> git branch new_branch3

> git checkout new_branch3

### git merge new_branch4
> 合并分支，将指定的分支合并到当前分支

### git branch –v
> 显示当前分支最近一次提交的信息，包括commit id, commit message

### git branch -m master master2
> 修改分支名称

### git checkout -b develop origin/develop
> 创建并切换一个分支develop，并且这个分支会追踪远程的origin/develop分支

### git push -u origin test
> 在远程创建一个分支，并将本地分支追踪这个远程分支，与git push --set-upstream origin develop作用类似（推荐使用set-upstream）

### git checkout -b test2 origin/test
> 在本地分支创建不一样的分支去追踪远程分支

### git checkout --track origin/test
> 创建一个和远程分支名字相同的分支来追踪远程分支

### git push origin :develop
> 删除远程分支develop

### git push origin --delete develop
> 删除远程分支develop

### git push --set-upstream origin develop
创建一个远程分支develop

### git checkout --track origin/mymaster
> 创建一个同名的本地分支去追踪未被追踪的远程分支

### git branch --unset-upstream
> 由于远程分支已经被删除，取消本地分支与远程分支的关联关系

### git checkout commit_id
> 基于某个commit_id新建分支

### git checkout tag_name
> 基于某个标签tag_name新建分支

### git commit -am 'this is commit message'
> 直接将当前目录下的所有修改进行提交, 相当于同时执行git add .和 git commit两个命令


### 版本回退


### git reset --hard HEAD^
> 回退到上一个版本

### git reset --hard HEAD^^
> 回退到上上个版本

### git reset --hard b0f2c
> 回退到指定commit id的版本

### git checkout -- test2.txt
> 针对工作区, 作用是：丢弃掉相当于暂存区中最后一次添加的文件内容所做的变更，会丢弃掉在工作区且为纳入到暂存区的修改。

### git reset HEAD test2.txt
> 针对暂存区（stage, index）, 作用是：将之前添加到暂存区的内容从暂存区移除到工作区

### git checkout c6ac
> 回退到指定commit id的版本，此时处于游离状态（detached）


### 查看日志

### git log
> 显示提交历史，按q键退出

### git log -3
> 显示最近3条提交日志

### git log --pretty=oneline
> 一行的格式显示日志

### git log --pretty=format:"%h - %an, %ar : %s"
> 格式化输出日志

### git reflog
> 显示操作日志，当不记得最新的commit id时可以通过这个命令查看到

### git log origin/master
> 查看远程分支的日志

### 保存工作现场
> 应用场景：当前分支的任务进行到一半，想切换到其他分支，又不想提交代码，就可以先保存工作现场。

### git stash
> 保存工作现场

### git stash list
> 查看已保存的工作现场列表

### git stash pop
> 恢复最近一次报存的工作现场

### 标签
> 每发布一个版本都需要打上一个标签。
> 标签与分支无关，在某个分支上加了标签，在其他所有分支上也能查看到这个分支

### git tag v1.0
> 打标签，没有相关说明

### git tag -a v2.0 -m 'v2.0 released'
> 打标签, 并有相关说明

### git show v1.0
> 显示标签的信息

### git tag -d tag_name
> 删除一个标签

### git push origin v1.0
> 将一个标签推送到远程

### git push v2.0 v3.0
> 将多个标签推送到远程

### git push origin –tags
> 将所有未提交的标签推送到远程

### git push origin :refs/tags/tag_name
> 删除远程标签

> git pull会把标签拉取下来

### git push origin :refs/tags/v1.0
> 删除远程标签

### git push origin --delete tag v2.0
> 删除远程标签

### git 重命名远程分支只有一种办法：
> 1.删除远程分支

> 2.重命名本地分支

> 3.将本地分支推送到远程


### 远程仓库
### git remote add origin git@github.com:wujq4git/gitlecture.git
> 添加一个远程仓库

### git remote rename origin origin2
> 重命名远程仓库

### git remote rm origin
> 删除一个远程仓库

### git remote show origin
> 参考远程仓库(分支)状态信息

### 其他
### git remote prune origin
> 清除已被其他人删除的远程分支的本地信息

### git cherry-pick commit_id
> 将另一个分支的提交应用到当前分支



















