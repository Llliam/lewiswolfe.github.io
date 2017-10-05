---
title:  "用 github pages+jekyll 搭建独立博客"
categories: 
  - program
---


## 前言

最近看了开智部落成员 @violettianjie 发起的 issues [如何用 Jeklly/Hexo+GitHub 最方便的搭建博客？](https://github.com/OpenMindClub/OpenMindWorld/issues/350)，于是决定搭建一个属于自己的独立博客，并把搭建过程记录下来。

> GitHub Pages 可以被认为是用户编写的、托管在 GitHub 上的静态网页。
Jekyll是一个静态站点生成器，它会根据网页源码生成静态文件。
整个思路到这里就很明显了。你先在本地编写符合Jekyll规范的网站源码，然后上传到github，由github生成并托管整个网站。----阮一峰

## 基础搭建

1. Fork Jekyll主题 [Minimal-Mistakes](https://github.com/mmistakes/minimal-mistakes) (此主题发现于[阳志平的日志](http://www.yangzhiping.com/)) 到自己的仓库，仓库名修改为：`username.github.io` 。等待片刻，打开网址：`https://username.github.io` ，就可以看到博客界面了。

2. 把这个github仓库git clone到本地，然后进行自定义修改。这个主题的自定义修改请参考: [Minimal-Mistakes:Quick-Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) 

3. 在本地仓库撰写发布新的博文，push到github仓库，等待片刻，打开博客就看看到自己更新的博文了。

## 在本地预览博客

1. gem安装jekyll环境，终端输入下面命令：

	```
	sudo chown -R your_name /Library/Ruby/Gems/2.3.0 #注释1
	gem install jekyll bundler
	bundler install
	```

2. 安装成功后，继续输入命令：`bundle exec jekyll serve` 来运行jekyll，
浏览器打开网址：http://127.0.0.1:4000 ，即可预览博客。

注释1：
> 在Mac OS下，gem安装时容易出现以下错误：
```
gem install xxx
ERROR:  While executing gem ... (Gem::FilePermissionError)
    You don't have write permissions for the /Library/Ruby/Gems/2.3.0 director
```
意思是gem要往某个神奇的目录写文件但是你的权限不够。因为你使用的是Apple家自带的 ruby，在尝试往Apple自家的库中塞东西，默认那个位置是给root的。有两个差劲的方法可以解决这个问题。一个是前面加 `sudo`。另一种是修改`/Library/Ruby/Gems/2.3.0`这个目录的用户权限，即：`sudo chown -R your_name /Library/Ruby/Gems/2.3.0` 。----出处：[Mac OS X 下使用 Ruby Gem 的两个坑](https://blog.argcv.com/articles/4429.c)

## 参考资料

- [理想的写作环境：Git+Github+Markdown+Jekyll](http://www.yangzhiping.com/tech/writing-space.html)
- [jekyll官网](http://jekyllrb.com/)
- [阳志平的日志](http://www.yangzhiping.com/)
- Minimal-Mistakes, A Jekyll Theme： [Live Preview](https://mmistakes.github.io/minimal-mistakes/) [Github Repository](https://github.com/mmistakes/minimal-mistakes) [Quick-Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/) 
- [搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html) 
- [如何搭建一个独立博客——简明 GitHub Pages与 jekyll 教程](http://www.cnfeat.com/blog/2014/05/10/how-to-build-a-blog/)
- [手把手教你用github pages搭建博客 最新版](http://www.jianshu.com/p/6fdb19aa4558)


## CHANGELOG
171003早上 创建


