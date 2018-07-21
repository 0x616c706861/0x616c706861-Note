---
title: 安装 Hexo 并部署到 GitHub Pages
urlname: install-hexo-and-deploy-to-github-pages
date: 2018-07-22 01:58:25
tags:
- Hexo
- GitHub
---

* https://github.com/hexojs/hexo
* https://hexo.io/docs

## 1. 安装 Hexo

```
$ sudo npm install -g hexo-cli
$ hexo -v
os: Linux 4.14.54-1-MANJARO linux x64
http_parser: 2.8.1
node: 10.6.0
```

<!-- more -->

## 2. 为 GitHub Pages 创建项目

```
$ hexo init 0x616c706861.github.io
$ cd 0x616c706861.github.io
$ npm install
```

## 3. 运行测试服务器

```
$ hexo server
INFO  Start processing
INFO  Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.
```

## 4. 配置 - 博客信息

https://hexo.io/zh-cn/docs/configuration.html

```
$ vim _config.yml

~~~~~~~~~~~~~~~~~~ _config.yml ~~~~~~~~~~~~~~~~~~
# Site
title: Alpha's Note
subtitle:
description:
keywords:
author: Alpha
language: zh_CN
timezone: Asia/Shanghai

# URL
url: https://0x616c706861.github.io
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:
```

## 5. 配置 - 使用 GitHub Pages

https://github.com/hexojs/hexo-deployer-git

```
$ npm install hexo-deployer-git --save
$ vim _config.yml

~~~~~~~~~~~~~~~~~~ _config.yml ~~~~~~~~~~~~~~~~~~
# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: git@github.com:0x616c706861/0x616c706861.github.io
  branch: master
```

## 6. 监视文件

Hexo 能够监视文件变动并立即重新生成静态文件

https://hexo.io/zh-cn/docs/generating.html

```
$ hexo generate --watch
```
## 7. 发布文章

```
$ hexo new install-hexo-and-deploy-to-github-pages
INFO  Created: ~/0x616c706861.github.io/source/_posts/install-hexo-and-deploy-to-github-pages.md
```

## 8. 使用 Markdown 或者 Hexo 辅助函数编辑文章

Hexo 辅助函数：https://hexo.io/zh-cn/docs/helpers.html

推荐使用 VSCode 编辑，`shift + control + v`可预览

https://code.visualstudio.com/


## 一些常用命令

```
$ hexo new "postName" #新建文章

$ hexo new page "pageName" #新建页面

$ hexo generate #生成静态页面至 public 目录

$ hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）

$ hexo deploy #将 .deploy 目录部署到 GitHub

$ hexo help #查看帮助

$ hexo version #查看 Hexo 的版本
```