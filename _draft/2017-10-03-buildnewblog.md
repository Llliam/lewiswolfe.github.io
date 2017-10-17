---
title:  "搭建独立博客"
categories: program
---

本教程适用于Mac平台，要求会使用git基本操作，命令行基本操作。

## 前言

最近看了开智部落成员 @violettianjie 发起的 issues [如何用 Jeklly/Hexo+GitHub 最方便的搭建博客？](https://github.com/OpenMindClub/OpenMindWorld/issues/350)，于是决定搭建一个属于自己的独立博客，并把搭建过程记录下来。

搭建博客的方法有很多，推荐使用Github Pages，它需要相应的博客引擎来驱动，
主流的有两个 [Hexo](https://hexo.io/) 和 [Jekyll](https://jekyllrb.com/) 。

> GitHub Pages 可以被认为是用户编写的、托管在GitHub上的静态网页。Jekyll是一个静态站点生成器，它会根据网页源码生成静态文件。整个思路到这里就很明显了。你先在本地编写符合Jekyll规范的网站源码，然后上传到github，由github生成并托管整个网站。----阮一峰

## 环境配置

- 操作系统 [Mac OS](https://support.apple.com/zh-cn/macos)
- 动态开源编程语言 [Ruby](https://www.ruby-lang.org/) 
- Ruby的包管理框架 [RubyGems](https://rubygems.org)
- 基于Chrome V8引擎的JavaScript运行环境 [Node.js](https://nodejs.org/en/)
- 分布式版本管理系统 [Git](https://git-scm.com/)
- 开源项目托管平台 [Github](https://github.com/)
- 静态站点托管服务 [Github Pages](https://pages.github.com/)
- 静态站点生产器/博客框架/博客引擎 [Jekyll](https://jekyllrb.com/) 或 [Hexo](https://hexo.io)


## Github搭建

1. Fork Jekyll/Hexo主题：从 [Jekyll theme](http://jekyllthemes.org/) [rubygems搜索jekyll theme](https://rubygems.org/search?utf8=%E2%9C%93&query=jekyll+theme) [Hexo theme](https://hexo.io/themes/) 搜索找到自己喜欢的博客主题，然后进入此博客主题的github库，
点击Fork，再回到自己的github库，把fork的仓库名修改为：`username.github.io` 。打开博客网址：`https://username.github.io` ，就可以看到博客界面了。

2. 在本地进行个性化配置：把这个`username.github.io`仓库git clone到本地，然后查看官网文档[Jekyll使用文档](http://jekyllrb.com/docs/home/) [中文](http://jekyllcn.com/docs/home/) [Hexo使用文档](https://hexo.io/docs/) [中文](https://hexo.io/zh-cn/docs/) 和相应的主题使用文档(此博客主题的github库)，进行个性化配置。

3. 撰写发布新的博文：在本地撰写新的博文，然后`git push origin master`推送到自己的github仓库，打开博客就看到自己更新的博文了。

## 本地搭建

1. 安装jekyll/hexo：	

- jekyll预览
	gem安装jekyll环境，打开终端输入命令：

	```
	sudo chown -R your_name /Library/Ruby/Gems/2.3.0 #注释1
	gem install jekyll bundler
	jekyll new blog
	cd blog
	bundler install
	bundle exec jekyll serve #或者jekyll serve
	```

	浏览器打开网址：`http://127.0.0.1:4000` ，即可预览博客。

-  hexo预览
	npm安装hexo环境，打开终端输入命令：

	```
	npm install hexo-cli -g
	hexo init blog
	cd blog
	npm install
	hexo server
	```

	浏览器打开网址：`http://127.0.0.1:4000` ，即可预览博客。

2. 安装主题并进行个性化配置：从 [Jekyll theme](http://jekyllthemes.org/) [rubygems搜索jekyll theme](https://rubygems.org/search?utf8=%E2%9C%93&query=jekyll+theme) [Hexo theme](https://hexo.io/themes/)  搜索找到自己喜欢的博客主题，然后进入此博客主题的github库，查看主题使用文档，进行个性化配置。

3. 撰写发布新的博文：在本地撰写新的博文，然后`git remote add origin`关联到自己的github仓库，打开博客就看到自己更新的博文了。



## 注释：

- 注释1

> 在Mac OS下，gem安装时容易出现以下错误：
```
gem install xxx
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.3.0 director
```
意思是gem要往某个神奇的目录写文件但是你的权限不够。因为你使用的是Apple家自带的 ruby，在尝试往Apple自家的库中塞东西，默认那个位置是给root的。有两个差劲的方法可以解决这个问题。一个是前面加 `sudo`。另一种是修改`/Library/Ruby/Gems/2.3.0`这个目录的用户权限，即：`sudo chown -R your_name /Library/Ruby/Gems/2.3.0` 。----出处：[Mac OS X 下使用 Ruby Gem 的两个坑](https://blog.argcv.com/articles/4429.c)

## 参考资料

- [Jekyll使用文档](http://jekyllrb.com/docs/home/) [中文](http://jekyllcn.com/docs/home/) 
- [Hexo使用文档](https://hexo.io/docs/) [中文](https://hexo.io/zh-cn/docs/) 
- [手把手教你用github pages搭建博客 最新版](http://www.jianshu.com/p/6fdb19aa4558)
- [搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html) 
- [使用Github Pages建独立博客](http://beiyuu.com/github-pages)
- [如何搭建一个独立博客——简明 GitHub Pages与 jekyll 教程](http://www.cnfeat.com/blog/2014/05/10/how-to-build-a-blog/)


## CHANGELOG

171003早上 创建
171008 增加Hexo、增加环境配置、优化


