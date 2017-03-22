---
title: node使用笔记
date: 2017-03-22 11:54:08
tags:
    - node
---

#### 1. npm install 迷之失败 
主要报错内容如下：

{% codeblock %}
npm ERR! Darwin 16.4.0
npm ERR! argv "/usr/local/bin/node" "/usr/local/bin/npm" "install" "-g" "gulp-cli"
npm ERR! node v6.7.0
npm ERR! npm  v3.10.3
npm ERR! code ETIMEDOUT
npm ERR! errno ETIMEDOUT
npm ERR! syscall connect

npm ERR! Cannot read property 'path' of null 
{% endcodeblock %}

公司网络最近很差，开始怀疑公司网络＝》终端使用代理失败＝》终于找到类似问题，解决方案如下：
`npm config set registry http://registry.npmjs.org/`

难道是因为https挂了？？