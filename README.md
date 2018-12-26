# Hexo博客搭建教程

## 准备工作

* 安装git
* 安装Node.js
* 注册github账号
* 创建新的仓库，名称为`xx.github.io`
* 添加本地电脑认证

```
ssh-keygen -t rsa -C "Github的注册邮箱地址"
```
生成两个文件：id_rsa/id_rsa.pub，复制id_rsa.pub里的内容到github的ssh认证key中即可

## 安装hexo

* 打开命令行工具

```
npm install -g hexo-cli
```

* 初始化项目

```
hexo init <folder>
```

* 在文件夹内执行

```
npm install
```

* 安装next主题

```
mkdir themes/next
curl -s https://api.github.com/repos/iissnan/hexo-theme-next/releases/latest | grep tarball_url | cut -d '"' -f 4 | wget -i - -O- | tar -zx -C themes/next --strip-components=1
```

> 若安装不了，可以直接克隆next项目下来

```
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

## 基本配置

```
title: 大艺术家_SN
subtitle: 事在人为，为者终成，生死之外又有什么是一定办不到的呢 
description: Painting talent persisted in playing music, but also dreamed of becoming a director and finally becoming a programmer's great artist.
author: chenshinan
language: zh-Hans
timezone: Asia/Shanghai

url: http://chenshinan.github.io
theme: next
deploy:
  type: git
  repository: git@github.com:chenshinan/chenshinan.github.io.git
  branch: master
```

## 基本命令

* 安装git部署脚本

```
npm install hexo-deployer-git --save
```

* 创建页面

```
hexo new page categories 
```
创建分类页面，在source/categories/index.md中添加type属性
```
---
title: 文章分类
date: 2018-01-01 10:00:00
type: "categories"   #这部分是新添加的
---
```
给模版添加这个分类属性，之后创建的新文章都会带上这个属性
```
title: {{ title }}
date: {{ date }}
categories:
tags:
```

* 创建文章

```
hexo new posts "Java8学习笔记" //hexo n "xx"
```
会生成一个markdown`./source/_posts/Java8学习笔记.md`

* 生成静态页面

```
hexo clean
hexo generate //hexo g
```

* 发布到服务器

```
hexo deploy //hexo d
```

* 本地启动

```
hexo server //hexo s
```
启动服务器，默认情况下，访问网站为http://localhost:4000/

参考文献：

- [官方文档](https://hexo.io/zh-cn/docs/)
- [github hexo主题大全](https://github.com/hexojs/hexo/wiki/Themes)
- [hexo+next主题及我走过的坑](https://www.jianshu.com/p/21c94eb7bcd1)