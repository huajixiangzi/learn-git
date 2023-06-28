## 6月25日

git 是一个分布式的版本管理系统。

* 每个人的电脑上都有一个完整的版本库。A，B同时修改文件W，那么只需要他们俩将各自的修改推送给对方，就能互相看到对方的修改。
* 安全性高：一个人的电脑坏掉了，只需要从另一个人的电脑中copy一份即可。



linux安装git

以下是debian或者 ubuntu linux安装git的方法：

```bash
sudu apt-get -install -git
#老版本的linux使用以下命令安装：
sudo apt-get install git-core
```



其他linux版本安装git则需要下载git源码，然后解压。依次输入：`./config` , `make` ,` sudo make install`



初始化git仓库

选择一个合适的目录，输入命令`git init` 即可初始化git仓库。请注意该目录及其父目录不应该包含中文字符。