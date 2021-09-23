---
title: Chocolatey到底好不好用？
categories:
  - windws
  - 软件
tags:
  - Chocolatey
  - 软件安装包
  - 批量安装
top_img: 'https://cdn.jsdelivr.net/gh/zining3235/images@main/img-398.jpg'
abbrlink: 9d3ce657
date: 2021-04-07 21:00:22
---
## 为什么要使用CHOCOLATEY

#### 官网介绍

- Chocolatey是一种软件管理解决方案，与您在Windows上经历过的任何其他事情都不一样。Chocolatey引入了真正的软件包管理概念，使您可以对事物进行版本控制，管理依赖关系和安装顺序，更好的库存管理以及其他功能。
- Chocolatey可以使用命令批量安装软件，只要把要安装的软件用命令，真正做到无人值守，而且二进制文件还会自动添加环境变量，这点很省事，做到装完即用。

##### <div class='tip warning'><p>如果想安装试用，请跳转结语看完再决定<p></div>

## 安装CHOCOLATEY

- 访问Chocolatey官网，找到CMD.exe或者PowerShell.exe安装命令

- CMD.exe命令（本地电脑使用管理员运行，开始菜单搜索CMD，然后右键点击以管理员运行）

```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "[System.Net.ServicePointManager]::SecurityProtocol = 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

- PowerShell.exe命令（windows10右键开始菜单，点击Windows PowerShell（管理员）运行）

```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

- 看到以下输出，就安装完了

```
Chocolatey (choco.exe) is now ready.
You can call choco from anywhere, command line or powershell by typing choco.
Run choco /? for a list of functions.
You may need to shut down and restart powershell and/or consoles
 first prior to using choco.
Ensuring Chocolatey commands are on the path
Ensuring chocolatey.nupkg is in the lib folder
```

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-07_19-59-09.png)

  - 测试是否安装成功，运行：

    ```
    choco
    ```

  - 显示版本号即安装成功

  ## 安装软件

- 我这里以nodejs为例  

- 输入命令:

  ```
  choco install --yes nodejs
  ```

  - 命令拆解  “choco”告诉系统使用Choco工具，“install”告诉系统使用安装命令，“--yes”告诉系统安装过程一律同意，“nodejs”告诉系统我要安装Nodejs

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-07_19-52-38.png)

- 测试是否安装成功，运行:

```
node -v
npm -v
```

![操作截图](https://yekei-images.s3.jp-tok.cloud-object-storage.appdomain.cloud/Sourcetree/Snipaste_2021-04-07_19-53-27.png)

- 返回版本号，安装成功

##### 软件默认安装目录为C:\ProgramData\Chocolatey\lib

## 批量安装软件

- 运行命令:

```
choco install --yes nodejs git 
```

- 软件会把上面命令中的软件都安装上，只要Chocolatey软件包里面有，那么你可以一次安装多个，只要把软件名字输进去回车，等待就可以了，对于新电脑或者批量部署很方便了。

## 卸载软件

- 运行命令:

```
choco uninstall nodejs
```

- 命令解析 “choco”告诉系统使用Choco工具，“uninstall”告诉系统使用卸载命令，“nodejs”告诉系统卸载Nodejs这个软件

### Chocolatey用法：常用命令

- search - 搜索包 choco search something
- list - 列出包 choco list -lo
- install - 安装 choco install baretail
- pin - 固定包的版本，防止包被升级 choco pin windirstat
- upgrade - 安装包的升级 choco upgrade baretail
- uninstall - 安装包的卸载 choco uninstall baretail
- 安装Ruby Gem - choco install compass -source ruby
- 安装Python Egg - choco install sphynx -source python
- 安装IIS服务器特性 - choco install IIS -source windowsfeatures
- 安装Webpi特性 - choco install IIS7.5Express -source webpi

### 常用的一些命令

- 列出本地已安装的包 ：choco list --local-only
- 列出Windows系统已安装的软件：choco list -li OR choco list -lai
- 升级所有已安装的包：choco upgrade all -y
- mysql安装：choco install mysql -y
- maven安装：choco install maven 
- 升级maven：choco upgrade maven
- java安装 ： choco install jdk7，choco install jdk8

```
choco install autohotkey.portable    #安装 AutoHotkey (Portable)
choco install nodejs.install  #安装 node
choco install git.install     #安装 git
choco install python          #安装 python
choco install ruby            #安装 ruby
choco install jdk8            #安装 JDK8
choco install googlechrome    #安装 Chrome
choco install google-chrome-x64 #Google Chrome (64-bit only)
choco install firefox         #安装 firefox
choco install notepadplusplus.install #安装 notepad++
choco install Atom                    #安装 Atom
choco install SublimeText3            #安装 SublimeText3
```

### 常用命令

```
choco -h                       # 查看帮助
choco <command> -h             #查看相应命令的帮助
choco install <package name>   #安装软件包
choco search <keyword>         #搜索软件包，会列出跟关键字相关的所有软件包
choco upgrade <package name>   #升级软件包
choco uninstall <package name> #卸载软件包
choco list --local-only        #查看本地安装的软件包
```

## 卸载Chocolatey

- 进入软件目录直接删除整个安装目录Chocolatey
- 然后找到Chocolatey系统变量环境删除就可以了

## 结语

#### 不太不懂linux基础用户使用，以下几点

- 这是一个开源和收费软件，标准版安装目录无法指定，只能安装在C盘指定目录。
- 使用Chocolatey最好有些英文基础，这也是折腾linux需要的，不然查命令就得费你半天时间。
- 好处是安装迅速，安装Chocolatey不到一分钟安装完，安装nodejs也就一分钟，相比去官网下载，再安装要快多了，纯净安全，杜绝了任何捆绑软件，可以批量安装软件，这点对于部署来说真心太方便了，一条命令搞定所有需要安装的软件，当然收费软件还是需要你去购买授权，不过Chocolatey软件包都已免费软件为主。



- 下面是我准备更改路径，软件给出的提示！

```
It appears you are attempting to use options that may be only available in licensed versions of Chocolatey ('--install-directory'). There may be ways in the open source edition to achieve what you are looking to do. Please remove the argument and consult the documentation.
```