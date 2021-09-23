---
title: CentOS7 手把手教你安装Git（可能是最详细图文教程）
categories:
  - linux基本
  - git
tags:
  - git
  - 源代码
highlight_shrink: false
top_img: 'https://cdn.jsdelivr.net/gh/zining3235/images@main/img-15.jpg'
abbrlink: 64388
date: 2021-03-16 18:43:20
---
#   工欲善其事必先利其器

安装编译库

```shell
yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel 
```

安装提示:Is this ok [y/d/N]: 输入Y即可

##### 接着安装编译工具

```shell
yum install gcc perl-ExtUtils-MakeMaker package 
```

同上安装提示:Is this ok [y/d/N]: 输入Y即可

安装完成，查看本机是否安装git，

```
git --version
```

显示版本号

```
git version 1.6.1
```

<div class='tip' ><p>很老的版本的，这里我们直接卸载掉，安装新版本<p></div>

输入命令删除现有Git

```shell
yum remove git
```

然后进入软件安装目录

```shell
cd /usr/local/src
```

# 下载安装

### 去[Kernel](https://mirrors.edge.kernel.org/pub/software/scm/git/)找到想安装的版本

https://mirrors.edge.kernel.org/pub/software/scm/git/

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/taunki/1.png)

选中里面的2.31.0版本，右键复制链接，在linux终端输入Wget空格，然后右键把棒材复制的链接粘贴进去，回车下载

```shell
wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.31.0.tar.gz
```

下载完成后运行以下命令解压到当前目录

```
tar -zvxf git-2.31.0.tar.gz
```

进入刚才解压的 git-2.9.5 目录下

```shell
cd git-2.31.0
```

复制命令到终端，执行编译，配置低的机器会比较慢，这里耐心等待跑完就好了

```shell
make prefix=/usr/local/git all
```

完成后输入以下命令安装到linux软件目录

```shell
make prefix=/usr/local/git install
```

# 配置变量

打开变量环境配置文件，

```shell
vim /etc/profile
#如果上面命令提示 vim 找不到，就换成下面的，两段命令同理，就是编辑工具不同
vi /etc/profile
```

打开后按住键盘下箭头，把光标一直移动到末尾最后一个字符上面

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/taunki/2.png)



把输入法切换成英文，按 i 进入编辑，终端下方会显示 -- INSERT -- 

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/taunki/3.png)

然后把终端光标向右移动到空字符上，也就是上图e的后面，然后回车

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/taunki/4.png)

如果光标在e的位置上按回车，会把e也回车到下面一行

<div class='tip error' ><p>需要多多注意终端变化，不然会出现莫名其妙的问题<p></div>

然后输入变量环境

```shell
PATH=$PATH:/usr/local/git/bin
export PATH
```

然后按下Esc，终端没有了 -- INSERT -- ，按住Shift+:再输入wq，回车即可

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/taunki/5.png)

这样就配置变量并保存完成完成，然后执行以下命令让刚才的变量环境生效

```shell
source /etc/profile
```

查看git版本号

```shell
git --version
```

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/taunki/6.png)

显示2.31.0

### 至此安装完成

## 结语

通过上面配置是正常使用了，但是有时候我们在远程使用git命令时候会出现无权限，或者没有这个库的问题，这个是因为我们的安装目录不是软件默认目录，所以需要建立一个软连接，来指定git的目录

```shell
ln -s /usr/local/git/bin/git-receive-pack /usr/bin/git-receive-pack
```

