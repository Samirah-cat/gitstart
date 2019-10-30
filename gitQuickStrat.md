# Dev2 Maintenance Tutorial

## Goal 
- 如何在linux上进行问题分析
- java命令及工具的初步了解和掌握
## install
- https://gitforwindows.org/
```
> git config --global user.name "bao"
> git config --global user.email "124335728@qq.com"
#检查信息是否写入成功
> git config --list 

git config --global i18n.commitencoding utf-8
git config --global i18n.logoutputencoding utf-8

export LESSCHARSET=utf-8 ## linux bash配置环境变量
set LESSCHARSET=utf-8 #windows配置环境变量
```
## Structure
![image](https://note.youdao.com/yws/public/resource/7c18d614a76e9fcc62525c32e12b1969/xmlnote/462C7807CA734F49B7AE428D515DABBA/744)

- Working Directory：平时存放项目代码的地方。
- Stage：临时存放你的改动，事实上它只是一个文件，保存即将提交的文件列表信息。
- Repository：提交的所有版本的数据。其中，HEAD 指向最新放入仓库的版本。

## Getting and Creating Projects
#### init
- git-init - Create an empty Git repository or reinitialize an existing one
#### clone
- git-clone - Clone a repository into a new directory
```
# 初始化Git项目，成功后创建有一个.git隐藏文件
F:\MyProject>git init
# 拷贝项目
F:\MyProject2>git clone https://github.com/mihumouse/Java-Mock-Testing-Notes
```
## Basic Snapshotting
#### status
- Description: Show the working tree

#### log
- Description: Show commit logs
- git log --graph --oneline --decorate --all: 以图像形式展示提交历史的分支结构
#### add
- Description: Add file contents to the index
- git add . 将当前目录下修改的所有代码从工作区添加到暂存区 . 代表当前目录

#### commit
- Description: Record changes to the repository
- git commit -m "some commit log..."
- git commit -am "some commit log...": 从工作目录一步添加到仓库
- git commit --amend -m "": “更正”最近一次的提交

#### rm

- Description: Remove files from the working tree and from the index

- git remove  文件名: 命令删除的只是工作目录和暂存区域的文件（即取消跟踪，在下次提交时不纳入版本管理）
- 如果想彻底删除，将快照回滚到上一个位置再提交（git reset --soft HEAD~)
- git rm --cached 文件名: 只删除暂存区域的文件，保留工作目录的

- git rm -f test.py 文件已被修改，还没有add到缓存区时，强制删除两个文件

#### mv

- Description: Move or rename a file, a directory, or a symlink
- git mv 旧文件名 新文件名

#### diff

- Description：Show changes between commits, commit and working tree, etc

- git diff：比较暂存区域与工作目录的文件内容
- git diff HEAD: 比较当前版本快照与当前工作目录内容
- git diff id: 比较之前版本的快照与当前工作目录内容
- git diff id1 id2: 比较两个历史快照
- git diff --cached: 比较最新提交的快照和暂存区域的文件
- git diff --cached id: 比较git diff --cached: 比较指定版本的快照和暂存区域的文件
(https://blog.csdn.net/weixin_37861326/article/details/80097198)






- git-reset - Reset current HEAD to the specified state


## Branching and Merging
#### branch 

- Description: List, create, or delete branches
- Git 的分支原理实际上只是通过一个指针记载([Git分支原理](https://alibaba.github.io/arthas/quick-start.html))
- git branch "分支名称"：创建分支
- git breach -d  "分支名称"：删除分支 （如删除未合并分支 -D）
#### checkout 
- Description: Switch branches or restore working tree files
- git checkout "分支名称"：切换分支
- git checkout -b "分支名称"：创建并切换分支
#### merge 
- Description: Join two or more development histories together
- git merge "分支名称"：合并分支


