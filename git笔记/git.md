## git简介

集中式管理系统：版本库存放在中央服务器，需要先从服务器取得最新版本，完成工作后再推送到中央服务器。



git是分布式的版本控制系统，每台工作电脑上都有完整的版本库。通常有一台充当中央服务器的电脑。



## 安装git

### Linux安装git

Debian 或者 Ubuntu 安装git

```shell
# 新版
sudu apt-get install git
# 旧版
sudu apt-get install git-core
```



其他Linux版本安装git，通过源码安装

* 下载git源码
* 解压
* 依次输入：`./config` ,`make`,`sudu make install`



### Windows安装git

下载git安装程序，一直next即可。

安装完成之后，设置git仓库全局用户名和邮箱：

```shell
git config --global user.name  "xxx"
git config --global user.email "xxx@xx.xx"
```







## 初次使用

### 初始化git仓库

进入相应文件目录，输入命令

```shell
git init
```

即可初始化git仓库

### 提交文件

将文件放入git仓库当中，输入命令`git add 文件名`即可将文件添加到git仓库。

输入`git commit -m "提交描述"`完成文件提交操作。

```shell
git add readme.txt
git commit -m "commit readme.txt"

git add 文件1 文件2 ...
```



### 查看仓库状态

查看文件是否有修改

```shell
git status
```



### 进行文件对比

查看修改的详情

```shell
git diff
```



### 查看日志

```shell
# 版本提交日志
git log

# 简化输出日志
git log --pretty=oneline

# 命令日志 
git reflog
```

可以查看到 提交版本号，提交人信息，以及提交日期。

主要用于版本回退。

### 版本回退

回退一个版本

```shell
git reset --hard^
```



### 查看工作区文件和版本库中最新版本的区别

```shell
git diff HEAD -- 文件名
```



### 放弃工作区的修改

```shell
git checkout -- 文件名
```

让文件回到最近一次的`git commit`或`git add`状态



### 暂存区的修改回退到工作区

```shell
git reset HEAD 文件名
```



### 删除文件

```shell
git rm 文件名
```



## 概念

### 工作区（work directory）

也就是工作目录



### 版本库

工作区的隐藏目录`.git`,这是git的版本库。



`git add`将文件添加到版本库的暂存区。

`git commit`将暂存区的文件提交到当前分支，暂存区会被清空。



## 远程仓库

### 创建SSH

在git bash中输入，linux直接在shell中打开。

```shell
ssh-keygen -t rsa -C "xxxx@XX.xxx"
```

之后就可以在用户的主目录下找到`.ssh`目录，里面有`id_rsa`**私钥**和`id_rsa.pub`**公钥** 两个文件。



登录GitHub,在**用户设置**，**SSH key**页面：

* 点击添加 SSH key
* 在title填写任意字符
* 将`id_rsa.pub`**公钥**文件内容粘贴在 Key文本框中





