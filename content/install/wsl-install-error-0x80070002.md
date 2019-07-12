---
title: "win10 家族中文版 安装使用 wsl"
date: 2018-03-02T12:15:19+08:00
draft: false
tags: ["wsl"]
categories: ["wsl"]
subtitle: ""
descriptions: ""
bigimg:
---


win10 家族中文版 安装使用 wsl

勾选 适用于Linux的Windows子系统 报 0x80070002 错误

## env
- os: windows10 home
- wsl: ubuntu

## step

解决步骤如下：

1. 勾除 .net3.5
2. stop update
3. delete directorys
4. start update
5. restart
6. 勾选 .net3.5
7. 勾选 linux 子系统 成功
8. restart 

先尝试 勾选 .Net Framework 3.5(包括 .Net 2.0和3.0 ) 看是否也是会报一样错误。

如果会，则说明不是 Windows子系统特有错误。那么先修改 .Net 3.5 下的 0x80070002 .

参考 https://jingyan.baidu.com/article/656db918d9942ae381249cf2.html

再次勾选 .Net 3.5 则会正常。

然后再 勾选 适用于Linux的Windows子系统 不报 0x80070002 错误, 一切正常了。


## ref
- https://jingyan.baidu.com/article/656db918d9942ae381249cf2.html















