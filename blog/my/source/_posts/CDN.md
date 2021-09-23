---
title: 从零部署阿里云全站加速DCDN（未备案仅海外加速）
categories:
  - CDN
  - 阿里云CDN
tags:
  - CDN
  - 全站加速
  - 静态加速
top_img: 'https://cdn.jsdelivr.net/gh/zining3235/images@main/img-227.jpg'
abbrlink: 64f5dcce
date: 2021-03-20 16:03:15
---
**网站虽然放在伯力机房，不过晚上速度还是很慢，所以想试下部署CDN加速看看有没有效果。**

##### 进入官网

开始动手 首先进入阿里云官网，在产品里面搜索全站加速，进入控制台

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/1.png)

##### 添加域名

点击域名管理，添加要加速的域名，

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/2.png)

<div class='tip error'><p>这里注意，如果是https选择442端口，后面计费多了个https的请求数（阿里云https的费用是0.1元万次，按请求数计费）<p></div>

##### 审核通过

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/3.png)

审核速度还是挺快的，我第一个域名添加进去大概不到一分钟就可以配置了，

##### 开始配置

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/4.png)

##### 配置加速规则

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/5.png)

##### 静态文件类型配置

点击修改配置，根据实际选中即可，一般选择图片页面文本其他即可，

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/6.png)



##### 缓存过期时间

配置资源对应的缓存过期时间，最长可以设置为3年。

- 不常更新的静态文件：例如图片类型、应用下载类型等，缓存时间建议设置为1个月以上。
- 频繁更新的静态文件：例如JS、CSS等，缓存时间请根据实际业务情况设置。
- 动态文件：例如PHP、JSP、ASP等，缓存时间建议设置为0s，即不缓存。

##### 静态URL

我这里直接设置源站域名，因为我网站是纯静态的，所以直接设置全站

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/7.png)

##### 静态文件路径

静态文件路径也同样设置源站域名

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/8.png)

动态内容协议跟随回源，这里配置https或者跟随源站端口都可以

##### https配置

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/9.png)

修改配置上传源站SSL证书就可以了，然后下面根据实际需要配置

##### 性能优化

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/10.png)

同样 根据实际情况打开即可，至此配置完成。可以ping下看看速度如何

## 结语

##### 本站未加速直连测试

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/11.png)

##### 阿里云全球加速节点测试（含中国大陆）

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/12.png)

##### 阿里云境外加速节点测试（不含中国大陆）

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/CDN/13.png)

#### 境外加速在国内访问惨不忍睹！如果有需要还是选用香港地区加速吧！而且阿里云SSL-CDN收费并不便宜。