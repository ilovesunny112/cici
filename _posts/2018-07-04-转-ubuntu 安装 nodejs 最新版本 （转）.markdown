---
layout: post
title:  "如何通过 ubuntu 安装最新 nodejs 步骤 转"
date:   2018-07-04 22:36:02 +0800
categories: ubuntu nodejs npm linux
---
# (转) 如果通过 ubuntu 安装 最新 nodejs

nodejs 已经更新到 了 10.多的版本。 ubuntu的自身版本比较低


更新 ubuntu 软件源

``` 
sudo apt-get update
sudo apt-get install -y python-software-properties softerware-properties-common
sudo add-apt-registory ppa:chris-lea/node.js
sudo apt-get update
```

安装 nodejs

```
sudo apt-get install nodejs
sudo apt install nodejs
sudo apt install npm
```

更新 npm 包镜像源 方便快速下载

```
sudo npm config set registry https://registry.npm.taobao.org
sudo npm config list
```
全局安装 n 管理器(用于管理 node 版本)


```
sudo npm install n -g
```
安装最新的 nodejs (stable 版本)

```
sudo n stable
sudo node -v
```


待续...





 

 



[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
