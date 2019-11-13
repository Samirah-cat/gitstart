# Git Reference

## Goal 
- 分布式版本控制系统，无需服务端支持
- 了解git基本原理和操作：https://git-scm.com/docs

## Structure
![image](https://note.youdao.com/yws/public/resource/7c18d614a76e9fcc62525c32e12b1969/xmlnote/462C7807CA734F49B7AE428D515DABBA/744)

- Working Directory：平时存放项目代码的地方。
- Stage：暂存已经修改的文件最后统一提交到仓库。
- Repository：提交的所有版本的数据。其中，HEAD 指向最新放入仓库的版本。

## Setup and Config
- 下载地址：https://gitforwindows.org/
```
> git config --global user.name "Samirah-cat"
> git config --global user.email "124335728@qq.com"
> git config --global i18n.commitencoding utf-8
> git config --global i18n.logoutputencoding utf-8
```

## Getting and Creating Projects
#### init
- Description: Create an empty Git repository or reinitialize an existing one
#### clone
- Description: Clone a repository into a new directory
```
F:\MyProject>git init
F:\MyProject2>git clone https://github.com/mihumouse/Java-Mock-Testing-Notes
```
## Basic Snapshotting
#### status
- Description: Show the working tree

#### add
- Description: Add file contents to the index
- git add . 将当前目录下修改的所有代码从工作区添加到暂存区 . 代表当前目录

#### commit
- Description: Record changes to the repository
- git commit -m "some commit log..."
- git commit -am "some commit log...": 从工作目录一步添加到仓库
- git commit --amend -m "": “更正”最近一次的提交

#### log
- Description: Show commit logs
- git log --graph --oneline --decorate --all: 以图像形式展示提交历史的分支结构

#### rm

- Description: Remove files from the working tree and from the index

- git rm  文件名: 命令删除的只是工作目录和暂存区域的文件（即取消跟踪，在下次提交时不纳入版本管理）
- git rm --cached 文件名: 只删除暂存区域的文件，保留工作目录的

- git rm -f test.py 文件已被修改，还没有add到缓存区时，强制删除两个文件

#### mv

- Description: Move or rename a file, a directory, or a symlink
- git mv 旧文件名 新文件名


#### reset 
- Description:Reset current HEAD to the specified state
- git reset HEAD~:  回退提交的代码。
移动 HEAD 的指向，将其指向上一个快照，然后再将该位置的快照回滚到暂存区域。
- git reset --soft HEAD~ : 只移动 HEAD 的指向，并不会将快照回滚到暂存区域。相当于撤消了上一次的提交（commit）。
- git reset --hard HEAD~ : 不仅移动 HEAD 的指向，将快照回滚动到暂存区域，它还将暂存区域的文件还原到工作目录。
- git reset --hard 快照id 文件名/路径: 将指定快照的指定文件回滚到暂存区域


#### diff

- Description：Show changes between commits, commit and working tree, etc

- git diff：比较暂存区域与工作目录的文件内容
- git diff HEAD: 比较当前版本快照与当前工作目录内容
- git diff id: 比较之前版本的快照与当前工作目录内容
- git diff id1 id2: 比较两个历史快照
- git diff --cached: 比较最新提交的快照和暂存区域的文件
- git diff --cached id: 比较git diff --cached: 比较指定版本的快照和暂存区域的文件

- summary
![image](
https://note.youdao.com/yws/public/resource/7c18d614a76e9fcc62525c32e12b1969/xmlnote/DC5BCFC5C96F452DA75D3F6121E12E51/871)


## Branching and Merging
#### branch 

- Description: List, create, or delete branches
- Git 的分支原理实际上只是通过一个指针记载([Git分支原理](https://blog.csdn.net/weixin_37861326/article/details/80097198))
- git branch "分支名称"：创建分支
- git breach -d  "分支名称"：删除分支 （如删除未合并分支 -D）
#### checkout 
- Description: Switch branches or restore working tree files
- git checkout "分支名称"：切换分支
- git checkout -b "分支名称"：创建并切换分支
#### merge 
- Description: Join two or more development histories together
- git merge "分支名称"：合并分支

## summary
![image](
https://note.youdao.com/yws/public/resource/7c18d614a76e9fcc62525c32e12b1969/xmlnote/9278468403A54932A4E65CA3434853CF/1027)

## todo
![image](https://note.youdao.com/yws/public/resource/7c18d614a76e9fcc62525c32e12b1969/xmlnote/9774ABEF571847C3A6383A480E01E608/1022)

    Vim
    1.移动命令
    j、k：向下移动一行/向上移动一行
    f、b：向下翻页/向上翻页
    d、u：向下翻半页/向上翻半页
    2.跳转命令
    g、G：跳转到第一行/跳转到最后一行
    先输入数字（如3），再输入g，表示跳转到该行（如第3行）
    3.搜索命令
    a.输入斜杠（/）或问号（?）,后面接搜索关键字
      区别：斜杠（/）表示从当前位置向下搜索，问号（?）表示从当前位置向上搜索。
    b.接着输入 n 表示顺着当前的搜索方向快速跳转到下个匹配的位置，大写的 N 则是与当前搜索方向相反。
    4.退出和帮助
    在:后边输入 q，表示退出 diff；输入 h 表示进入帮助界面，你会看到很多命令和功能，输入 q 可以退出帮助界面。
    
