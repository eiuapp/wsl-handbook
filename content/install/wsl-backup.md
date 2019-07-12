---
title: "wsl backup"
date: 2018-03-02T12:15:19+08:00
draft: false
tags: ["wsl"]
categories: ["wsl"]
subtitle: ""
descriptions: ""
bigimg:
---

## LxRunOffline

https://github.com/DDoSolitary/LxRunOffline

[WSL安装和使用LxRunOffline备份](https://www.cnblogs.com/ahmczsy/p/10544926.html)

通过 [scoop](https://github.com/lukesampson/scoop) 安装

安装好后最好重启下电脑，如果不重启可能有问题

常用LxRunOffline命令

```
//已经安装的wsl
LxRunOffline.exe list 
//安装wsl
LxRunOffline.exe install
//备份wsl
LxRunOffline.exe export
//启动一个wsl
LxRunOffline.exe run
```

```
lxrunoffline.exe export -n Ubuntu -f wsl-ubuntu-20190712.tar.gz
```

## Tar

https://help.ubuntu.com/community/BackupYourSystem/TAR


## 导出导入Linux子系统



