---
title: Sourcetree添加gitlab账户出现认证失败（可能是最详细的图文教程）
categories:
  - linux基本
  - Git
tags:
  - Sourcetree
  - gitlab
  - 访问令牌
top_img: 'https://cdn.jsdelivr.net/gh/zining3235/images@main/img-414.jpg'
abbrlink: 18ee9552
date: 2021-04-03 18:09:50
---
###   前言

今天准备搭建一下小康博主的友链页面，在使用Sourcetree添加gitlab账户出现认证失败的问题，

多方尝试都是失败，百度没有查到类似问题，即使有也是乱七八糟的，没有一点用处，随即谷歌了一下，找到了问题所在。

##### 期初失败截图

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-03_17-28-57.png)

##### 问题源头

其实就是因为英文界面的缘故，密码弄错了而已，设置令牌然后使用令牌当做密码登录就可以了。

#### 创建Gitlab访问令牌

访问Gitlab[令牌页面](https://gitlab.com/-/profile/personal_access_tokens)，创建令牌，名字随便，权限选中下面四个

- api
- read_user
- read_api
- write_repository

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-03_17-44-08.png)

然后点击下面的<span class="inline-tag blue">Creach personal access token</span>创建令牌，就会给出令牌了，复制令牌，然后先不要关闭网页，万一刚才没复制上，还可以回来复制，关闭了就找不回来了。

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-03_17-45-24.png)

##### 重新添加账户

复制令牌后，回到Sourcetree软件，添加Gitlab账户

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-03_17-49-07.png)

点击刷新令牌，然后在弹出的窗口用户名处输入你的Git用户名，密码处粘贴你刚才复制的令牌就可以了。

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-03_17-54-02.png)

现在你应该已经登录上去了，然后点击确定，就认证成功登录上了。

##### 登录认证成功

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-03_17-56-48.png)

### 结语

其实这玩意真没啥可说的，吃亏就吃亏在英文上了，资额在这里就是给自己做个备忘，如果能帮到你就更好了。