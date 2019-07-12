---
title: "wsl中使用原生docker"
date: 2018-03-02T12:15:19+08:00
draft: false
tags: ["wsl", "docker"]
categories: ["docker"]
subtitle: ""
descriptions: ""
bigimg:
---


wsl中使用原生docker

```bash
DESKTOP-APB1HCJ% sudo docker run hello-world
docker: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?.
See 'docker run --help'.
DESKTOP-APB1HCJ%
```

https://www.cnblogs.com/LiangSW/p/9842295.html 的 评论里，有提到

https://github.com/Microsoft/WSL/issues/2291#issuecomment-383698720

查到 https://github.com/Microsoft/WSL/issues/2291


```bash
DESKTOP-APB1HCJ% sudo service docker stop
[sudo] password for u:
 * Stopping Docker: docker
start-stop-daemon: warning: failed to kill 13661: No such process
No process in pidfile '/var/run/docker-ssd.pid' found running; none killed.
DESKTOP-APB1HCJ% sudo cgroupfs-mount
DESKTOP-APB1HCJ% sudo usermod -aG docker u
DESKTOP-APB1HCJ% sudo service docker start
 * Starting Docker: docker                                                                                                                                                                                                             [ OK ] DESKTOP-APB1HCJ% sudo docker run --rm hello-world
docker: Cannot connect to the Docker daemon at unix:///var/run/docker.sock. Is the docker daemon running?.
See 'docker run --help'.
DESKTOP-APB1HCJ%
```


## ref
- https://www.cnblogs.com/LiangSW/p/9842295.html
- https://www.cnblogs.com/xiaoliangge/p/9134585.html
