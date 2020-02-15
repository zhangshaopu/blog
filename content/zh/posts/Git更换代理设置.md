---
title: Git 更换代理设置
date: 2020-02-09T20:56:07+08:00
draft: false
excerpt: 使用github的一些坑
toc: true
tags: [git]
categories: [tech,git]


---
Github 更换代理设置
<!--more-->

### 两种形式： 
#### http形式：
```html
git clone https://github.com/xxx/git.git
```


#### 修改git config：
#### 一、走http代理：

#### 1. 只对github进行代理

```html
git config --global http.https://github.com.proxy https://127.0.0.1:1080
git config --global https.https://github.com.proxy https://127.0.0.1:1080
```
#### 2. 全局代理
```html
git config --global http.proxy "http://127.0.0.1:8080" 
git config --global https.proxy "http://127.0.0.1:8080"
```
#### 二、走 socks5 代理（如 Shadowsocks）
#### 1. 全局代理
```html
git config --global http.proxy "socks5://127.0.0.1:1080"
git config --global https.proxy "socks5://127.0.0.1:1080"
```
#### 2. 只对github进行代理
```html
git config --global http.https://github.com.proxy socks5://127.0.0.1:1086
git config --global https.https://github.com.proxy socks5://127.0.0.1:1086
```
#### 三、查看已有配置
```html
git config --global -l
```

> 注意：8080为端口号，需要查看vpn的http/socks5端口号

#### 取消设置：
```html
git config --global --unset http.proxy
git config --global --unset https.proxy
```


