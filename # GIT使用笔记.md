---
typora-copy-images-to: ./assets
---

# GIT使用笔记

**git**  是 **分布式版本控制系统**

仓库中每个文件都有一个完整的版本历史记录 可以看到谁在什么时候修改了内容 需要的话可以恢复到之前的版本。

传统（什么都不用）：将一个文件复制备份 对备份进行修改 作为修订版。如果多个人对一个文件（项目）进行修改，就需要手工来合并两个人修改的内容 低效也麻烦。**版本控制系统就是用来解决这个问题，让项目成员之间的协作更加高效**
**分布式版本控制系统：**

```mermaid
graph TB
A[分布式版本控制系统] -->|种类1|B["集中式(SVN、CVS...)"]
A -->|种类2|C["分布式(GIT、MERCURIAL...)"]
```
TIP:md在节点使用符号得用双引号括起来
集中式：
代码都是从中央服务器下载，然后修改后进行提交。中央服务器挂了就可以下班了。
```mermaid
graph TB
A[中央服务器] -->|分发及接受| B[client1]
A -->|分发及接受| C[client2]
A -->|分发及接受| D[client3]
```
分布式：
代码从一个人进行发布开始 给所有人，每个人都能获取别人提交的代码 修改 并发布给所有人。等同于每个人都用有一个完整的仓库。

```mermaid
graph LR
    A[Client1] --> B[中央服务器]
    A --> D[client3]
    B --> C[client2]
    D --> C
    A --> C
    B --> D


```

## git使用方式
1.命令行
2.图形界面GUI
3.IDE 例如使用vscode扩展

## git使用
第一步使用git config命令配置一下用户名和邮箱
```bash
git config --global user.name "Your Name "
#省略（Local）：本地配置，只对本地仓库有效
#--global : 全局配置，所有仓库生效
#--system :系统配置，对所有用户生效
git config --global user.email youremail@.com
git config --global credential.helper store
git config --global --list
```
##创建仓库
方式一：在本地这只文件夹为仓库
方式二：将github仓库克隆到本地
```bash 
git init
git clone
```
## unknown
工作区Working Directory
暂存区staging Area/Index
本地仓库Local Repository

```mermaid
graph LR
A[工作区]-->B[暂存区]
B-->C[本地仓库]
```

```bash
![1](C:/Users/Administrator/Pictures/gitPic/1.png)
#创建仓库
git init
#查看仓库的状态
git status
#添加到暂存区
git add
#提交
git commit

```