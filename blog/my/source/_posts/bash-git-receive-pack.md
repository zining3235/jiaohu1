---
title: Hexo d bash：git-receive-pack：command not found 报错没有该库或者权限
categories:
  - hexo教程
  - 排错
tags:
  - hexo
  - hexo部署
  - hexo上传
top_img: 'https://cdn.jsdelivr.net/gh/zining3235/images@main/img-447.jpg'
abbrlink: 26898
date: 2021-02-28 17:51:31
cover:
---

一.报错如下

```shell
git.exe push --progress "origin" master
bash: git-receive-pack: command not found
fatal: Could not read from remote repository.
```

二、报错原因
代码服务器git安装路径是/usr/local/git，不是默认路径，根据提示，在git服务器上， 建立链接文件：
三、解决方式
在linux命令行输入如下命令即可解决：

```shell
ln -s /usr/local/git/bin/git-receive-pack /usr/bin/git-receive-pack
```

————————————————
原文链接：https://blog.csdn.net/li1325169021/article/details/111874334