* [集中式与分布式](#集中式与分布式)
* [SSH 传输设置](#SSH-传输设置)
* [工作流](#工作流)
* [版本回退](#版本回退)
* [管理修改](#管理修改)
* [撤销修改](#撤销修改)
* [删除文件](#删除文件)
* [创建与合并分支](#创建与合并分支)
* [.gitignore 文件](#gitignore-文件)
* [参考资料](#参考资料)

# 集中式与分布式

SVN是集中式版本控制系统，Git是分布式版本控制系统。

集中式版本控制系统：版本库集中存放在中央服务器，需要联网才能工作。

集中式版本控制系统：存在很大的安全问题，一旦中央服务器故障，所有人都没法工作。

集中式版本控制系统：创建一个分支相当于复制了一份完整代码，速度慢。

分布式版本控制系统：版本库存放在每个人的电脑里，没有联网也能工作。

分布式版本控制系统：新建分支、合并分支的操作只需要修改指针，速度非常快。


# SSH 传输设置

# 工作流
新建一个仓库之后，当前目录就成为了工作区，工作区下有一个隐藏目录 .git，它属于 Git 的版本库。
<div align="center"> <img src="pics/版本库.jpg"/> </div><br>
Git 版本库中有一个称为 stage 的暂存区，还有自动创建的 master 分支以及指向分支的 HEAD 指针。

- git add files 把文件修改添加到暂存区
- git commit   把暂存区的所有内容提交到当前分支
- git commit -a   直接把所有文件的修改添加到暂存区然后执行提交

# 版本回退
- git log 命令显示从最近到最远的提交日志
- git log --pretty=online 精简日志信息

在 Git 中， HEAD 表示当前版本，上一个版本就是 HEAD^，上上个版本就是 HEAD^^，上上上个版本就是 HEAD~3

回退到上一个版本可以使用 git reset 命令
- git reset --hard HEAD^

# 撤销修改

# 管理修改
Git 比其他版本控制系统设计的更优秀的原因：跟踪并管理的是修改，而非文件。
- git diff HEAD -- files 查看工作区和版本库最新版本的区别
# 删除文件
- git rm files 从暂存区中删除文件
- git checkout -- files 从暂存区中恢复文件到工作区

# 创建与合并分支
- git branch 查看分支
- git branch <name> 创建分支
- git checkout <name> 切换分支
- git checkout -b <name> 创建+切换分支
- git merge <name> 合并某分支到当前分支
- git branch -d <name> 删除分支
# .gitignore 文件
该文件可以到 [https://github.com/github/gitignore](https://github.com/github/gitignore) 中进行查询。

# 参考资料

- [廖雪峰 : Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)