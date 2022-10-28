---
layout: post
title: GitHub搭建免费个人博客
date: 2022-10-28 
tags: 经验 学习    
---

## github免费搭建个人博客

### 注册GitHub账号

> 首先得注册一个GitHub账号。点击<a href="https://www.github.com">进入官网</a>

![](./images/posts/github/github1.jpg)

> 按提示填写资料，邮箱一定要能接收验证码，最后点击**Create an account**完成注册，选free版即可。

![](/images/posts/github/github2.png)

> 最后进入这个类似首页的节面。点击右上角头像，个人项目主页之类的入口都在这里。

### 开始搭建博客

> 首先，我们需要新建一个Repositories，相当于一个仓库，用来存放我们的项目文件。
>
> 点击上图头像旁边的“**+**” ，选择New Repositories

![](/images/posts/github/github3.png)

> 给自己的repositories取个名字，格式最好为把上图中*替换成你的用户名。
>
> 然后点击create repositories。
>
> 随后跳转到该库的界面，里面有没有文件不用管，点击Settings

![](/images/posts/github/github4.png)

进入settings后，往下拉，找到GitHub pages设置界面

![](/images/posts/github/github5.png)

> 按上图选择，下方箭头处可以添入自定义域名。
>
> 选择完成后，记得save.刷新，当上方出现**Your site is live at http://项目名.github.io 时，就算完成了。可以点击进去看看，当然，现在还是一个空白页面。

### 安装GitHub桌面版

[GitHub desktop下载入口](https://docs.github.com/cn/desktop/installing-and-configuring-github-desktop/installing-and-authenticating-to-github-desktop/installing-github-desktop)

```
按系统选择相应的版本下载，下载完成双击安装，一路默认即可
安装完成，双击打开，输入用户名，密码完成登录
点击file--Clone repositories.
将刚建好的repositories的url复制过来，点击Clone。Localpath这里选择本地存放项目文件的位置。
```

![](/images/posts/github/github6.png)

```
clone完成后，你会发现你刚才选择的位置路径下多了一个以域名命名的文件夹。
然后将该文件夹里的文件都删掉，如果有.git文件，需要保留.git文件
```

### 博客模板

```
模板库：网络资源比较多，可自行搜索
```

- [HTML5 UP](https://html5up.net/)
- [模板王](http://www.mobanwang.com/)

```
模板下载下来后，将文件加压缩到本地的那个库文件夹中即可。
```

### 同步到GitHub

```
打开GitHub桌面版，你会发现有很多Changes,如下图在summary中随意填一些内容，然后commit to main(提交到main)
```

![](/images/posts/github/github7.png)

```
右侧出现“push origin"（推送origin）按钮，点击即可
```

![](/images/posts/github/github8.png)

```
然后回到GitHub网站上，你会发现该库文件下多了很多文件
到这里也就差不多了，可以输入地址访问自己的博客了，剩下的就该自己优化博客了。
说明，博客首页为index.htm文件，也是默认起始页面。
```

