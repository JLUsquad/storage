# 如何使用本仓库以及github

我们建立了GitHub机构`JLUsquad`，之后我们就通过GitHub来进行代码协作和其它信息共享。首先要实现的是将我们的代码上传到仓库中，然后在每次编辑后都进行同步，这样能实现代码的便捷协作。下面是具体的使用方法。

## 初始化

在一个从来没有使用过git同步的环境中建立和使用repo需要进行初始化的操作：

### 配置邮箱和用户名

配置个人的用户名称和电子邮件地址：

```bash
$ git config --global user.name "runoob"
$ git config --global user.email test@runoob.com
```

#### 建立和添加SSHkey

先在本地创建ssh key:

```bash
$ ssh-keygen -t rsa -C "your_email@youremail.com"
```

后面的your_email@youremail.com改为你在github上注册的邮箱，之后会要求确认路径和输入密码，我们这使用默认的一路回车就行。成功的话会在~/下生成.ssh文件夹，进去，打开id_rsa.pub，复制里面的key。

回到github上，进入 Account Settings（账户配置），左边选择SSH Keys，Add SSH Key,title随便填，粘贴在你电脑上生成的key。
![image](http://www.runoob.com/wp-content/uploads/2014/05/github-account.jpg)

完成以上两个步骤之后，为了验证是否成功，输入以下命令：

```bash
$ ssh -T git@github.com
```

如果是第一次的会提示是否continue，输入yes就会看到：You've successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。

到此时git环境就已经配置好了，可以开始建立和使用仓库了。

## 建立仓库

以两种不同的情况讨论。

### 本地以存在代码

1. 在github上建立repository，但不添加README.md文件。
2. 在本地文件夹中:
    1. `git init`
    2. `git remote add origin 地址`
    3. `git add .`添加所有文件。
    4. `git commit -m '信息'`
    5. `git push -u origin master`第一次push时加上`-u`可以将本地master与远程进行链接，之后的push才可以直接使用`git push`.

### 本地无代码

克隆远程建立的仓库。

## 日常使用

* `git add .`添加文件到缓存区域
* `git commit -m '本次更新的信息'`将文件添加到本地分支
* `git pull`将远程分支和本地分支合并
* `git push`同步远程和本地

## 参考教程

>[Git远程操作详解 - 阮一峰的网络日志](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)
>详解了 `clone`,`remote`,`fetch`,`pull`,`push`五个`git`远程操作。
>
>*“Git有很多优势，其中之一就是远程操作非常简便。本文详细介绍5个Git命令，它们的概念和用法，理解了这些内容，你就会完全掌握Git远程操作。”*
>
><https://git-scm.com/book/zh/v2>
>
>Book *Git Pro* 的中文版，详细讲解了关于git的一切。
>
>*"The entire Pro Git book, written by Scott Chacon and Ben Straub and published by Apress, is available here."*
>
><http://www.runoob.com/manual/git-guide/>很帅的git实用简介！
>
><http://www.runoob.com/git/git-tutorial.html>菜鸟教程网站的git教程,简明实用！
>
><http://www.runoob.com/w3cnote/git-guide.html>