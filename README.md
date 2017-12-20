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



### 查看日志

### git log
> 显示提交历史，按q键退出

### git log -3
> 显示最近3条提交日志

### git log --pretty=oneline
> 一行的格式显示日志

### git log --pretty=format:"%h - %an, %ar : %s"
> 格式化输出日志













