---
title: CentOS7 手把手安装Nodejs（可能是最详细图文教程）
categories:
  - linux基本
  - nodejs
tags:
  - Nodejs
  - Npm
highlight_shrink: false
top_img: 'https://cdn.jsdelivr.net/gh/zining3235/images@main/img-437.jpg'
abbrlink: 27165
date: 2021-03-15 22:33:46
---
# CentOS 7 安装Nodejs

##### 首先进入官网找到最新版链接（[Nodejs官网](https://nodejs.org/zh-cn/download/)）右键点击箭头位置复制链接

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/nodejs/1.png)

##### 然后回到Linux shell 命令窗口输入 `wget`  然后按下空格空出来一个字节，

```shell
wget https://nodejs.org/dist/v14.16.0/node-v14.16.0-linux-x64.tar.xz
```

##### 然后点击右键粘贴，然后回车下载。

##### （红色箭头位置是有一个空格的，**这里注意**）

![](https://yinyinyushi.com/imgs/2021/03/be7a3f68ae0ebf67.png)

##### 显示百分百就下载完了

##### 然后解压缩

```shell
tar -xvf node-v14.16.0-linux-x64.tar.xz
```

### 解压完成

![](https://yinyinyushi.com/imgs/2021/03/eb6f265b32a6f042.png)

### 创建Nodejs目录

```shell
mkdir -p /usr/local/nodejs
```

### 把解压后的Nodejs文件移动到新建目录

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/nodejs/2.png)

```shell
mv node-v14.16.0-linux-x64/* /usr/local/nodejs/
```

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/nodejs/3.png)

##### 运行以下命令建立软连接，使得命令全局可用（ln -s /usr/local/nodejs##以下命令这里前半部分为nodejs所在目录，后半部分为nodejs默认目录/bin/node /usr/local/bin），所有nodejs命令都是要在默认目录里面读取nodejs来运行。

```shell
ln -s /usr/local/nodejs/bin/node /usr/local/bin
ln -s /usr/local/nodejs/bin/npm /usr/local/bin
```

### 验证是否安装成功

```shell
node -v
npm -v
```

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/nodejs/4.png)

### 自此安装完成