[Git 官网下载地址](http://git-scm.com/downloads)

[Git 国内镜像下载地址](https://npm.taobao.org/mirrors/git-for-windows/。)

[git 教程1](https://backlog.com/git-tutorial/cn/reference/)

[廖雪峰git教程](https://www.liaoxuefeng.com/wiki/896043488029600)

[git官网教程](https://git-scm.com/book/zh/v2)



## git 配置

##### 配置个人的用户名称和电子邮件地址：

去掉 **--global** 参数只对当前仓库有效。

```bash
$ git config --global user.name "jinwei333"
$ git config --global user.email 1343711279@qq.com
```

##### 设置Git默认使用的文本编辑器

```bash
$ git config --global core.editor emacs
```

##### 差异分析工具

Git 可以理解 kdiff3，tkdiff，meld，xxdiff，emerge，vimdiff，gvimdiff，ecmerge，和 opendiff 等合并工具的输出信息。

```bash
$ git config --global merge.tool vimdiff
```

##### 查看配置信息

```bash
$ git config --list
$ git config user.name
```

##### 编辑 git 配置文件

```bash
$ git config -e    # 针对当前仓库
$ git config -e --global   # 针对系统上所有仓库
```

##### git clone

拷贝一份远程仓库，也就是下载一个项目。

```bash
git clone -o main git@github.com:fsliurujie/test.git
```

git clone 时，可以所用不同的协议，包括 ssh, git, https 等，其中最常用的是 ssh，因为速度较快，还可以配置公钥免输入密码。各种写法如下：

```bash
$ git clone git@github.com:fsliurujie/test.git         --SSH协议
$ git clone git://github.com/fsliurujie/test.git          --GIT协议
$ git clone https://github.com/fsliurujie/test.git      --HTTPS协议
```


![img](https://www.runoob.com/wp-content/uploads/2015/02/git-command.jpg)

说明：

- workspace：工作区
- staging area：暂存区/缓存区
- local repository：版本库或本地仓库
- remote repository：远程仓库

```bash
$ git init	# 使用当前目录作为 Git 仓库
$ git init dir	# dir 目录下会创建一个 Git 仓库

$ git add .	# 添加当前目录下的所有文件到暂存区
$ git add Readme.txt	# Readme.txt 纳入版本控制
$ git commit -m '版本注释'

```



```bash
$ git status # 查看项目的当前状态。
$ git status -s
```



##### 查看提交历史

```bash
git log
```



##  标签（tag）

```bash
git tag -a v1.0 	# 添加标签
```

-a 选项意为"创建一个带注解的标签"。 不用 -a 选项也可以执行的，但它不会记录这标签是啥时候打的，谁打的，也不会让你添加个标签的注解。 

```bash
git tag -a <tagname> -m "标签信息"
git show v1.0		# 查看分支所修改的内容
```



## 分支（branch）

分支是用来标记特定代码的提交，每一个分支通过SHA1sum值来标识，所以对分支的操作是轻量级的，你改变的仅仅是SHA1sum值。

```bash
git branch	# 查看本地所有分支
git branch -r # 查看远程所有分支
git branch -a # 查看本地和远程的所有分支
git branch <branchname>	# 创建新的分支
git checkout <branchname> # 切换分支
git checkout -b <branchname>	# 创建新的分支并切换到新分支
git branch -d <branchname>	# 删除本地分支
git branch -d -r <branchname> # 删除远程分支，删除后还需推送到服务器
git push origin:<branchname>  # 删除后推送至服务器
git branch -m <oldbranch> <newbranch> //重命名本地分支
git merge	# 将任何分支合并到当前分支中
```



# Git 远程仓库(Github)

```bash
git remote add [shortname] [url]
```

由于本地 Git 仓库和 GitHub 仓库之间的传输是通过SSH加密的，所以我们需要配置验证信息：

使用以下命令生成 SSH Key

```bash
ssh-keygen -t rsa -C "youremail@example.com"
```

要查看当前配置有哪些远程仓库，可以用命令：

```bash
git remote
git remote -v
```

执行时加上 -v 参数，可以看到每个别名的实际链接地址。

## fetch

将远程主机的最新内容拉到本地，用户在检查了以后决定是否合并到工作本机分支中。

```bash
git fetch <远程主机名>	# git fetch origin
git fetch <远程主机名> <分支名>	# 只想取回特定分支的更新，常用 git fetch origin master
```

执行 `git fetch origin master` 时，它的意思是从名为 **origin** 的远程上拉取名为 **master** 的分支到本地分支 **origin/master** 中。既然是拉取代码，当然需要同时指定远程名与分支名，所以分开写。

## pull

即将远程主机的某个分支的更新取回，并与本地指定的分支合并。等同于：

```bash
git fetch origin master
git merge FETCH_HEAD
```

完整格式：

```bash
git pull <远程主机名> <远程分支名>:<本地分支名>
git pull origin master:master
```

## merge

将两个或两个以上的开发历史合并在一起。

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210306150648609.png" alt="image-20210306150648609" style="zoom: 33%;" />

它会把两个分支的最新快照（C3 和 C4）以及二者最近的共同祖先（C2）进行三方合并，合并的结果是生成一个新的快照（并提交）。

<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210306150756060.png" alt="image-20210306150756060" style="zoom: 33%;" />

```bash
git merge
git merge origin/master
```

执行 `git merge origin/master` 时，它的意思是合并名为 **origin/master** 的分支到当前所在分支。既然是分支的合并，当然就与远程名没有直接的关系，所以没有出现远程名。需要指定的是被合并的分支。

## push

推送新分支与数据到某个远端仓库命令

```bash
git push <远程主机名> <本地分支名>:<远程分支名>

git push origin master
```

执行 `git push origin master` 时，它的意思是推送本地的 **master** 分支到远程 **origin**，涉及到远程以及分支，当然也得分开写了。

删除远程仓库你可以使用命令：

```bash
git remote rm [别名]
```



跟踪分支

```
git checkout -b <本地分支名> <远程主机名>/<远程分支名>
```

设置已有的本地分支跟踪一个刚刚拉取下来的远程分支，或者想要修改正在跟踪的上游分支

