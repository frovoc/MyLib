# Git 基本操作

Git 的工作就是创建和保存你项目的快照及与之后的快照进行对比。

本章将对有关创建与提交你的项目快照的命令作介绍。

Git 常用的是以下 6 个命令：**git clone**、**git push**、**git add** 、**git commit**、**git checkout**、**git pull**，后面我们会详细介绍。

![img](https://www.runoob.com/wp-content/uploads/2015/02/git-command.jpg)

**说明：**

- workspace：工作区
- staging area：暂存区/缓存区
- local repository：版本库或本地仓库
- remote repository：远程仓库

一个简单的操作步骤：

```
$ git init    
$ git add .    
$ git commit  
```

- git init - 初始化仓库。
- git add . - 添加文件到暂存区。
- git commit - 将暂存区内容添加到仓库中。

### 创建仓库命令

下表列出了 git 创建仓库的命令：

| 命令        | 说明                                   |
| :---------- | :------------------------------------- |
| `git init`  | 初始化仓库                             |
| `git clone` | 拷贝一份远程仓库，也就是下载一个项目。 |

------

## 提交与修改

Git 的工作就是创建和保存你的项目的快照及与之后的快照进行对比。

下表列出了有关创建与提交你的项目的快照的命令：

| 命令         | 说明                                     |
| :----------- | :--------------------------------------- |
| `git add`    | 添加文件到仓库                           |
| `git status` | 查看仓库当前的状态，显示有变更的文件。   |
| `git diff`   | 比较文件的不同，即暂存区和工作区的差异。 |
| `git commit` | 提交暂存区到本地仓库。                   |
| `git reset`  | 回退版本。                               |
| `git rm`     | 删除工作区文件。                         |
| `git mv`     | 移动或重命名工作区文件。                 |

### 提交日志

| 命令               | 说明                                 |
| :----------------- | :----------------------------------- |
| `git log`          | 查看历史提交记录                     |
| `git blame <file>` | 以列表形式查看指定文件的历史修改记录 |

### 远程操作

| 命令         | 说明               |
| :----------- | :----------------- |
| `git remote` | 远程仓库操作       |
| `git fetch`  | 从远程获取代码库   |
| `git pull`   | 下载远程代码并合并 |
| `git push`   | 上传远程代码并合并 |



## 详细

#### 一、git初始化

在本地新建项目文件后进入项目文件右键打开git bash
使用git init初始化项目目录

#### 二、配置个人信息

目的：在公司团队开发项目时方便查看git使用用户

git config --global user.name "用户名"
git config --global user.mail “邮箱@163.com”

#### 三、上传代码（存储到.git）

git add ./文件名 （单个文件上传，add：添加）
git add ./ （所有文件）
git commit -m "提交说明" （commit：提交，-m 说明）
如果只输入git commit时会跳转到新的界面说明，可以使用Esc键，输入冒号:!q强制退回

git status (检查是否吧文件放到暂存区，status：状态)

#### 四、上传所有文件到版本库

git commit --all -m "说明信息" （–all:所有）

#### 五、查看历史提交日志

git log （查看所有提交记录）
git log --oneline (在一行显示提交记录信息)

#### 六、版本回退

git reset --hard Head~0 （回退到上次提交的状态）
git reset --hard [版本号] （精确回退到提交时的状态）

#### 七、版本号切换

如果后悔版本回退到上一版本可以通过查询以前提交的所有版本号切换回来

git reflog

#### 八、创建分支

git branch dev
说明：创建一个分支名为dev的子分子

2.git branch

说明：查看当前有哪些分支

#### 九、切换分支

git checkout dev
说明:切换到一个分支名为dev的分支中，checkout：切换

#### 十、回到默认分支master

git checkout master

#### 十一、合并分支

git merge dev
说明：把当前分支与指定分支（dev）合并，merge：合并
注1：当前分支指的是“git branch” 命令有星号（*）的分支；
注2：合并分支时如果有冲突，需要手动解决；

#### 十二、删除分支

git branch -d dev
说明：删除一个分支为dev的；

#### 十三、把本地文件上传到远程服务器（例：GitHub）

git push [地址] master(分支名)
说明：把当前分支上传到远程的master分支上；
例子：“git push git@github.com:lishubin01/myproty.git master”
注：如果第一次上传需要输入GitHub的账号和密码；

#### 十四、从远程仓库拉取项目到本地（例：GitHub）

git pull [地址] 分支名(master)
注：本地要初始化一个仓储；
例子：“git pull git@github.com:lishubin01/myproty.git master”
pull：拉取

#### 十五、从远程仓库克隆项目到本地（例：GitHub）

git clone [地址]
例子：“git clone git@github.com:lishubin01/myproty.git master”
注：pull和clone一样，一般常用pull， 使用pull只会做相应的合并，而多次使用clone会覆盖本地内容

#### 十六、使用ssh（例：GitHub）

ssh-keygen -t rsa -C "邮箱"
例子：ssh-keygen -t rsa -C “1350254342@qq.com”
说明:为远程仓库添加ssh便于团队协作时拉取和上传代码不需要提供账号和密码；

#### 十七、pull和push使用顺序

说明：当团队开发时，从服务器拉取或者上传代码到服务器时，应该先使用git pull [仓库地址]  master（分支名）然后在使用git push [仓库地址] master（分支名）
1

#### 十八、push和pull简写方式

1.git remote（远程的） add [变量名] master（分支名）
说明：添加一个远程仓库地址
例：git remote add rogin master
2.git pull [变量名] master(分支)
git push [变量名] master(分支)
3.git push [变量名] -u master(分支)
说明：加上-u参数，下次push时只需要执行git push就能上传代码了（加上-u之后git会把当前分支与远程指定的分支进行关 联，下次操作时只需要git push和git pull进行上传和拉取）