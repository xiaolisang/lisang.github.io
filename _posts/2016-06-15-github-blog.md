---
layout: post
title:  "github创建blog"
width: large
date:   2016-06-13 10:51:47 +0530
categories: jekyll update
img: 1.jpg
categories: [one, two]
color: 9E9D24
author: lisang
---

github page
github-page是一个免费的静态网站托管平台，由github提供，它具有以下特点：
{% highlight ruby %}
    免空间费，免流量费
    具有项目主页和个人主页两种选择
    支持页面生成，可以使用jekyll来布局页面，使用markdown来书写正文
    可以自定义域名
{% endhighlight %}
项目主页

项目主页的目的是为项目提供一个展示功能的网站，方便项目推广。但是也可以用来做个人博客。对于博客来说，博客的整个网站目录需要是项目仓库的gh-pages分支，而且gh-pages是个没有父分支的分支。通过https://pages.github.com/上的向导，在你的项目仓库中创建这样的分支，并且github还提供了多种模板供你选择：

通过向导自动创建的项目类似这样http://pchou.github.io/pagetest/，在使用自定义域名前，你需要通过这样的链接访问项目主页。它是一个纯粹为项目推广准备的，因此并没有博客的结构，但是自定义模板的功能确实很不错。

手动创建分支的方法，也很简单，可以参考Creating Project Pages manually
个人主页

每个帐号只能有一个仓库来存放个人主页，而且仓库的名字必须是username/username.github.io，这是特殊的命名约定。你可以通过http://username.github.io来访问你的个人主页。

通过向导很容易创建一个仓库，并测试成功。不过，同样的，没有博客的结构。需要注意的个人主页的网站内容是在master分支下的。
本地环境搭建

这一步不是必须的，但是强烈建议完成。因为在博客发布之前，通常都是需要在本地先检验一下的。笔者曾经在一步步在GitHub上创建博客主页(4)中详细描述了如何构建一个本地环境。不过现在情况变的更简单了，github有一个对应的gem，可以”一键”配置环境，具体可以参考Using Jekyll with Pages。这里稍微提一下：
Ruby安装

参考一步步在GitHub上创建博客主页(4)
安装Bundle

直接使用下面命令即可：

$ gem install bundle

Gemfile和Bundle安装

在更目录下创建一个叫Gemfile的文件，注意没有后缀，输入

source 'http://ruby.taobao.org/'
gem 'github-pages'

保存后，在命令行中执行

$ bundle install

命令会根据当前目录下的Gemfile，安装所需要的所有软件。这一步所安装的东西，可以说跟github本身的环境是完全一致的，所以可以确保本地如果没有错误，上传后也不会有错误。而且可以在将来使用下面命令，随时更新环境，十分方便

$ bundle update

使用下面命令，启动转化和本地服务：

$ bundle exec jekyll serve

使用现成的模板

博客基于jekyll，而新手往往摸不着头脑，幸好有一些现成的模板可以直接使用：

以White Paper这个模板为例，可以直接下载压缩包，也可以使用如下命令clone到本地：

$ git clone https://github.com/vinitkumar/white-paper.git

把克隆下来的文件拷贝到你自己的目录就行了，这样你就有一个现成的网站结构了：
