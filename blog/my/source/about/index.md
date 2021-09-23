---
title: 关于本站
date: 2021-02-16 11:08:17
tag_img: https://cdn.jsdelivr.net/gh/zining3235/images@main/img-132.jpg

---
- <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/zining3235/hexo-DIY@main/lyb--diy-page.css">

#### 博客简介

#####        本博客基于[HEXO](https://hexo.io/)框架搭建，由[CODING](https://coding.net)提供部署推送，坐落在俄罗斯[G-Core](https://gcorelabs.com)机房，博客主题采用[Butterfly](https://github.com/jerryc127/hexo-theme-butterfly)主题，并内嵌[小康魔改工具库](https://antmoe.com)。



#### 博客自己引入的CSS

##### 作用：

##### 美化文章页面日期、分类、标签、评论图标。

##### 美化文章封面图，加一个小小的滤镜。

##### 美化文章框架，增加了对齐，

<div class='tip warning'><p>直接引入的CSS文件我添加了字体修改，不喜欢的话直接使用下面的CSS代码就好了<p></div>

##### 直接使用下面这条CSS，直接引入这条CSS

```
- <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/zining3235/hexo-DIY@main/diy-page.css">
```

##### 或者自己新建CSS文件丢到博客主题CSS文件里面，然后再引入就好了。

```
/* Font Icon */
#menus .site-page .fa-coffee{
 color:#ee6295 !important;
}

/* Font Icon */
#menus li .fa-comments{
 color:#ee6295 !important;
}

/* Font Icon */
#menus .site-page .fa-graduation-cap{
 color:#ee6295 !important;
}

/* Font Icon */
#menus .site-page .fa-home{
 color:#ee6295 !important;
}

/* Font Icon */
#search-button .search i{
 color:#ee6295;
}

/* Font Icon */
#menus .site-page .fa-link{
 color:#ee6295;
}

/* Font Icon */
#menus .site-page .fa-paper-plane{
 color:#ee6295;
}
/* Font Icon */
#menus .site-page .fa-heart{
 color:#ee6295 !important;
}

/* Font Icon */
#menus .menus_item .fa-fw{
 color:#ee6295;
}

/* Font Icon */
#menus li .fa-images{
 color:#ee6295;
}

/* Font Icon */
#menus li .fa-folder-open{
 color:#ee6295;
}
/* Font Icon */
#recent-posts .post-meta-date i{
 color:#ea4335;
}

/* Font Icon */
#recent-posts .article-meta .fa-inbox{
 color:#fbbc05;
}

/* Font Icon */
#recent-posts .article-meta .fa-tag{
 color:#34a853;
}

/* Font Icon */
#recent-posts .article-meta .fa-comments{
 color:#4285f4;
}
/* 图片边框 */
#recent-posts a img{
 border-style:solid;
 border-color:#f5bcbc;
}
/* 对齐 */
#aside-content{
 height:2680px;
}
/* 引入字体 */
@import url("//fonts.googleapis.com/css2?family=IBM+Plex+Mono:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,500;1,600;1,700&display=swap");

/* 字体 */
#content-inner{
 font-family:'IBM Plex Mono', monospace;
}
/* 文章页面使用字体 */
#post{
 font-family:'IBM Plex Mono', monospace;
}
```
#### 美化效果：

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/hexo-diy/ioctu.png)

![](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/hexo-diy/duiqi.png)