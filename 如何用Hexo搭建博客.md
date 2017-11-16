---
title: 如何用Hexo搭建博客
date: 2017-11-14 22:08:03
tags:
---
*首先Hexo是什么？一个博客框架，可以使用Markdown(或其他渲染引擎)来解析文章，速度快、且有丰富的插件功能，今天我们就来完成用Hexo来搭建博客，并将博客部署到GitHub网站上。*
# 安装
安装前电脑中必须要有以下应用程序：
Node.js
Git
接下来我们就可以用npm来安装Hexo了
`$ npm install -g hexo-cli`
# 建站
用以下命令在指定文件夹'myblog'(或者其他名字)生成Hexo所需的文件
`$ hexo init myblog`
`$ cd myblog`
`$ npm install`
部分文件目录的用途如下：
### _config.yml
网站的配置信息，可以更改部分的参数。
如：
title 网站的标题
description 网站描述
autor 你的名字
theme 当前主题名称
deploy 部署部分的设置
### scaffolds
模板文件夹
### source
存放用户资源的地方
### theme
存放主题的文件夹，放入主题文件夹后，将_config.yml文件里的theme改为相对应的文件夹名字并部署到GItHub上就能生效了
# 写博客
执行以下命令新建一篇文章
`$ hexo new 文章的名称`
就会看见一个md文件的路径，编辑这个文件就可以用Markdown语法来写你的博客文章了
# 部署到GitHub
写完之后，我们需要安装Hexo部署插件
`$ npm install hexo-deployer-git --save`
记得在_config.yml上修改配置，不然你的仓库类型和地址都没有怎么给你部署啊
deploy:
  type: git
  repo: '仓库的地址'
然后执行以下命令就能将网站部署到服务器上了
`$ hexo generate`
`$ hexo deploy`
# 瞧一瞧
打开你的仓库的地址，点击Settings，滑到GitHub Pages就能看见你的博客地址啦！
# 上传源代码
刚刚部署到GitHub上的仓库只是你的博客，我们应该在GitHub上新建一个仓库来保存你的源代码
也就是每次发布新文章之后，你还要把文章的源代码推送到这个仓库来，一个仓库是博客，一个仓库是文章的源代码，这样才能保证数据的万无一失!